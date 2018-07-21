# GitCheatSheet
Persian Git Commands and Best Practices Cheat Sheet

# General Commands
<div dir="rtl" align="right" >
 مشاهده و تغییر نام شخص به صورت سراسری جهت استفاده در پروژه های گیت :
</div>
git config —global user.name

<div dir="rtl" align="right" >
 مشاهده و تغییر ایمیل شخص به صورت سراسری جهت استفاده در پروژه های گیت :
</div>
git config —global user.email

<div dir="rtl" align="right" >
افزودن همه فایل ها به Stage :
</div>
git add -A
<div dir="rtl" align="right" >
حذف فایل از Stage :
</div>
git reset $FILENAME
<div dir="rtl" align="right" >
کامیت کردن فایل های درون Stage :
</div>
git commit -m “Commit Message"
<div dir="rtl" align="right" >
برگرداندن یک فایل به آخرین Commit :
</div>
git checkout — $FILENAME
<div dir="rtl" align="right" >
بررسی تغییرات فایل های فعلی با آخرین Commit :
</div>
git diff head

<div dir="rtl" align="right" >
بررسی تغیررات فایل های فعلی با فایل های داخل استیج :
</div>
git diff —staged
<div dir="rtl" align="right" >
فایل را هم از گیت و هم از روی هارد حذف می کند :
</div>
git rm $FILENAME
<div dir="rtl" align="right" >
تغییرات کامیت مورد نظر : 
</div>
git show $COMMITID 
<div dir="rtl" align="right" >
پیدا کردن مقصر ایجاد یک باگ که کل تغییرات یک فایل را بهمراه نام افراد تغییر دهنده لیست می کند :
</div>
git blame $FILENAME
<div dir="rtl" align="right" >
کلیه تغییرات روی یک خط خاص را لیست می کند :
</div>
git blame $FILENAME -L8

# Branches
<div dir="rtl" align="right" >
لیست Branch ها :
</div>
git branch
<div dir="rtl" align="right" >
ساخت Branch جدید :
</div>
git branch $BRANCHNAME
<div dir="rtl" align="right" >
حذف یک Branch :
</div>
git branch -d $BRANCHNAME
<div dir="rtl" align="right" >
سویچ به Branch دیگر :
</div>
git checkout $BRANCHNAME
<div dir="rtl" align="right" >
Merge برنچ فعلی با برنچ دیگر :
</div>
git merge $BRANCHNAME

# Remote Projects
<div dir="rtl" align="right" >
دانلود یک پروژه از گیت :
</div>
git clone URL
<div dir="rtl" align="right" >
دانلود تغیررات از وب به برنچ مستر :
</div>
git pull origin master
<div dir="rtl" align="right" >
آپلود تغییرات روی گیت :
</div>
git push -u origin master
<div dir="rtl" align="right" >
لیست سرور های خارجی قابل ارسال و دریافت تغییرات پروژه :
</div>
git remote -v
<div dir="rtl" align="right" >
افزودن یک سرور گیت به نام origin برای ارسال و دریافت تغییرات :
</div>
gir remote add origin $URL

# Tags
<div dir="rtl" align="right" >
نمایش لیست تگ ها :
</div>
git tag
<div dir="rtl" align="right" >
ایجاد یک تگ جدید بر روی آخرین کامیت پروژه :
</div>
git tag -a v2.0 -m “Second Version”
<div dir="rtl" align="right" >
ایجاد تگ جدید روی کامیت مورد نظر :
</div>
git tag -a v2.0  COMMITID -m “Second Version”
<div dir="rtl" align="right" >
نمایش کامیت تگ مورد نظر :
</div>
git show v2.0
<div dir="rtl" align="right" >
ارسال تگ ها به سرور گیت چون به صورت پیشفرض تگ ها ارسال نمی شوند :
</div>
git push origin —tags
<div dir="rtl" align="right" >
بردن پروژه به یک تگ مشخص : 
</div>
git checkout v2.0

# Bisect

<div dir="rtl" align="right" >
شروع عملیات پیدا کردن کامیتی که باعث باگ شده :
</div>
git bisect start
<div dir="rtl" align="right" >
وضعیت فعلی دارای باگ می باشد :
</div>
git bisect bad
<div dir="rtl" align="right" >
وضعیت در کامیت مورد نظر بدون باگ می باشد :
</div>
git bisect good COMMITID

<div dir="rtl" align="right" >
در قدم بعد روی کامیت ها جلو عقب می رود تا ما بعد از چک کردن بوسیله دستورات زیر بهش بگیم که باگ دارد یا خیر تا کامیت باعث باگ پیدا شود :
</div>
git bisect bad
git bisect good

# Signing with GPG

<div dir="rtl" align="right" >
نمایش کلید ها :
</div>
gpg —list-keys
<div dir="rtl" align="right" >
ساخت کلید جدید :
</div>
gpg —gen-key
<div dir="rtl" align="right" >
نمایش لیست کلید ها :
</div>
gpg —list-secret-keys —keyid-format LONG
<div dir="rtl" align="right" >
ثبت کلید خصوصی برای امضای تغییرات بر روی گیت :
</div>
git config —global user.signingkey $SECRETKEY
<div dir="rtl" align="right" >
امضای یک تگ :
</div>
git tag -s v2.0 -m “Second Tag”
<div dir="rtl" align="right" >
امضای یک کامیت :
</div>
git commit -S -m “Commit Message"