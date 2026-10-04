# TermuxUbuntuPRoot: Install Ubuntu in Termux with PRoot

> 🌐 [Other languages / Outros idiomas](README.md)

A practical guide to install Ubuntu in Termux on Android using PRoot, without root access.

**NOTE: You don't need root on your device to follow this guide**

## 0 - Update Termux packages

```
pkg update && pkg upgrade -y
```

## 1 - Install PRoot

```
pkg install proot-distro -y
```

## 2 - Install `Ubuntu` inside PRoot

```
proot-distro install ubuntu
```

## 3 - Login into `Ubuntu`

```
proot-distro login ubuntu
```

Now you are into Ubuntu under the **root** user.

## 4 - Update `Ubuntu` system packages

```
apt update && apt upgrade -y
```

## 5 - Install a GUI (optional)

### With Termux:X11 (recommended for better performance)

1. Install the Termux:X11 app on Android.
2. In Termux (outside PRoot), install the support packages: `pkg install x11-repo termux-x11-nightly`.
3. Inside Ubuntu, install the graphical environment: `apt install xfce4 xfce4-goodies -y`.

### With VNC

1. In Ubuntu, install: `apt install xfce4 tigervnc-standalone-server -y`.
2. Set the VNC password and start the server with `vncserver`, then connect using a VNC client app (such as AVNC or VNC Viewer) at the address `127.0.0.1:5901`.

## Useful PRoot-Distro Commands

- Exit Ubuntu: type `exit`.
- List supported distributions: `proot-distro list`.
- Back up your Ubuntu: run in Termux: `tar -zcvf ubuntu-backup.tar.gz -C $PREFIX/var/lib/proot-distro/installed-rootfs/ubuntu .`

## Frequently asked questions about Termux, Android, and Ubuntu

These questions cover the main **Termux** search terms reported in the [Google Trends comparison for Termux](https://trends.google.com/trends/explore?date=all&q=Termux), including “termux android”, “android termux”, “apk termux”, “termux download”, “github termux”, “termux python”, and “termux pc”. The terms are included to answer real questions, not to encourage keyword stuffing.

### What is Termux Android, or Android Termux?

Termux is an Android terminal and Linux environment. It provides a package manager and a shell so you can run tools such as Git, Python, and SSH on Android. This guide combines Termux with PRoot to run an Ubuntu user space without requiring root access on the device.

### Where can I download Termux or get the Termux APK?

For a safe **Termux download**, use the [official Termux app repository on GitHub](https://github.com/termux/termux-app) or [F-Droid](https://f-droid.org/packages/com.termux/). Those are the recommended sources for the **Termux APK**. Avoid third-party “apk termux”, “termux apk download”, “download apk termux”, “download termux apk”, and “termux download apk” pages that may be outdated or modified. Do not combine installations from different sources.

### How do I install Ubuntu in Termux without root?

Run the commands in this guide in order: update Termux, install `proot-distro`, install Ubuntu, and log in with `proot-distro login ubuntu`. PRoot provides a user-space compatibility layer; it does not grant real root access to Android. See the step-by-step installation above.

### How do I install Python in Termux or Ubuntu?

For **Termux Python**, run `pkg update && pkg install python -y` in Termux. After logging into Ubuntu, use `apt update && apt install python3 python3-pip -y`. The correct command depends on whether you want **Python Termux** packages or packages inside the Ubuntu environment.

### Can Termux be used as a PC?

The query **Termux PC** usually means using an Android device as a lightweight Linux workstation. Termux and Ubuntu PRoot work well for command-line development, scripting, automation, Git, and SSH. They are not a complete replacement for a desktop PC and may have limits around performance, permissions, hardware access, and graphical applications.

### Is this the official GitHub Termux repository?

No. TermuxUbuntuPRoot is a community guide for installing Ubuntu in Termux. The official app source and releases are maintained in [termux/termux-app on GitHub](https://github.com/termux/termux-app). If you search for **GitHub Termux** or **Termux GitHub**, verify that the result points to that repository before downloading an APK.

### Does Termux work on Android 5, and what is the Termux latest version?

Support depends on the requirements of the specific official release. For **Termux Android 5**, check the current compatibility information before installing; older Android versions may not be supported by newer builds. For the **Termux latest version**, use the official [GitHub releases](https://github.com/termux/termux-app/releases) or [F-Droid listing](https://f-droid.org/packages/com.termux/) rather than an APK mirror.

### Why do people search for Termex, Termax, or other spellings?

**Termex** and **Termax** are common spelling variations. In Turkish, `termux indir` means “download Termux.” You may also see Arabic queries such as `تحميل`, `تيرمكس`, `termux تحميل`, `تحميل termux`, `تيرموكس`, `تريمكس`, `ترميكس`, `ترماكس`, `تنزيل termux`, and `التريمكس`, or Russian queries such as `термукс` and `термукс скачать`. These searches refer to the same Termux app, so the official GitHub and F-Droid links above remain the safest download sources.
