---
title: "آموزش کار با eopkg — پیشرفته 2"
description: "آموزش کار با eopkg — پیشرفته 2"
image: "images/post/course/eopkg4.jpg"
date: 2021-03-27T16:43:08+04:30
author: "Gnkalk"
tags: ["eopkg", "Course", "eopkg-course"]
categories: ["Linux"]
draft: false
---
توی این اموزش قصد دارم بهتون یاد بدم چجوری یه ریپو برا خودتون بزنید و حالشو ببرید :)))

خب ابتدا باید پیش نیاز های اموزش رو نصب کنید ، برای این کار از دستور زیر استفاده کنید :

```
sudo eopkg it -c system.devel solbuild
```

پس از اون باید اینیت سولبیلد ک حدود ١۵۰ مگ هست رو دانلود کنید ، برای اینکار..

```
sudo solbuild init
```

و سپس اون رو اپدیت کنید :

```
sudo solbuild update
```

خب حالا ک پیش نیاز هارو نصب کردیم و اماده باید بریم سراغ اینکه یه پکیجر ایجاد کنیم ، برای اینکار یه فولدر به اسم .solus بسازید و توی اون فایل پکیجر رو اضافه کنید :

```
touch packager
```

و سپس توی اون مقادیر زیر رو اضافه میکنید :

>   [Packager]
>
>   Name=First_Name Last_Name
>
>   Email=username@second_level_domain.tld

حالا بسته common رو دانلود میکنیم : 

```
git clone https://dev.getsol.us/source/common.git
```

سپس یه دایرکتوری برای بیلد کردن پکیج ها ایجاد میکنیم ، داخل دایریکتوری یه سری فایل از common لینک میکنیم :

```
ln -sv common/Makefile.common .
ln -sv common/Makefile.toplevel Makefile
ln -sv common/Makefile.iso .
```

سپس برای فچ یمل یه الیاس تایین میکنیم..

```
alias fetchYml="$HOME/Solus-LB/common/Scripts/yauto.py"
```

حالا یکی از نرم افزار های kde به اسم kile رو پکیج میکنیم 🙂

ابتدا وارد دایرکتوری بیلد میشیم و یک دایرکتوری به اسم پکیج میسازیم.. بعد وارد پوشه میشیم و گیت لوکال ست میکنیم :

```
git config --local user.name "My Name"
git config --local user.email "username@second_level_domain.tld"
```

و بعد میک فایل رو اکو میکنیم :

```
echo "include ../Makefile.common" > Makefile
```

حالا برای بروز شدن سولبیلد اون رو اپدیت میکنیم :

```
sudo solbuild update
```

خب فچ یمل پکیج رو میگیریم :

```
fetchYml https://github.com/KDE/kile/archive/v٣.۰b٣.tar.gz
```

حالا خودتون فایل yml رو ویرایش کنید..

حال به سخت ترین بخش کار رسیدیم جایی ک باید نیازمندی های هر پکیج رو قرار بدید ، این کار بسیار دشوار هست و پیدا کردن نیازمندی ها نیز دشوار تر ، شما در بسته های cmake میتوانید از cmakelist.txt کمک بگیرید و همچنین میتوانید با استفاده از rpm آن پکیج نیازمندی های آن را پیدا کنید و …

وقتی همه این هارو تکمیل کردید ، میبایست فایل yml شما ساختاری این چنینی داشته باشد :

```


    name       : kile

    version    : ٣.۰.۰٣

    release    : ١

    source     :

        – https://github.com/KDE/kile/archive/v٣.۰b٣.tar.gz : ddc٢٧٧e١۵٨٩۵۶٣۴٧۵٣٧۶۰۶٧ad٣١٧eef۵a٨cc٩f۵cb٨٢f١٣٣٨۶١٩d۶b۶d۵٢ddf۴e١

    license    : GPL-٢.۰-or-later

    component  : editor

    summary    : Kile is a user-friendly TeX/LaTeX editor for the KDE desktop environment.

    description: Kile is a user-friendly TeX/LaTeX editor for the KDE desktop environment.

    builddeps  :

        – pkgconfig(Qt۵Core)

        – pkgconfig(Qt۵Script)

        – plasma-framework-devel

        – okular-devel

        – pkgconfig(poppler-qt۵)

        – extra-cmake-modules

        – kcrash-devel

        – kdbusaddons-devel

        – kdoctools-devel

        – kguiaddons-devel

        – kiconthemes-devel

        – ktexteditor-devel

        – ki١٨n-devel

        – kinit-devel

        – khtml-devel

        – kio-devel

        – kparts-devel

        – kxmlgui-devel

    rundeps    :

        – qt۵-base

        – plasma-framework

        – okular

        – texlive

        – imagemagick

        – tar

        – zip

        – gzip

        – bzip٢

        – kbibtex

        – jabref

    build      : |

        %cmake

    install    : |

      %make_install

```

وقتی از ساختار پکیجتون مطمئن شدید و کامل بود با استفاده از دستور زیر اون رو بیلد کنید :

```
sudo solbuild build package.yml -p main-x٨۶_۶۴
```

خب یه دایرکتوری بسازید (اسم دلخواه) و فایل .eopkg پکیجتون رو بزارید توش ، ما در اینجا یک دایرکتوری با نام Solus-LR ایجاد کردیم و فایل .eopkg رو توی اون قرار دادیم ؛ حالا وقت اون رسیده ک فایل ایندکس ریپو رو بگیریم : 

```
sudo eopkg index -o ~/Solus-LR/eopkg-index.xml --skip-signing ~/Solus-LR
```

حالا همونطور ک تو اموزش های قبل توضیح داده بودیم این ریپو رو اد میکنیم :

```
sudo eopkg ar Solus-LR ~/Solus-LR/eopkg-index.xml.xz
```

کار به پایان رسید و شما میتونید با دستور eopkg lr ریپو های خودتون رو مشاهده کنید :)

اما اگر یک ریپو خوب ساختید و قصد به اشتراک گذاشتن اون رو داشتید یه ریپو تو گیتهاب باز کنید و بعد پوشه ای ک توی اون عملیات ایندکس رو انجام دادید توی ریپو اپلود کنید ، و با استفاده از لینک rew اون رو به پکیج منیجر اد کنید..