# GitCheatSheet
Persian Git Commands and Best Practices Cheat Sheet

# General Commands
<div align="right" dir="rtl">
 مشاهده و تغییر نام شخص به صورت سراسری جهت استفاده در پروژه های گیت :
</div>
git config —global user.name

<div align="right" dir="rtl">
 مشاهده و تغییر ایمیل شخص به صورت سراسری جهت استفاده در پروژه های گیت :
</div>
git config —global user.email

<div align="right" dir="rtl">
افزودن همه فایل ها به Stage :
</div>
git add -A
<div align="right" dir="rtl">
حذف فایل از Stage :
</div>
git reset $FILENAME
<div align="right" dir="rtl">
کامیت کردن فایل های درون Stage :
</div>
git commit -m “Commit Message"
<div align="right" dir="rtl">
برگرداندن یک فایل به آخرین Commit :
</div>
git checkout — $FILENAME
<div align="right" dir="rtl">
بررسی تغییرات فایل های فعلی با آخرین Commit :
</div>
git diff head

<div align="right" dir="rtl">
بررسی تغیررات فایل های فعلی با فایل های داخل استیج :
</div>
git diff —staged
<div align="right" dir="rtl">
فایل را هم از گیت و هم از روی هارد حذف می کند :
</div>
git rm $FILENAME
<div align="right" dir="rtl">
تغییرات کامیت مورد نظر : 
</div>
git show $COMMITID 
<div align="right" dir="rtl">
پیدا کردن مقصر ایجاد یک باگ که کل تغییرات یک فایل را بهمراه نام افراد تغییر دهنده لیست می کند :
</div>
git blame $FILENAME
<div align="right" dir="rtl">
کلیه تغییرات روی یک خط خاص را لیست می کند :
</div>
git blame $FILENAME -L8

# Branches
<div align="right" dir="rtl">
لیست Branch ها :
</div>
git branch
<div align="right" dir="rtl">
ساخت Branch جدید :
</div>
git branch $BRANCHNAME
<div align="right" dir="rtl">
حذف یک Branch :
</div>
git branch -d $BRANCHNAME
<div align="right" dir="rtl">
سویچ به Branch دیگر :
</div>
git checkout $BRANCHNAME
<div align="right" dir="rtl">
Merge برنچ فعلی با برنچ دیگر :
</div>
git merge $BRANCHNAME

# Remote Projects
<div align="right" dir="rtl">
دانلود یک پروژه از گیت :
</div>
git clone URL
<div align="right" dir="rtl">
دانلود تغیررات از وب به برنچ مستر :
</div>
git pull origin master
<div align="right" dir="rtl">
آپلود تغییرات روی گیت :
</div>
git push -u origin master
<div align="right" dir="rtl">
لیست سرور های خارجی قابل ارسال و دریافت تغییرات پروژه :
</div>
git remote -v
<div align="right" dir="rtl">
افزودن یک سرور گیت به نام origin برای ارسال و دریافت تغییرات :
</div>
gir remote add origin $URL

# Tags
<div align="right" dir="rtl">
نمایش لیست تگ ها :
</div>
git tag
<div align="right" dir="rtl">
ایجاد یک تگ جدید بر روی آخرین کامیت پروژه :
</div>
git tag -a v2.0 -m “Second Version”
<div align="right" dir="rtl">
ایجاد تگ جدید روی کامیت مورد نظر :
</div>
git tag -a v2.0  COMMITID -m “Second Version”
<div align="right" dir="rtl">
نمایش کامیت تگ مورد نظر :
</div>
git show v2.0
<div align="right" dir="rtl">
ارسال تگ ها به سرور گیت چون به صورت پیشفرض تگ ها ارسال نمی شوند :
</div>
git push origin —tags
<div align="right" dir="rtl">
بردن پروژه به یک تگ مشخص : 
</div>
git checkout v2.0

# Bisect

<div align="right" dir="rtl">
شروع عملیات پیدا کردن کامیتی که باعث باگ شده :
</div>
git bisect start
<div align="right" dir="rtl">
وضعیت فعلی دارای باگ می باشد :
</div>
git bisect bad
<div align="right" dir="rtl">
وضعیت در کامیت مورد نظر بدون باگ می باشد :
</div>
git bisect good COMMITID

<div align="right" dir="rtl">
در قدم بعد روی کامیت ها جلو عقب می رود تا ما بعد از چک کردن بوسیله دستورات زیر بهش بگیم که باگ دارد یا خیر تا کامیت باعث باگ پیدا شود :
</div>
git bisect bad
git bisect good

# Signing with GPG

<div align="right" dir="rtl">
نمایش کلید ها :
</div>
gpg —list-keys
<div align="right" dir="rtl">
ساخت کلید جدید :
</div>
gpg —gen-key
<div align="right" dir="rtl">
نمایش لیست کلید ها :
</div>
gpg —list-secret-keys —keyid-format LONG
<div align="right" dir="rtl">
ثبت کلید خصوصی برای امضای تغییرات بر روی گیت :
</div>
git config —global user.signingkey $SECRETKEY
<div align="right" dir="rtl">
امضای یک تگ :
</div>
git tag -s v2.0 -m “Second Tag”
<div align="right" dir="rtl">
امضای یک کامیت :
</div>
git commit -S -m “Commit Message"