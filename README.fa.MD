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
