<div dir="rtl">
# گنو میک
* گنو میک ابزاری است که تولید فایل‌های اجرایی و سایر فایل‌های غیر منبع یک برنامه را از فایل‌های منبع برنامه کنترل می‌کند.

* میک دانش خود را در مورد نحوه ساخت برنامه شما از فایلی به نام makefile دریافت می کند که هر یک از فایل های غیر منبع و نحوه محاسبه آن را از فایل های دیگر فهرست می کند. وقتی برنامه ای می نویسید باید برای آن یک makefile بنویسید تا بتوان از Make برای ساخت و نصب برنامه استفاده کرد.

 > قابلیت های Make‍‍‍‍‍‍‍‍
 ```
میک به کاربر نهایی امکان می‌دهد بسته شما را بدون اطلاع از جزئیات نحوه انجام آن بسازد و نصب کند -- زیرا این جزئیات در فایل make که شما ارائه می‌کنید ثبت می‌شوند.
به طور خودکار مشخص کنید که کدام فایل ها باید به روز شوند، بر اساس کدام فایل های منبع تغییر کرده اند. همچنین به طور خودکار ترتیب مناسب برای به‌روزرسانی فایل‌ها را تعیین می‌کند، در صورتی که یک فایل غیر منبع به فایل غیر منبع دیگری وابسته باشد
در نتیجه، اگر چند فایل منبع را تغییر دهید و سپس Make را اجرا کنید، نیازی به کامپایل مجدد همه برنامه شما نیست. فقط آن دسته از فایل‌های غیر منبع را که به طور مستقیم یا غیرمستقیم به فایل‌های منبعی که تغییر داده‌اید وابسته هستند، به‌روزرسانی می‌کند.

```

Make محدود به زبان خاصی نیست. برای هر فایل غیر منبع در برنامه، makefile دستورات پوسته برای محاسبه آن را مشخص می کند. این دستورات پوسته می توانند یک کامپایلر را برای تولید یک فایل شی، پیوند دهنده برای تولید یک فایل اجرایی، ar برای به روز رسانی کتابخانه، یا TeX یا Makeinfo را برای قالب بندی مستندات اجرا کنند
Make محدود به ساخت پکیج نیست. همچنین می‌توانید از Make برای کنترل نصب یا حذف نصب یک بسته، ایجاد جداول برچسب‌ها برای آن، یا هر کار دیگری که می‌خواهید انجام دهید، استفاده کنید تا هنگام نوشتن نحوه انجام آن، ارزش آن را داشته باشید.
قوانین و اهداف بسازید
یک قانون در makefile به Make می گوید که چگونه یک سری دستورات را برای ساختن یک فایل هدف از فایل های منبع اجرا کند. همچنین فهرستی از وابستگی های فایل هدف را مشخص می کند. این لیست باید شامل تمام فایل‌هایی باشد (اعم از فایل‌های منبع یا سایر اهداف) که به عنوان ورودی دستورات در قانون استفاده می‌شوند.

در اینجا یک قانون ساده به نظر می رسد:

هدف:   تبعیت ...
          دستور
          ...
وقتی Make را اجرا می کنید، می توانید اهداف خاصی را برای به روز رسانی مشخص کنید. در غیر این صورت، به‌روزرسانی‌ها را اولین هدف فهرست‌شده در فایل ایجاد کنید. البته، هر فایل هدف دیگری که به عنوان ورودی برای تولید این اهداف مورد نیاز است، ابتدا باید به روز شود.

Make از makefile استفاده می کند تا بفهمد کدام فایل های هدف باید به روز شوند و سپس تعیین می کند که کدام یک از آنها واقعاً نیاز به به روز رسانی دارند. اگر یک فایل هدف جدیدتر از همه وابستگی‌هایش باشد، از قبل به‌روز است و نیازی به بازسازی ندارد. سایر فایل‌های هدف باید به‌روزرسانی شوند، اما به ترتیب درست: هر فایل هدف باید قبل از اینکه در بازسازی اهداف دیگر استفاده شود، بازسازی شود.

مزایای ساخت گنو
GNU Make دارای ویژگی‌های قدرتمند بسیاری برای استفاده در فایل‌های میک است، فراتر از آنچه نسخه‌های Make دیگر دارند. همچنین می‌تواند فایل‌های میانی را که نیازی به ذخیره ندارند، بازسازی، استفاده و سپس حذف کند.

GNU Make نیز دارای چند ویژگی ساده است که بسیار راحت هستند. به عنوان مثال، گزینه فایل -o که می‌گوید «تظاهر کنید که فایل فایل منبع تغییر نکرده است، حتی اگر تغییر کرده باشد.» این زمانی که یک ماکرو جدید به یک فایل هدر اضافه می‌کنید بسیار مفید است. اکثر نسخه‌های Make فرض می‌کنند که باید تمام فایل‌های منبعی را که از فایل هدر استفاده می‌کنند، دوباره کامپایل کنند. اما GNU Make راهی برای جلوگیری از کامپایل مجدد در اختیار شما قرار می دهد، در صورتی که می دانید تغییر شما در فایل هدر به آن نیاز ندارد.
</div>
However, the most important difference between GNU Make and most versions of Make is that GNU Make is free software.

Makefiles And Conventions
We have developed conventions for how to write Makefiles, which all GNU packages ought to follow. It is a good idea to follow these conventions in your program even if you don't intend it to be GNU software, so that users will be able to build your package just like many other packages, and will not need to learn anything special before doing so.

These conventions are found in the chapter ``Makefile conventions'' (147 k characters) of the GNU Coding Standards (147 k characters).

Downloading Make
Make can be found on the main GNU ftp server: http://ftp.gnu.org/gnu/make/ (via HTTP) and ftp://ftp.gnu.org/gnu/make/ (via FTP). It can also be found on the GNU mirrors; please use a mirror if possible.

Documentation
Documentation for Make is available online, as is documentation for most GNU software. You may also find more information about Make by running info make or man make, or by looking at /usr/share/doc/make/, /usr/local/doc/make/, or similar directories on your system. A brief summary is available by running make --help.

Mailing lists
Make has the following mailing lists:

bug-make is used to discuss most aspects of Make, including development and enhancement requests, as well as bug reports.
help-make is for general user help and discussion.
Announcements about Make and most other GNU software are made on info-gnu (archive).

Security reports that should not be made immediately public can be sent directly to the maintainer. If there is no response to an urgent issue, you can escalate to the general security mailing list for advice.

Getting involved
Development of Make, and GNU in general, is a volunteer effort, and you can contribute. For information, please read How to help GNU. If you'd like to get involved, it's a good idea to join the discussion mailing list (see above).

Test releases
Trying the latest test release (when available) is always appreciated. Test releases of Make can be found at http://alpha.gnu.org/gnu/make/ (via HTTP) and ftp://alpha.gnu.org/gnu/make/ (via FTP).
Development
For development sources, issue trackers, and other information, please see the Make project page at savannah.gnu.org.
Translating Make
To translate Make's messages into other languages, please see the Translation Project page for Make. If you have a new translation of the message strings, or updates to the existing strings, please have the changes made in this repository. Only translations from this site will be incorporated into Make. For more information, see the Translation Project.
Maintainer
Make is currently being maintained by Paul Smith. Please use the mailing lists for contact.
Licensin
Make is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation; either version 3 of the License, or (at your option) any later version.
