<style>
.persian-text {
    font-family: tahoma;
    font-size:.9em;
    direction: rtl;
    text-align: right;
}
</style>

# GitCheatSheet
Persian Git Commands and Best Practices Cheat Sheet

# General Commands
<div class="persian-text">
 مشاهده و تغییر نام شخص به صورت سراسری جهت استفاده در پروژه های گیت :
</div>
git config —global user.name

<div class="persian-text">
 مشاهده و تغییر ایمیل شخص به صورت سراسری جهت استفاده در پروژه های گیت :
</div>
git config —global user.email

<div class="persian-text">
افزودن همه فایل ها به Stage :
</div>
git add -A
<div class="persian-text">
حذف فایل از Stage :
</div>
git reset $FILENAME
<div class="persian-text">
کامیت کردن فایل های درون Stage :
</div>
git commit -m “Commit Message"
<div class="persian-text">
برگرداندن یک فایل به آخرین Commit :
</div>
git checkout — $FILENAME
<div class="persian-text">
بررسی تغییرات فایل های فعلی با آخرین Commit :
</div>
git diff head

<div class="persian-text">
بررسی تغیررات فایل های فعلی با فایل های داخل استیج :
</div>
git diff —staged
<div class="persian-text">
فایل را هم از گیت و هم از روی هارد حذف می کند :
</div>
git rm $FILENAME
<div class="persian-text">
تغییرات کامیت مورد نظر : 
</div>
git show $COMMITID 
<div class="persian-text">
پیدا کردن مقصر ایجاد یک باگ که کل تغییرات یک فایل را بهمراه نام افراد تغییر دهنده لیست می کند :
</div>
git blame $FILENAME
<div class="persian-text">
کلیه تغییرات روی یک خط خاص را لیست می کند :
</div>
git blame $FILENAME -L8

# Branches
<div class="persian-text">
لیست Branch ها :
</div>
git branch
<div class="persian-text">
ساخت Branch جدید :
</div>
git branch $BRANCHNAME
<div class="persian-text">
حذف یک Branch :
</div>
git branch -d $BRANCHNAME
<div class="persian-text">
سویچ به Branch دیگر :
</div>
git checkout $BRANCHNAME
<div class="persian-text">
Merge برنچ فعلی با برنچ دیگر :
</div>
git merge $BRANCHNAME

# Remote Projects
<div class="persian-text">
دانلود یک پروژه از گیت :
</div>
git clone URL
<div class="persian-text">
دانلود تغیررات از وب به برنچ مستر :
</div>
git pull origin master
<div class="persian-text">
آپلود تغییرات روی گیت :
</div>
git push -u origin master
<div class="persian-text">
لیست سرور های خارجی قابل ارسال و دریافت تغییرات پروژه :
</div>
git remote -v
<div class="persian-text">
افزودن یک سرور گیت به نام origin برای ارسال و دریافت تغییرات :
</div>
gir remote add origin $URL

# Tags
<div class="persian-text">
نمایش لیست تگ ها :
</div>
git tag
<div class="persian-text">
ایجاد یک تگ جدید بر روی آخرین کامیت پروژه :
</div>
git tag -a v2.0 -m “Second Version”
<div class="persian-text">
ایجاد تگ جدید روی کامیت مورد نظر :
</div>
git tag -a v2.0  COMMITID -m “Second Version”
<div class="persian-text">
نمایش کامیت تگ مورد نظر :
</div>
git show v2.0
<div class="persian-text">
ارسال تگ ها به سرور گیت چون به صورت پیشفرض تگ ها ارسال نمی شوند :
</div>
git push origin —tags
<div class="persian-text">
بردن پروژه به یک تگ مشخص : 
</div>
git checkout v2.0

# Bisect

<div class="persian-text">
شروع عملیات پیدا کردن کامیتی که باعث باگ شده :
</div>
git bisect start
<div class="persian-text">
وضعیت فعلی دارای باگ می باشد :
</div>
git bisect bad
<div class="persian-text">
وضعیت در کامیت مورد نظر بدون باگ می باشد :
</div>
git bisect good COMMITID

<div class="persian-text">
در قدم بعد روی کامیت ها جلو عقب می رود تا ما بعد از چک کردن بوسیله دستورات زیر بهش بگیم که باگ دارد یا خیر تا کامیت باعث باگ پیدا شود :
</div>
git bisect bad
git bisect good

# Signing with GPG

<div class="persian-text">
نمایش کلید ها :
</div>
gpg —list-keys
<div class="persian-text">
ساخت کلید جدید :
</div>
gpg —gen-key
<div class="persian-text">
نمایش لیست کلید ها :
</div>
gpg —list-secret-keys —keyid-format LONG
<div class="persian-text">
ثبت کلید خصوصی برای امضای تغییرات بر روی گیت :
</div>
git config —global user.signingkey $SECRETKEY
<div class="persian-text">
امضای یک تگ :
</div>
git tag -s v2.0 -m “Second Tag”
<div class="persian-text">
امضای یک کامیت :
</div>
git commit -S -m “Commit Message"