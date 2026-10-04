# TermuxUbuntuPRoot

> 🌐 [لغات أخرى / Other languages](README.md)

دليل تثبيت أوبونتو داخل Termux باستخدام PRoot.

**ملاحظة: لا تحتاج إلى صلاحيات روت (root) على جهازك لاتباع هذا الدليل**

## 0 - تحديث حزم Termux

```
pkg update && pkg upgrade -y
```

## 1 - تثبيت PRoot

```
pkg install proot-distro -y
```

## 2 - تثبيت `Ubuntu` داخل PRoot

```
proot-distro install ubuntu
```

## 3 - تسجيل الدخول إلى `Ubuntu`

```
proot-distro login ubuntu
```

الآن أنت داخل أوبونتو بالمستخدم **root**.

## 4 - تحديث حزم نظام `Ubuntu`

```
apt update && apt upgrade -y
```

## 5 - تثبيت واجهة رسومية (اختياري)

### باستخدام Termux:X11 (موصى به لأداء أفضل)

1. ثبّت تطبيق Termux:X11 على أندرويد.
2. في Termux (خارج PRoot)، ثبّت حزم الدعم: `pkg install x11-repo termux-x11-nightly`.
3. داخل أوبونتو، ثبّت البيئة الرسومية: `apt install xfce4 xfce4-goodies -y`.

### باستخدام VNC

1. في أوبونتو، ثبّت: `apt install xfce4 tigervnc-standalone-server -y`.
2. عيّن كلمة مرور VNC وشغّل الخادم بالأمر `vncserver`، ثم اتصل عبر تطبيق عميل VNC (مثل AVNC أو VNC Viewer) على العنوان `127.0.0.1:5901`.

## أوامر مفيدة لـ PRoot-Distro

- الخروج من أوبونتو: اكتب `exit`.
- عرض التوزيعات المدعومة: `proot-distro list`.
- عمل نسخة احتياطية من أوبونتو: نفّذ في Termux: `tar -zcvf ubuntu-backup.tar.gz -C $PREFIX/var/lib/proot-distro/installed-rootfs/ubuntu .`
