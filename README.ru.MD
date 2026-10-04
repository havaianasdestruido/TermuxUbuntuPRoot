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

## Часто задаваемые вопросы о Termux, Android и Ubuntu

Эти вопросы отвечают на основные запросы Google Trends о **Termux**, включая «termux android», «android termux», «termux download», «apk termux», «github termux», «termux python» и «termux pc». Смотрите также [сравнение Google Trends для Termux](https://trends.google.com/trends/explore?date=all&q=Termux).

### Что такое Termux Android или Android Termux?

Termux — это терминал и среда Linux для Android. В ней можно запускать Git, Python и SSH на телефоне. Это руководство использует Termux и PRoot, чтобы запустить Ubuntu в пользовательском пространстве без root-доступа к устройству.

### Где скачать Termux и найти безопасный APK Termux?

Для безопасной загрузки **Termux download** используйте [официальный репозиторий Termux на GitHub](https://github.com/termux/termux-app) или [F-Droid](https://f-droid.org/packages/com.termux/). Это рекомендуемые источники **APK Termux**. Избегайте сторонних сайтов с запросами «termux apk download», «download apk termux», «download termux apk» или «termux download apk»: файлы могут быть изменены или устареть. Не смешивайте установки из разных источников.

### Как установить Ubuntu в Termux без root?

Обновите Termux, установите `proot-distro`, выполните `proot-distro install ubuntu`, затем войдите командой `proot-distro login ubuntu`. PRoot предоставляет слой совместимости в пользовательском пространстве и не даёт настоящего root-доступа к Android.

### Как установить Python в Termux или Ubuntu?

Для **Termux Python** выполните в Termux команду `pkg update && pkg install python -y`. В Ubuntu используйте `apt update && apt install python3 python3-pip -y`. Команда зависит от среды, в которой вы хотите установить Python.

### Может ли Termux заменить ПК?

Запрос **Termux PC** обычно означает использование телефона Android как лёгкой Linux-рабочей станции. Termux и Ubuntu через PRoot подходят для разработки, автоматизации, Git и SSH, но не полностью заменяют настольный ПК и могут иметь ограничения по производительности, разрешениям и доступу к оборудованию.

### Какой GitHub является официальным для Termux и где найти последнюю версию?

TermuxUbuntuPRoot — это руководство сообщества. Официальный исходный код и релизы приложения находятся в репозитории [termux/termux-app на GitHub](https://github.com/termux/termux-app). Для запросов **GitHub Termux**, **Termux GitHub**, **Termux Android 5** и **Termux latest version** проверяйте актуальные требования и [официальные релизы](https://github.com/termux/termux-app/releases), а не сайты с APK. «Termex», «Termax», `termux indir`, `تيرمكس` и `термукс` — распространённые варианты поиска.
