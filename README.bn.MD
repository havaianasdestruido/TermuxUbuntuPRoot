# TermuxUbuntuPRoot

> 🌐 [অন্যান্য ভাষা / Other languages](README.md)

PRoot ব্যবহার করে Termux-এর ভিতরে Ubuntu ইনস্টল করার গাইড।

**দ্রষ্টব্য: এই গাইড অনুসরণ করতে আপনার ডিভাইসে root-এর প্রয়োজন নেই**

## 0 - Termux প্যাকেজ আপডেট করুন

```
pkg update && pkg upgrade -y
```

## 1 - PRoot ইনস্টল করুন

```
pkg install proot-distro -y
```

## 2 - PRoot-এর ভিতরে `Ubuntu` ইনস্টল করুন

```
proot-distro install ubuntu
```

## 3 - `Ubuntu`-তে লগইন করুন

```
proot-distro login ubuntu
```

এখন আপনি **root** ব্যবহারকারী হিসেবে Ubuntu-এর ভিতরে আছেন।

## 4 - `Ubuntu` সিস্টেম প্যাকেজ আপডেট করুন

```
apt update && apt upgrade -y
```

## 5 - GUI ইনস্টল করুন (ঐচ্ছিক)

### Termux:X11 দিয়ে (ভালো পারফরম্যান্সের জন্য প্রস্তাবিত)

1. Android-এ Termux:X11 অ্যাপ ইনস্টল করুন।
2. Termux-এ (PRoot-এর বাইরে), সাপোর্ট প্যাকেজ ইনস্টল করুন: `pkg install x11-repo termux-x11-nightly`।
3. Ubuntu-এর ভিতরে, গ্রাফিক্যাল এনভায়রনমেন্ট ইনস্টল করুন: `apt install xfce4 xfce4-goodies -y`।

### VNC দিয়ে

1. Ubuntu-তে ইনস্টল করুন: `apt install xfce4 tigervnc-standalone-server -y`।
2. VNC পাসওয়ার্ড সেট করুন এবং `vncserver` দিয়ে সার্ভার চালু করুন, তারপর একটি VNC ক্লায়েন্ট অ্যাপ (যেমন AVNC বা VNC Viewer) দিয়ে `127.0.0.1:5901` ঠিকানায় সংযোগ করুন।

## PRoot-Distro-এর দরকারী কমান্ড

- Ubuntu থেকে বের হতে: `exit` টাইপ করুন।
- সমর্থিত ডিস্ট্রিবিউশনের তালিকা দেখতে: `proot-distro list`।
- আপনার Ubuntu-এর ব্যাকআপ নিতে: Termux-এ চালান: `tar -zcvf ubuntu-backup.tar.gz -C $PREFIX/var/lib/proot-distro/installed-rootfs/ubuntu .`

## Termux, Android এবং Ubuntu সম্পর্কে সাধারণ প্রশ্ন

এই প্রশ্নগুলো **Termux** নিয়ে Google Trends-এর প্রধান অনুসন্ধানগুলোর উত্তর দেয়, যেমন “termux android”, “android termux”, “termux download”, “apk termux”, “github termux”, “termux python” এবং “termux pc”। [Termux-এর Google Trends তুলনাটিও](https://trends.google.com/trends/explore?date=all&q=Termux) দেখুন।

### Termux Android বা Android Termux কী?

Termux হলো Android-এর জন্য একটি টার্মিনাল এবং Linux পরিবেশ। এর মাধ্যমে ফোনে Git, Python এবং SSH-এর মতো টুল চালানো যায়। এই গাইডে Termux-এর সঙ্গে PRoot ব্যবহার করে ডিভাইসে root ছাড়াই user space-এ Ubuntu চালানো হয়।

### কোথা থেকে Termux ডাউনলোড করব এবং নিরাপদ Termux APK কোথায় পাব?

নিরাপদ **Termux download**-এর জন্য [GitHub-এর অফিসিয়াল Termux repository](https://github.com/termux/termux-app) অথবা [F-Droid](https://f-droid.org/packages/com.termux/) ব্যবহার করুন। **Termux APK**-এর জন্য এগুলোই প্রস্তাবিত উৎস। “termux apk download”, “download apk termux”, “download termux apk” অথবা “termux download apk” দেওয়া তৃতীয় পক্ষের সাইট এড়িয়ে চলুন, কারণ ফাইল পুরোনো বা পরিবর্তিত হতে পারে। বিভিন্ন উৎসের ইনস্টলেশন একসঙ্গে ব্যবহার করবেন না।

### Root ছাড়া Termux-এ Ubuntu কীভাবে ইনস্টল করব?

Termux আপডেট করুন, `proot-distro` ইনস্টল করুন, `proot-distro install ubuntu` চালান এবং `proot-distro login ubuntu` দিয়ে প্রবেশ করুন। PRoot user space-এ compatibility layer দেয়; এটি Android-এ প্রকৃত root access দেয় না।

### Termux বা Ubuntu-তে Python কীভাবে ইনস্টল করব?

**Termux Python**-এর জন্য Termux-এ `pkg update && pkg install python -y` চালান। Ubuntu-এর ভিতরে `apt update && apt install python3 python3-pip -y` ব্যবহার করুন। Python কোন পরিবেশে ইনস্টল করবেন তার ওপর সঠিক কমান্ড নির্ভর করে।

### Termux কি PC-এর বিকল্প হতে পারে?

**Termux PC** অনুসন্ধানটি সাধারণত Android ফোনকে হালকা Linux workstation হিসেবে ব্যবহার করাকে বোঝায়। Termux এবং PRoot-এর Ubuntu development, automation, Git এবং SSH-এর জন্য উপযোগী, কিন্তু এগুলো পুরোপুরি desktop PC-এর বিকল্প নয় এবং performance, permission ও hardware access-এ সীমাবদ্ধতা থাকতে পারে।

### অফিসিয়াল Termux GitHub কোনটি এবং সর্বশেষ সংস্করণ কীভাবে পাব?

TermuxUbuntuPRoot একটি community guide। অ্যাপের অফিসিয়াল source ও release [GitHub-এর termux/termux-app](https://github.com/termux/termux-app)-এ রয়েছে। **GitHub Termux**, **Termux GitHub**, **Termux Android 5** এবং **Termux latest version** অনুসন্ধানের সময় বর্তমান requirements ও [অফিসিয়াল release](https://github.com/termux/termux-app/releases) যাচাই করুন, APK mirror নয়। “Termex”, “Termax”, `termux indir`, `تيرمكس` এবং `термукс`-ও প্রচলিত search variant।
