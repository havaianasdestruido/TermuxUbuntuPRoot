# TermuxUbuntuPRoot
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
