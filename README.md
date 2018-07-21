# GitCheatSheet
Persian Commands and Best Practices Cheat Sheet

# General Commands
<div dir="rtl" align="right" >
 مشاهده و تغییر نام شخص به صورت سراسری جهت استفاده در پروژه های گیت :
</div>

```bash
CyberGx@github:~$ git config —global user.name
```


<div dir="rtl" align="right" >
 مشاهده و تغییر ایمیل شخص به صورت سراسری جهت استفاده در پروژه های گیت :
</div>

```bash
CyberGx@github:~$ git config —global user.email
```

<div dir="rtl" align="right" >
افزودن همه فایل ها به Stage :
</div>

```bash
CyberGx@github:~$ git add -A
```
<div dir="rtl" align="right" >
حذف فایل از Stage :
</div>

```bash
CyberGx@github:~$ git reset $FILENAME
```
<div dir="rtl" align="right" >
کامیت کردن فایل های درون Stage :
</div>

```bash
CyberGx@github:~$ git commit -m "Commit Message"
```

<div dir="rtl" align="right" >
برگرداندن یک فایل به آخرین Commit :
</div>

```bash
CyberGx@github:~$ git checkout — $FILENAME
```
<div dir="rtl" align="right" >
بررسی تغییرات فایل های فعلی با آخرین Commit :
</div>

```bash
CyberGx@github:~$ git diff head
```

<div dir="rtl" align="right" >
بررسی تغیررات فایل های فعلی با فایل های داخل استیج :
</div>

```bash
CyberGx@github:~$ git diff —staged
```
<div dir="rtl" align="right" >
فایل را هم از گیت و هم از روی هارد حذف می کند :
</div>

```bash
CyberGx@github:~$ git rm $FILENAME
```
<div dir="rtl" align="right" >
تغییرات کامیت مورد نظر : 
</div>

```bash
CyberGx@github:~$ git show $COMMITID 
```
<div dir="rtl" align="right" >
پیدا کردن مقصر ایجاد یک باگ که کل تغییرات یک فایل را بهمراه نام افراد تغییر دهنده لیست می کند :
</div>

```bash
CyberGx@github:~$ git blame $FILENAME
```
<div dir="rtl" align="right" >
کلیه تغییرات روی یک خط خاص را لیست می کند :
</div>

```bash
CyberGx@github:~$ git blame $FILENAME -L8
```

# Branches
<div dir="rtl" align="right" >
لیست Branch ها :
</div>

```bash
CyberGx@github:~$ git branch
```
<div dir="rtl" align="right" >
ساخت Branch جدید :
</div>

```bash
CyberGx@github:~$ git branch $BRANCHNAME
```
<div dir="rtl" align="right" >
حذف یک Branch :
</div>

```bash
CyberGx@github:~$ git branch -d $BRANCHNAME
```
<div dir="rtl" align="right" >
سویچ به Branch دیگر :
</div>

```bash
CyberGx@github:~$ git checkout $BRANCHNAME
```
<div dir="rtl" align="right" >
Merge برنچ فعلی با برنچ دیگر :
</div>

```bash
CyberGx@github:~$ git merge $BRANCHNAME
```

# Remote Projects
<div dir="rtl" align="right" >
دانلود یک پروژه از گیت :
</div>

```bash
CyberGx@github:~$ git clone $URL
```
<div dir="rtl" align="right" >
دانلود تغیررات از وب به برنچ مستر :
</div>

```bash
CyberGx@github:~$ git pull origin master
```
<div dir="rtl" align="right" >
آپلود تغییرات روی گیت :
</div>

```bash
CyberGx@github:~$ git push -u origin master
```
<div dir="rtl" align="right" >
لیست سرور های خارجی قابل ارسال و دریافت تغییرات پروژه :
</div>

```bash
CyberGx@github:~$ git remote -v
```

<div dir="rtl" align="right" >
افزودن یک سرور گیت به نام origin برای ارسال و دریافت تغییرات :
</div>

```bash
CyberGx@github:~$ git remote add origin $URL
```

# Tags
<div dir="rtl" align="right" >
نمایش لیست تگ ها :
</div>

```bash
CyberGx@github:~$ git tag
```
<div dir="rtl" align="right" >
ایجاد یک تگ جدید بر روی آخرین کامیت پروژه :
</div>

```bash
CyberGx@github:~$ git tag -a v2.0 -m "Second Version"
```
<div dir="rtl" align="right" >
ایجاد تگ جدید روی کامیت مورد نظر :
</div>

```bash
CyberGx@github:~$ git tag -a v2.0 $COMMITID -m "Second Version"
```
<div dir="rtl" align="right" >
نمایش کامیت تگ مورد نظر :
</div>

```bash
CyberGx@github:~$ git show v2.0
```
<div dir="rtl" align="right" >
ارسال تگ ها به سرور گیت چون به صورت پیشفرض تگ ها ارسال نمی شوند :
</div>

```bash
CyberGx@github:~$ git push origin —tags
```
<div dir="rtl" align="right" >
بردن پروژه به یک تگ مشخص : 
</div>

```bash
CyberGx@github:~$ git checkout v2.0
```

# Bisect

<div dir="rtl" align="right" >
شروع عملیات پیدا کردن کامیتی که باعث باگ شده :
</div>

```bash
CyberGx@github:~$ git bisect start
```
<div dir="rtl" align="right" >
وضعیت فعلی دارای باگ می باشد :
</div>

```bash
CyberGx@github:~$ git bisect bad
```
<div dir="rtl" align="right" >
وضعیت در کامیت مورد نظر بدون باگ می باشد :
</div>

```bash
CyberGx@github:~$ git bisect good $COMMITID
```

<div dir="rtl" align="right" >
در قدم بعد روی کامیت ها جلو عقب می رود تا ما بعد از چک کردن بوسیله دستورات زیر بهش بگیم که باگ دارد یا خیر تا کامیت باعث باگ پیدا شود :
</div>

```bash
CyberGx@github:~$ git bisect bad
```

```bash
CyberGx@github:~$ git bisect good
```

# Signing with GPG

<div dir="rtl" align="right" >
نمایش کلید ها :
</div>

```bash
CyberGx@github:~$ gpg —list-keys
```

<div dir="rtl" align="right" >
ساخت کلید جدید :
</div>

```bash
CyberGx@github:~$ gpg —gen-key
```

<div dir="rtl" align="right" >
نمایش لیست کلید ها :
</div>

```bash
CyberGx@github:~$ gpg —list-secret-keys —keyid-format LONG
```

<div dir="rtl" align="right" >
ثبت کلید خصوصی برای امضای تغییرات بر روی گیت :
</div>

```bash
CyberGx@github:~$ git config —global user.signingkey $SECRETKEY
```

<div dir="rtl" align="right" >
امضای یک تگ :
</div>

```bash
CyberGx@github:~$ git tag -s v2.0 -m "Second Tag"
```
<div dir="rtl" align="right" >
امضای یک کامیت :
</div>

```bash
CyberGx@github:~$ git commit -S -m "Commit Message"
```