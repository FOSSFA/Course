---
title: "آموزش کار با eopkg — مقدماتی 2"
description: "آموزش کار با eopkg — 2 مقدماتی"
image: "images/post/course/eopkg2.jpg"
date: 2021-03-06T16:43:08+04:30
author: "Gnkalk"
tags: ["eopkg", "Course", "eopkg-course"]
categories: ["Linux"]
draft: false
---

در قسمت اول یه سری از دستورات ک در استفاده روز مره نیاز میشه رو بهتون اموزش دادیم در این قسمت میخوام یه سری دیگه از دستورات که بازم در استفاده روز مره نیازتون میشه رو بهتون معرفی کنم.

خب شاید پیش اومده باشه یه پکیجی نصب کرده باشید و بخواید یه سری اطلاعات در مورد اون پکیج به دست بیارید برای این کار از دستور زیر استفاده میشه :

```
sudo eopkg info [package name]
```

حالا فرض کنید شما یه پکیجی نصب کردید و میخواید فقط خود اون پکیج رو پاک کنید برای این کار از دستور زیر کمک بگیرید :

```
sudo eopkg rm [package name]
```

خب باید بگم دستور rmf هم اون پکیج رو پاک میکنه براتون و هم پکیج هایی ک اگه اون نباشن کار نمیکنن در اصل میاد و یه پاک سازی انجام میده ولی اگه یادتون رفت اون f رو بزنید و rm زدید ؛ با استفاده از دستور زیر اون سری پکیج های هرزنامه موجود رو پاک کنید :

```
sudo eopkg rm --purge
```

حالا که قشنگ سیستم رو تمیز کردید شاید میخواید یه پکیج جدید نصب کنید ولی نمیدونید اسم دقیقش چیه؟ برای اینکار از دستور زیر کمک بگیرید و پکیج مورد نظر رو سرچ کنید :

```
sudo eopkg sr [package name]
```

خب الان فرض کنید یه پکیج نیاز دارید ک توی ریپو اصلی نیست خب باید ریپو رو اد کنید برای اینکار از دستور زیر کمک بگیرید :

```
sudo eopkg ar [repo neme] [repo url]
```

الان ک ریپو رو اضافه کردید و پکیجتون رو نصب کردید دیگه از امنیت اون ریپو مطمئن نیستید ولی بازم بهش احتیاج دارید برای اینکار میتونید اون ریپو رو غیر فعال کنید تا دیگه پکیجی ازش نصب یا اپدیت نشه :

```
sudo eopkg dr [repo name]
```

حالا دوباره به اون ریپو نیاز پیدا کردید میتونید دوباره اون ریپو رو فعال کنید :

```
sudo eopkg er [repo name]
```

اینم از قسمت دوم اموزش eopkg شما میتونید از این دستور ها به صورت کامل هم استفاده کنید :

**نکته** بر روی info هیچگونه مخفف سازی صورت نگرفته

```
sudo eopkg remove [package name]

sudo eopkg remove --purge

sudo eopkg search [package name]

sudo eopkg add-repo

sudo eopkg disable-repo

sudo eopkg enable-repo
```

باتشکر از اینکه این مقاله رو مطالعه کردید