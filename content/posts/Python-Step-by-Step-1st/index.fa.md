---
title: آموزش گام به گام پایتون - قسمت اول
date: 2018-01-25
lastmod: 2020-10-19T10:10:00+03:30
tags: ['پایتون', 'آموزش']
cover:
    image: python-step-by-step-1st.png
    alt: آموزش گام به گام پایتون - قسمت اول - مقدمات پایتون
    relative: true
---

در [قسمت قبل]({{< ref "/posts/Python-Step-by-Step-0th" >}}) توضیحاتی کلی در مورد پایتون دادم و خیلی سریع و کوتاه به کد «سلام دنیا!» اشاره کردم. در این قسمت می‌خوام در مورد مقدمات پایتون بنویسم و کم کم بریم سراغ کد نوشتن.

## نوشتن و اجرای کد

در قسمت قبل، کد «سلام، دنیا!» رو نوشتم ولی توضیحی در مورد اجراش ندادم.
کدهای پایتون رو باید در فایل‌هایی با پسوند py نوشت و بعد به وسیله‌ی مفسر پایتون کد رو اجرا کرد. برای مثال اگر کد «سلام، دنیا!» رو در فایلی به اسم *helloworld.py* بنویسیم و ذخیره کنیم، با اجرای این دستور در شِل (ترمینال لینوکس و مک یا پاورشِل ویندوز) می‌تونیم کد رو اجرا کنیم.

```bash
python3 helloworld.py
```

یا می‌تونید دستور *python* رو اجرا کنید و در شِل پایتون کد رو خط به خط بنویسد و خط به خط اجرا کنید. این قابلیت برای آزمایش کدهای کوچک و دنبال کردن روند اجرای کد خیلی می‌تونه مفید باشه.

خوب تا اینجا یاد گرفتیم چجوری یه کد ساده پایتون رو بنویسیم و اجرا کنیم.

## متغیرها و تایپ‌ها

تعریف متغیر تو پایتون به سادگی کدهای زیره.

```python
some_var = 42
```

تو پایتون نوع متغیرها نوشته نمیشه و خود مفسر موظفه تا نوعش رو تشخیص بده. تایپ‌های زیادی تو پایتون داریم که فعلا چند تایپ ساده و پرکاربرد رو معرفی می‌کنم و بعدا در ادامه با تایپ‌های بیشتری آشنا خواهیم شد.

دو نوع **int** و **float** برای اعداد صحیح و اعشار هستند.

```python
int_var = 314 # int
float_var = 3.141592 # float
```

نوع **‌bool** هم برای نگهداری درست و غلط.

```python
true_val = True
false_val = False
```

برای کاراکترها پایتون تایپ **str** رو داره که از یونیکد هم پشتیبانی می‌کنه. تو پایتون با سه روش میشه متغیر از نوع رشته تعریف کرد.

```python
single_quote_str = 'good for strings containing double quote(")'
double_quote_str = "good for strings containing single quote(')"
triple_quote_str = """good for long string containing both single quote(')
                                and double quote(") and multi-line text like this one"""
```

اگر جایی خواستید با نوع یه متغیر رو بدونید می‌تونید از تابع *type* استفاده کنید.

```python
unknown_var = 42
print(type(unknown_var)) # prints <class 'int'>

other_unknown_var = "some text"
print(type(unknown)) # prints <class 'str'>
```

## عملگرها

الان که یاد گرفتیم چجوری متغیر تعریف کنیم، می‌تونیم بریم سراغ اینکه چجوری از این متغیرها استفاده کنیم.

## عملگرهای محاسباتی

```python
a = 5
b = 4

print(a + b) # 9
print(a - b) # 1
print(a * b) # 20
print(a / b) # 1.25
print(a // b) # 1 تقسیم صحیح
print(a % b) # 1 باقیمانده
print(a ** b) # 625 توان
```

همچنین با یک سری از این عملیات‌ها رو میشه برای رشته هم انجام داد.

```python
a = "first"
b = "second"

print(a + b) # firstsecond
print(a * 2) # firstfirst تکرار رشته
```

و از اونجایی که **True** و **False** در واقع ۱ و ۰ هستند در عملگرهای محاسبه‌ای به عنوان ۱ و ۰ عمل می‌کنن.

```python
print(True + True) # 2
print(False * True) # 0
```

## عملگرهای مقایسه‌ای

```python
a = 5
b = 4

print(a > b) # True بزرگ‌تر
print(a < b) # False کوچک‌تر
print(a >= b) # True بزرگ‌تر مساوی
print(a <= b) # False کوچک‌تر مساوی
print(a == b) # False تساوی
print(a != b) # True نامساوی
```

## عملگرهای منطقی

```python
a = True
b = False

print(a and b) # False
print(a or b) # True
print(not a) # False
print(not b) # True
```

تا [قسمت بعد]({{< ref "/posts/Python-Step-by-Step-2nd" >}})!
