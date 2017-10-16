+++
title = "The story of a nil pointer receiver"
date = "2017-10-16"
categories = ["go"]
tags = ["pointer","nil", "receiver", "Go", "golang"]
keywords = ["go", "golang", "receiver", "nil", "pointer"]
thumbnailImagePosition = "left"
thumbnailImage = "/images/2017-10-the-story-of-nil-pointer-receiver.jpg"
+++

Let's assume we want to store `Gender` as an attribute for our users.

<!--more-->

And since we use PostgreSQL we can define an enum for gender like this:
```sql
CREATE TYPE gender_type AS ENUM('MALE', 'FEMALE', 'OTHER');
```
Now let's see how should we use `gender_type` in our code.
I always prefer to have as much similarity as possible between my models and my database design so I create a new type for `Gender` as I did in database and implement the `Scanner` interface:
```go
package gender

// Gender type is nothing more than a string
type Gender string

import (
	"database/sql/driver"
	"errors"
	"fmt"
)

const (
	MALE Gender = "MALE"
	FEMALE Gender = "FEMALE"
	OTHER Gender = "OTHETR"
)

func (g *Gender) Scan(src interface{}) (err error) {
	switch val := src.(type) {
		case []byte:
			*g = Gender(string(val))
		// OTHER CASES ...
		default:
			err = fmt.Errorf("unexpected type: %q", src)
	}
	return
}

func (g Gender) Value() (value driver.Value, err error) {
	if g == MALE || g == FEMALE || g == OTHER {
		return string(g), nil
	}
	return nil, fmt.Errorf("Invalid Gender value: %q", g)
}
```
Now let's use our `Gender` type in the user model:

```go
package model

type User struct {
	ID int
	Name string
	// ...
	Gender gender.Gender `sql:"type:gender_type"`
}
```
and everything works fine now...except when we want to be able to have **NULL** values for gender and we modify the model to this
```go
Gender *gender.Gender `sql:"type:gender_type"`
```
Now when we create an empty instance of user model to scan from database the `Gender` field is **nil** and when the `Scan` method is called the pointer receiver(g) is **nil** too. And when we try to dereference the g to update its value we receive `panic: runtime error: invalid memory address or nil pointer dereference`.  
The instant solution that comes to mind is to do this:

```go
// instead of *g = Gender(string(val))
g = &Gender(string(val))
```
But as soon as you find this solution, you find it useless because this is what happens.

1. you create an empty instance of user so the gender field is a nil pointer (a pointer pointing to nothing)
2. you call the scan method and go sees that you want a pointer receiver, so it creates a **new** pointer pointing the the value of gender(which is currently **nil**)
3. you create a new `Gender` instance and put its address in the pointer you receieved.
4. But this is the **new** pointer that go created for you and the pointer in user model is still untouched
5. And BOOM!

# Conclusion
Be really careful with these pointer receivers and as long as you can don't dereference a pointer receiver!  
I'd be glad to see what do you think of the problem and what's your solution?

## P.S.
The solution I used was to look other similar types out there and see what they do and here is what they do:
https://golang.org/src/database/sql/sql.go?s=4291:4610#L151
