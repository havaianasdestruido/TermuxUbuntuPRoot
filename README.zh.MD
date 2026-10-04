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

## Termux、Android 和 Ubuntu 常见问题

以下内容回答 Google Trends 中关于 **Termux** 的主要搜索，例如“termux android”、“android termux”、“termux download”、“apk termux”、“github termux”、“termux python”和“termux pc”。也可以查看 [Termux 的 Google Trends 对比](https://trends.google.com/trends/explore?date=all&q=Termux)。

### 什么是 Termux Android 或 Android Termux？

Termux 是 Android 上的终端和 Linux 环境，可以在手机上运行 Git、Python 和 SSH 等工具。本指南将 Termux 与 PRoot 结合，在不需要设备 root 权限的情况下于用户空间运行 Ubuntu。

### 从哪里下载 Termux，如何获取安全的 Termux APK？

如需安全地进行 **Termux download**，请使用 [GitHub 上的 Termux 官方仓库](https://github.com/termux/termux-app) 或 [F-Droid](https://f-droid.org/packages/com.termux/)。这些是获取 **Termux APK** 的推荐来源。请避免使用提供“termux apk download”、“download apk termux”、“download termux apk”或“termux download apk”的第三方网站，因为文件可能已过时或被修改。不要混用来自不同来源的安装包。

### 如何在没有 root 的情况下将 Ubuntu 安装到 Termux？

更新 Termux，安装 `proot-distro`，运行 `proot-distro install ubuntu`，然后使用 `proot-distro login ubuntu` 登录。PRoot 只在用户空间提供兼容层，不会为 Android 提供真正的 root 权限。

### 如何在 Termux 或 Ubuntu 中安装 Python？

如需 **Termux Python**，请在 Termux 中运行 `pkg update && pkg install python -y`。进入 Ubuntu 后，运行 `apt update && apt install python3 python3-pip -y`。具体命令取决于你要在哪个环境中安装 Python。

### Termux 可以替代 PC 吗？

**Termux PC** 通常表示将 Android 手机作为轻量级 Linux 工作站使用。Termux 和 PRoot 中的 Ubuntu 适合开发、自动化、Git 和 SSH，但不能完全替代桌面 PC，并且在性能、权限和硬件访问方面可能存在限制。

### Termux 官方 GitHub 是哪个，如何获取最新版本？

TermuxUbuntuPRoot 是社区维护的指南。应用的官方源代码和版本发布位于 [GitHub 的 termux/termux-app](https://github.com/termux/termux-app)。对于 **GitHub Termux**、**Termux GitHub**、**Termux Android 5** 和 **Termux latest version** 等搜索，请查看当前要求和[官方版本](https://github.com/termux/termux-app/releases)，不要使用 APK 镜像站。“Termex”、“Termax”、`termux indir`、`تيرمكس` 和 `термукс` 也是常见的搜索变体。
