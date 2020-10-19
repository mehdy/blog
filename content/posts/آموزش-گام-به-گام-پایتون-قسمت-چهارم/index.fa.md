---
title: آموزش گام به گام پایتون - قسمت چهارم
date: 2019-05-07
lastmod: 2020-10-19T10:10:00+03:30
tags: ['پایتون', 'آموزش']
cover:
    image: python-step-by-step-4th.png
    alt: آموزش گام به گام پایتون - قسمت چهارم - توابع
    relative: true
---

در [قسمت قبل]({{< ref "/posts/آموزش-گام-به-گام-پایتون-قسمت-سوم" >}}) در مورد **داده ساختارها** یاد گرفتیم. تو این قسمت می‌خوایم یاد بگیریم چجوری قسمتی از منطق برنامه رو به صورت مستقل قابل استفاده کنیم. این کار رو به کمک توابع انجام می‌دیم.

## تابع

هموجوری که از اسمش پیداست تابع چیزیه که بر اساس ورودی‌هایی که می‌گیره یک سری عملیات رو انجام میده و ممکنه یه سری خروجی هم داشته باشه یا اثرات جانبی داشته باشه (مثلا توی یه فایل چیزی بنویسه). فرض کنید ما یه برنامه می‌خوایم بنویسم که یه سری عدد بهش بدیم و اونایی که عدد اول بودن رو برامون چاپ کنه.

```python
input_text = input("enter numbers: ")
for i in input_text.split(' '):
    number = int(i)
    is_prime = True
    for j in range(2, number):
        if number % j == 0:
            is_prime = False
            break
    if is_prime:
        print(number)
```

این کد همون کاری رو می‌کنه که می‌خوایم. حالا فرض کنید تو برنامه‌ چندیدن جا می‌خوایم چک کنیم که یک عدد اول هست یا نه؟ باید بیایم از وسط این کد اون قسمتی رو که چک می‌کنه عدد اول هست یا نه رو کپی کنیم ببریم اونجا هم استفاده کنیم. مشکلاتی که این کار داره اینه که حجم کد رو الکی زیاد می‌کنه و ممکنه بخوایم الگوریتممون رو عوض کنیم باید بریم همه جا این کار رو بکنیم. پس اگر بیایم اون قسمت از کد رو به صورت یه تابع بنویسیم این مشکلاتمون حل میشه.

```python
def is_prime(number):
    for i in range(2, number):
        if number % i == 2:
            return False
    return True

input_text = input("enter numbers: ")
for i in input_text.split(' '):
    number = int(i)
    if is_prime(number):
        print(number)
```

نه تنها مشکلاتی که داشت رو حل کردیم بلکه کد رو هم تمیزتر کردیم. یعنی خوندن کد راحت‌تر شده.

تو پایتون **توابع** می‌تونن چندین ورودی و چندین خروجی داشته باشن. برای مثال

```python
def add(a, b):
    return a + b

def min_avg_max(list_of_numbers):
    sum = 0
    min = max = list_of_numbers[0]
    for i in list_of_numbers:
        if i < min:
            min = i
        if i > max:
            max = i
        sum += i
    return min, sum/len(list_of_numbers), max
```

همچنین میشه برای ورودی‌ها مقدار اولیه تعیین کرد و اگر موقع صدا زدن مقدار اون ورودی داده نشه، مقدار پیش‌فرض استفاده بشه

```python
def greet_user(name, lang='en'):
    if lang == 'en':
        print(f"hello, {name}")
    elif lang == 'fa':
        print(f"سلام، {name}")
    else:
        print("language is not specified")

greet_user("Ali") # hello, Ali
greet_user("Ali", 'en') # hello, Ali
greet_user("Ali", 'fa') # سلام، Ali
```

در حالت عادی موقع صدا زدن توابع باید مقادیر ورودی رو به همون ترتیبی که تو تعریف تابع اومده به تابع داد. هرچند پایتون این امکان رو میده که مقادیر رو صریحا برای هر ورودی مشخص کنیم بدون توجه به ترتیبشون. برای مثال تابع قبلی رو در نظر بگیرید

```python
greet_user(name="Ali") # hello, Ali
greet_user(name="Ali", lang='en') # hello, Ali
greet_user("Ali", name='fa') # سلام، Ali
greet_user(lang='en', name="Ali") # hello, Ali
```

تا قسمت بعد!
