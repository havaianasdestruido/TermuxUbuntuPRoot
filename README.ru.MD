# TermuxUbuntuPRoot

> 🌐 [Другие языки / Other languages](README.md)

Руководство по установке Ubuntu внутри Termux с помощью PRoot.

**ПРИМЕЧАНИЕ: Для выполнения этого руководства root-доступ на устройстве не требуется**

## 0 - Обновите пакеты Termux

```
pkg update && pkg upgrade -y
```

## 1 - Установите PRoot

```
pkg install proot-distro -y
```

## 2 - Установите `Ubuntu` внутри PRoot

```
proot-distro install ubuntu
```

## 3 - Войдите в `Ubuntu`

```
proot-distro login ubuntu
```

Теперь вы находитесь в Ubuntu под пользователем **root**.

## 4 - Обновите системные пакеты `Ubuntu`

```
apt update && apt upgrade -y
```

## 5 - Установите графический интерфейс (необязательно)

### С Termux:X11 (рекомендуется для лучшей производительности)

1. Установите приложение Termux:X11 на Android.
2. В Termux (вне PRoot) установите поддержку: `pkg install x11-repo termux-x11-nightly`.
3. Внутри Ubuntu установите графическую среду: `apt install xfce4 xfce4-goodies -y`.

### С VNC

1. В Ubuntu установите: `apt install xfce4 tigervnc-standalone-server -y`.
2. Задайте пароль VNC и запустите сервер командой `vncserver`, затем подключитесь через клиентское VNC-приложение (например, AVNC или VNC Viewer) по адресу `127.0.0.1:5901`.

## Полезные команды PRoot-Distro

- Выйти из Ubuntu: введите `exit`.
- Показать список поддерживаемых дистрибутивов: `proot-distro list`.
- Создать резервную копию вашей Ubuntu: выполните в Termux: `tar -zcvf ubuntu-backup.tar.gz -C $PREFIX/var/lib/proot-distro/installed-rootfs/ubuntu .`
