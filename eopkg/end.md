---
title: "آموزش کار با eopkg — پایانی"
description: "آموزش کار با eopkg — پایانی"
image: "images/post/course/eopkg5.jpg"
date: 2021-04-08T16:43:08+04:30
author: "Gnkalk"
tags: ["eopkg", "Course", "eopkg-course"]
categories: ["Linux"]
draft: false
---

به اخرین قسمت از سری اموزش های eopkg رسیدیم ، توی این قسمت قراره چیزایی رو بهتون یاد بدیم ک باعث راحت تر شدن کار با eopkg میشه 🙂

یکی چیز هایی ک باعث میشه تو امر های مختلف بتونیم سریع تر عمل کنیم و.. کامند اپشن ها هستن ، در اصل کامند اپشن ها بعد از کامند اصلی قرار میگیرند :

```
eopkg [Command] [Command Option]
```

هر کامند دارای کامند اپشن های مختلفیه ک شما میتوانید با دستور زیر اونهارو ببینید :

```
eopkg [Command] -h
```

اما بجز این کامند اپشن ها ، کامند اپشن هایی وجود دارن تحت عنوان « گلوبال کامند اپشن » که در همه دستور ها قابل استفاده هستن… مثل تایید همه ( yes-all ) که نحوه استفاده از اون رو مشاهده میکنید :

```
eopkg [Command] -y
or
eopkg [Command] --yes-all
```

کاری که این کامند اپشن انجام میده تایید همه پرسش های eopkg هنگام انجام هر گونه فرایند هست.

کامند اپشن بعدی برای پسورد ها هست که دیگه لازم نیست مدام به eopkg پسوردی رو وارد کنید ، با این کامند اپشن به صورت اتوماتیک این کار رو انجام میده :

```
eopkg [Command] -p [Your Password]
or
eopkg [Command] --password [Your Password]
```

این دو گلوبال کامند اپشن پر کاربرد ترین گلوبال کامند اپشن های هستن در ادامه به کامند اپشن های عادی میپردازیم…

کامند اپشن مولفه (ترجمه واژه انگلیسی) یا دسته بندی که کامند اپشن دستور « it » یا همون « install » هست ، این کامند اپشن یک دسته بندی از مخازن رو نصب میکنه ، برای مثال من با کامند زیر دسته kde که زیر دسته desktop هست رو نصب میکنم :

```
eopkg it --component desktop.kde
or
eopkg it -c desktop.kde
```

شاید براتون پیش اومده باشه که یک پکیج رو در دو مخزن داشته باشید ولی بخواید از مخرنی ک پیشفرض نیست اون رو نصب کنید ، برای اینکار از کامند اپشن ریپوزیتوری کمک میگیریم :

```
eopkg it -r [Repo Name] [Package Name]
or 
eopkg it --repository [Repo Name] [Package Name]
```

کامند اپشن اخر برای رینستال (نصب مجدد ) نرم افزار یا پکیج مورد نظر هست : 

```
eopkg it --reinstall [Package Name]
```

این چند کامند اپشن پرکاربرد ترین کامند اپشن های دستور اینستال بودن ، در ادامه به کامند اپشن های دستور ریموو میپردازیم..

**نکته** برخی از کامند اپشن های دستور اینستال و ریموو مشترک هستن

و اخرین کامند اپشنی که به کارتون میاد کامند اپشن پرج هست ، این کامند اپشن نرم افزار ها و پکیج های اضافی سیستم رو پاک میکنه :

```
eopkg rm --purge 
```

به دلیل تعداد بالای کامند اپشن ها نمیشه همه اونهارو گفت و شما میتونید خودتون اونهارو ببینید (همونطور که ابتدا گفتم) ، کامند اپشن ها خیلی به کار شما سرعت میبخشن و باعث میشن سریع تر و بهتر از eopkg استفاده کنید 🙂

ممنون از اینکه این مقاله رو مطالعه کردید…