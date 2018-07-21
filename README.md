# GitCheatSheet
Persian Git Commands and Best Practices Cheat Sheet

# General Commands
<div dir="rtl" align="right" ><font face="tahoma" size="2">
 مشاهده و تغییر نام شخص به صورت سراسری جهت استفاده در پروژه های گیت :
</font></div>
git config —global user.name

<div dir="rtl" align="right" ><font face="tahoma" size="2">
 مشاهده و تغییر ایمیل شخص به صورت سراسری جهت استفاده در پروژه های گیت :
</font></div>
git config —global user.email

<div dir="rtl" align="right" ><font face="tahoma" size="2">
افزودن همه فایل ها به Stage :
</font></div>
git add -A
<div dir="rtl" align="right" ><font face="tahoma" size="2">
حذف فایل از Stage :
</font></div>
git reset $FILENAME
<div dir="rtl" align="right" ><font face="tahoma" size="2">
کامیت کردن فایل های درون Stage :
</font></div>
git commit -m “Commit Message"
<div dir="rtl" align="right" ><font face="tahoma" size="2">
برگرداندن یک فایل به آخرین Commit :
</font></div>
git checkout — $FILENAME
<div dir="rtl" align="right" ><font face="tahoma" size="2">
بررسی تغییرات فایل های فعلی با آخرین Commit :
</font></div>
git diff head

<div dir="rtl" align="right" ><font face="tahoma" size="2">
بررسی تغیررات فایل های فعلی با فایل های داخل استیج :
</font></div>
git diff —staged
<div dir="rtl" align="right" ><font face="tahoma" size="2">
فایل را هم از گیت و هم از روی هارد حذف می کند :
</font></div>
git rm $FILENAME
<div dir="rtl" align="right" ><font face="tahoma" size="2">
تغییرات کامیت مورد نظر : 
</font></div>
git show $COMMITID 
<div dir="rtl" align="right" ><font face="tahoma" size="2">
پیدا کردن مقصر ایجاد یک باگ که کل تغییرات یک فایل را بهمراه نام افراد تغییر دهنده لیست می کند :
</font></div>
git blame $FILENAME
<div dir="rtl" align="right" ><font face="tahoma" size="2">
کلیه تغییرات روی یک خط خاص را لیست می کند :
</font></div>
git blame $FILENAME -L8

# Branches
<div dir="rtl" align="right" ><font face="tahoma" size="2">
لیست Branch ها :
</font></div>
git branch
<div dir="rtl" align="right" ><font face="tahoma" size="2">
ساخت Branch جدید :
</font></div>
git branch $BRANCHNAME
<div dir="rtl" align="right" ><font face="tahoma" size="2">
حذف یک Branch :
</font></div>
git branch -d $BRANCHNAME
<div dir="rtl" align="right" ><font face="tahoma" size="2">
سویچ به Branch دیگر :
</font></div>
git checkout $BRANCHNAME
<div dir="rtl" align="right" ><font face="tahoma" size="2">
Merge برنچ فعلی با برنچ دیگر :
</font></div>
git merge $BRANCHNAME

# Remote Projects
<div dir="rtl" align="right" ><font face="tahoma" size="2">
دانلود یک پروژه از گیت :
</font></div>
git clone URL
<div dir="rtl" align="right" ><font face="tahoma" size="2">
دانلود تغیررات از وب به برنچ مستر :
</font></div>
git pull origin master
<div dir="rtl" align="right" ><font face="tahoma" size="2">
آپلود تغییرات روی گیت :
</font></div>
git push -u origin master
<div dir="rtl" align="right" ><font face="tahoma" size="2">
لیست سرور های خارجی قابل ارسال و دریافت تغییرات پروژه :
</font></div>
git remote -v
<div dir="rtl" align="right" ><font face="tahoma" size="2">
افزودن یک سرور گیت به نام origin برای ارسال و دریافت تغییرات :
</font></div>
gir remote add origin $URL

# Tags
<div dir="rtl" align="right" ><font face="tahoma" size="2">
نمایش لیست تگ ها :
</font></div>
git tag
<div dir="rtl" align="right" ><font face="tahoma" size="2">
ایجاد یک تگ جدید بر روی آخرین کامیت پروژه :
</font></div>
git tag -a v2.0 -m “Second Version”
<div dir="rtl" align="right" ><font face="tahoma" size="2">
ایجاد تگ جدید روی کامیت مورد نظر :
</font></div>
git tag -a v2.0  COMMITID -m “Second Version”
<div dir="rtl" align="right" ><font face="tahoma" size="2">
نمایش کامیت تگ مورد نظر :
</font></div>
git show v2.0
<div dir="rtl" align="right" ><font face="tahoma" size="2">
ارسال تگ ها به سرور گیت چون به صورت پیشفرض تگ ها ارسال نمی شوند :
</font></div>
git push origin —tags
<div dir="rtl" align="right" ><font face="tahoma" size="2">
بردن پروژه به یک تگ مشخص : 
</font></div>
git checkout v2.0

# Bisect

<div dir="rtl" align="right" ><font face="tahoma" size="2">
شروع عملیات پیدا کردن کامیتی که باعث باگ شده :
</font></div>
git bisect start
<div dir="rtl" align="right" ><font face="tahoma" size="2">
وضعیت فعلی دارای باگ می باشد :
</font></div>
git bisect bad
<div dir="rtl" align="right" ><font face="tahoma" size="2">
وضعیت در کامیت مورد نظر بدون باگ می باشد :
</font></div>
git bisect good COMMITID

<div dir="rtl" align="right" ><font face="tahoma" size="2">
در قدم بعد روی کامیت ها جلو عقب می رود تا ما بعد از چک کردن بوسیله دستورات زیر بهش بگیم که باگ دارد یا خیر تا کامیت باعث باگ پیدا شود :
</font></div>
git bisect bad
git bisect good

# Signing with GPG

<div dir="rtl" align="right" ><font face="tahoma" size="2">
نمایش کلید ها :
</font></div>
gpg —list-keys
<div dir="rtl" align="right" ><font face="tahoma" size="2">
ساخت کلید جدید :
</font></div>
gpg —gen-key
<div dir="rtl" align="right" ><font face="tahoma" size="2">
نمایش لیست کلید ها :
</font></div>
gpg —list-secret-keys —keyid-format LONG
<div dir="rtl" align="right" ><font face="tahoma" size="2">
ثبت کلید خصوصی برای امضای تغییرات بر روی گیت :
</font></div>
git config —global user.signingkey $SECRETKEY
<div dir="rtl" align="right" ><font face="tahoma" size="2">
امضای یک تگ :
</font></div>
git tag -s v2.0 -m “Second Tag”
<div dir="rtl" align="right" ><font face="tahoma" size="2">
امضای یک کامیت :
</font></div>
git commit -S -m “Commit Message"