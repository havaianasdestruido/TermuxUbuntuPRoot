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
