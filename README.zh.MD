# TermuxUbuntuPRoot

> 🌐 [其他语言 / Other languages](README.md)

在 Termux 中使用 PRoot 安装 Ubuntu 的指南。

**注意：按照本指南操作无需设备 root 权限**

## 0 - 更新 Termux 软件包

```
pkg update && pkg upgrade -y
```

## 1 - 安装 PRoot

```
pkg install proot-distro -y
```

## 2 - 在 PRoot 中安装 `Ubuntu`

```
proot-distro install ubuntu
```

## 3 - 登录 `Ubuntu`

```
proot-distro login ubuntu
```

现在你已经以 **root** 用户身份进入了 Ubuntu。

## 4 - 更新 `Ubuntu` 系统软件包

```
apt update && apt upgrade -y
```

## 5 - 安装图形界面（可选）

### 使用 Termux:X11（推荐，性能更好）

1. 在 Android 上安装 Termux:X11 应用。
2. 在 Termux 中（PRoot 外部）安装支持组件：`pkg install x11-repo termux-x11-nightly`。
3. 在 Ubuntu 内部安装图形环境：`apt install xfce4 xfce4-goodies -y`。

### 使用 VNC

1. 在 Ubuntu 中安装：`apt install xfce4 tigervnc-standalone-server -y`。
2. 设置 VNC 密码并使用 `vncserver` 启动服务器，然后通过 VNC 客户端应用（如 AVNC 或 VNC Viewer）连接到地址 `127.0.0.1:5901`。

## PRoot-Distro 实用命令

- 退出 Ubuntu：输入 `exit`。
- 列出支持的发行版：`proot-distro list`。
- 备份你的 Ubuntu：在 Termux 中运行：`tar -zcvf ubuntu-backup.tar.gz -C $PREFIX/var/lib/proot-distro/installed-rootfs/ubuntu .`
