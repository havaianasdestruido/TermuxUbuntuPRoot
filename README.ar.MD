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

## الأسئلة الشائعة حول Termux وAndroid وUbuntu

تجيب هذه الأسئلة عن عمليات البحث الرئيسية في Google Trends حول **Termux**، مثل “termux android” و“android termux” و“termux download” و“apk termux” و“github termux” و“termux python” و“termux pc”. راجع أيضًا [مقارنة Google Trends الخاصة بـ Termux](https://trends.google.com/trends/explore?date=all&q=Termux).

### ما هو Termux Android أو Android Termux؟

Termux هو تطبيق طرفية وبيئة Linux لنظام Android. يتيح تشغيل أدوات مثل Git وPython وSSH على الهاتف. يجمع هذا الدليل بين Termux وPRoot لتشغيل Ubuntu في مساحة المستخدم من دون الحاجة إلى صلاحيات root على الجهاز.

### من أين يمكن تنزيل Termux والعثور على APK آمن؟

لتنزيل **Termux download** بأمان، استخدم [المستودع الرسمي لتطبيق Termux على GitHub](https://github.com/termux/termux-app) أو [F-Droid](https://f-droid.org/packages/com.termux/). هذان هما المصدران الموصى بهما للحصول على **Termux APK**. تجنّب المواقع الخارجية التي تعرض “termux apk download” أو “download apk termux” أو “download termux apk” أو “termux download apk”، فقد تكون الملفات قديمة أو معدّلة. لا تخلط بين عمليات التثبيت من مصادر مختلفة.

### كيف أثبّت Ubuntu داخل Termux من دون root؟

حدّث Termux، وثبّت `proot-distro`، ثم نفّذ `proot-distro install ubuntu` وسجّل الدخول باستخدام `proot-distro login ubuntu`. يوفر PRoot طبقة توافق في مساحة المستخدم، لكنه لا يمنح صلاحيات root حقيقية لنظام Android.

### كيف أثبّت Python في Termux أو Ubuntu؟

لتثبيت **Termux Python**، نفّذ الأمر `pkg update && pkg install python -y` داخل Termux. وبعد الدخول إلى Ubuntu، استخدم `apt update && apt install python3 python3-pip -y`. يعتمد الأمر المناسب على البيئة التي تريد تثبيت Python فيها.

### هل يمكن استخدام Termux كبديل عن الكمبيوتر؟

يشير البحث عن **Termux PC** عادةً إلى استخدام هاتف Android كمحطة عمل Linux خفيفة. يفيد Termux وUbuntu عبر PRoot في البرمجة النصية والأتمتة وGit وSSH، ولكنهما لا يستبدلان الكمبيوتر المكتبي بالكامل وقد توجد قيود على الأداء والصلاحيات والوصول إلى العتاد.

### ما هو GitHub الرسمي لـ Termux وكيف أحصل على أحدث إصدار؟

TermuxUbuntuPRoot هو دليل من المجتمع. يوجد المصدر والإصدارات الرسمية للتطبيق في [termux/termux-app على GitHub](https://github.com/termux/termux-app). عند البحث عن **GitHub Termux** أو **Termux GitHub** أو **Termux Android 5** أو **Termux latest version**، تحقّق من المتطلبات الحالية ومن [الإصدارات الرسمية](https://github.com/termux/termux-app/releases)، وليس من مواقع APK غير رسمية. وقد تظهر أيضًا صيغ بحث مثل `تحميل` و`تيرمكس` و`تنزيل termux` و`термукс` و`termux indir`.
