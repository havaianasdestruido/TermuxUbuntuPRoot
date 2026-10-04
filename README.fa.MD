# TermuxUbuntuPRoot

> 🌐 [زبان‌های دیگر / Other languages](README.md)

راهنمای نصب اوبونتو داخل Termux با استفاده از PRoot.

**توجه: برای دنبال کردن این راهنما نیازی به روت (root) در دستگاه خود ندارید**

## 0 - به‌روزرسانی بسته‌های Termux

```
pkg update && pkg upgrade -y
```

## 1 - نصب PRoot

```
pkg install proot-distro -y
```

## 2 - نصب `Ubuntu` داخل PRoot

```
proot-distro install ubuntu
```

## 3 - ورود به `Ubuntu`

```
proot-distro login ubuntu
```

اکنون شما با کاربر **root** داخل اوبونتو هستید.

## 4 - به‌روزرسانی بسته‌های سیستم `Ubuntu`

```
apt update && apt upgrade -y
```

## 5 - نصب رابط گرافیکی (اختیاری)

### با Termux:X11 (برای عملکرد بهتر توصیه می‌شود)

1. برنامه Termux:X11 را روی اندروید نصب کنید.
2. در Termux (خارج از PRoot)، بسته‌های پشتیبانی را نصب کنید: `pkg install x11-repo termux-x11-nightly`.
3. داخل اوبونتو، محیط گرافیکی را نصب کنید: `apt install xfce4 xfce4-goodies -y`.

### با VNC

1. در اوبونتو نصب کنید: `apt install xfce4 tigervnc-standalone-server -y`.
2. رمز عبور VNC را تنظیم کنید و سرور را با `vncserver` راه‌اندازی کنید، سپس با یک برنامه کلاینت VNC (مانند AVNC یا VNC Viewer) به آدرس `127.0.0.1:5901` متصل شوید.

## دستورات مفید PRoot-Distro

- خروج از اوبونتو: `exit` را تایپ کنید.
- فهرست توزیع‌های پشتیبانی‌شده: `proot-distro list`.
- پشتیبان‌گیری از اوبونتوی خود: در Termux اجرا کنید: `tar -zcvf ubuntu-backup.tar.gz -C $PREFIX/var/lib/proot-distro/installed-rootfs/ubuntu .`

## پرسش‌های متداول درباره Termux، اندروید و اوبونتو

این پرسش‌ها به جستجوهای اصلی Google Trends درباره **Termux**، مانند “termux android”، “android termux”، “termux download”، “apk termux”، “github termux”، “termux python” و “termux pc” پاسخ می‌دهند. همچنین [مقایسه Google Trends برای Termux](https://trends.google.com/trends/explore?date=all&q=Termux) را ببینید.

### Termux Android یا Android Termux چیست؟

Termux یک ترمینال و محیط Linux برای اندروید است. با آن می‌توانید ابزارهایی مانند Git، Python و SSH را روی گوشی اجرا کنید. این راهنما Termux را با PRoot ترکیب می‌کند تا Ubuntu را در فضای کاربر و بدون نیاز به دسترسی root دستگاه اجرا کنید.

### Termux را از کجا دانلود کنم و APK امن Termux را از کجا بگیرم؟

برای **Termux download** امن، از [مخزن رسمی Termux در GitHub](https://github.com/termux/termux-app) یا [F-Droid](https://f-droid.org/packages/com.termux/) استفاده کنید. این‌ها منابع پیشنهادی برای دریافت **Termux APK** هستند. از سایت‌های متفرقه‌ای که «termux apk download»، «download apk termux»، «download termux apk» یا «termux download apk» ارائه می‌کنند دوری کنید، چون فایل‌ها ممکن است قدیمی یا دستکاری‌شده باشند. نصب‌هایی را که از منابع مختلف گرفته‌اید با هم ترکیب نکنید.

### چگونه Ubuntu را بدون root در Termux نصب کنم؟

Termux را به‌روزرسانی کنید، `proot-distro` را نصب کنید، دستور `proot-distro install ubuntu` را اجرا کنید و با `proot-distro login ubuntu` وارد شوید. PRoot یک لایه سازگاری در فضای کاربر فراهم می‌کند و دسترسی root واقعی به اندروید نمی‌دهد.

### چگونه Python را در Termux یا Ubuntu نصب کنم؟

برای **Termux Python**، در Termux دستور `pkg update && pkg install python -y` را اجرا کنید. پس از ورود به Ubuntu، از `apt update && apt install python3 python3-pip -y` استفاده کنید. دستور مناسب به محیطی بستگی دارد که می‌خواهید Python را در آن نصب کنید.

### آیا Termux می‌تواند جایگزین PC شود؟

جستجوی **Termux PC** معمولاً به استفاده از گوشی اندرویدی به‌عنوان یک ایستگاه کاری سبک Linux اشاره دارد. Termux و Ubuntu با PRoot برای توسعه، خودکارسازی، Git و SSH مفید هستند، اما کاملاً جایگزین رایانه رومیزی نمی‌شوند و ممکن است محدودیت‌هایی در عملکرد، مجوزها و دسترسی به سخت‌افزار داشته باشند.

### GitHub رسمی Termux کدام است و جدیدترین نسخه را از کجا بگیرم؟

TermuxUbuntuPRoot یک راهنمای جامعه است. کد منبع و نسخه‌های رسمی برنامه در [termux/termux-app در GitHub](https://github.com/termux/termux-app) قرار دارند. برای جستجوهایی مانند **GitHub Termux**، **Termux GitHub**، **Termux Android 5** و **Termux latest version**، نیازمندی‌های فعلی و [نسخه‌های رسمی](https://github.com/termux/termux-app/releases) را بررسی کنید، نه سایت‌های APK. «Termex»، «Termax»، `termux indir`، `تیرمکس` و `термукс` نیز شکل‌های رایج جستجو هستند.
