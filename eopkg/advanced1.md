---
title: "آموزش کار با eopkg — پیشرفته"
description: "آموزش کار با eopkg — پیشرفته"
image: "images/post/course/eopkg3.jpg"
date: 2021-03-11T16:43:08+04:30
author: "Gnkalk"
tags: ["eopkg", "Course", "eopkg-course"]
categories: ["Linux"]
draft: false
---

همونطور که در سری مقالات مرتبط با تاریخچه eopkg گفتم ، eopkg پکیج منیجر گسترده ای هست و همین باعث میشه اموزش اون طولانی باشه 🙂

خب توی این مقاله یکم بیشتر جلو میریم و یاد میگرید چجوری پکیج بیلد کنید و….

اول بهتره یه چیزی رو بگم که یادم رفت 👀 ؛ چجوری از eopkg هلپ بگیریم و اصلا خودمون دستوراش رو بخونیم ؟ 

```
eopkg help
```

شما میتونید اینجوری خودتون هلپ eopkg رو نگاه کنید و یادش بگیرید =)

یه مورد دیگه ای یادم رفت بود هم حذف ریپو بود ؛ برای حذف ریپو : 

```
sudo eopkg rr
```

حالا میرسیم به بیلد کردن پکیج ها ؛ شما تو eopkg به دو صورت میتونید پکیج بیلد کنید که یکی از اونا وابسته به سولبیلد هست و دیگری رو خودش انجام میده ، ما اینجا نوع دوم رو اموزش میدیم و نوع سوم رو توی قسمت بعد اموزش میدیم .

شما برای بیلد کردن پکیج نیاز به یک فایل pspec دارید که توی اون اطلاعات پکیج نوشته شده و یا میتونید اون پکیج رو از مخازن به صورت مستقیم بیاد کنید .

برای بیلد کردن پکیج pspec ای که دارید (میتونید از ترد پارتی سولاس یکی بگیرید) ؛ توی اون پوشه ای که فایل pspec هست دستور :

```
sudo eopkg bi
```

رو اجرا کنید ، eopkg ادرس سورس پکیج که توی pspec هست رو پیدا میکنه و اون پکیج رو دانلود میکنه سپس اون رو کامپایل و بیلد میکنه اما توجه کنید الان اون پکیج نصب نشده ! تنها بیلد شده و فایل .eopkg اون توی پوشه ای که بیلد کردید هست ؛ برای نصب از دستور زیر استفاده کنید :

```
eopkg it *.eopkg
```

حالا اگه بازم خواستید پکیجی از ترد پارتی نصب کنید این کار رو انجام ندید چون زمان بره و اپدیت کردن پکیج ها هم براتون یکم دشوار میشه ؛ میتونید از eopkg٣p استفاده کنید ، جهت نصب eopkg٣p :

```
pip٣ install eopkg٣p
```

اینم از اموزش بیلد پکیج از pspec 🙂 حالا اگه میخواید یه پکیج رو از مخازن بیلد کنید : 

```
sudo eopkg fc [package name]
```

دستورات مخفف نشده : 

```
sudo eopkg remove-repo

sudo eopkg build

sudo eopkg install *.eopkg

sudo eopkg fetch
```