# TermuxUbuntuPRoot

> 🌐 [Other languages / Outros idiomas](README.md)

Guide on how to install Ubuntu inside Termux using PRoot.

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
