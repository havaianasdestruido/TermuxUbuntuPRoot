# TermuxUbuntuPRoot

> 🌐 [Diğer diller / Other languages](README.md)

PRoot kullanarak Termux içine Ubuntu kurma rehberi.

**NOT: Bu rehberi takip etmek için cihazınızda root gerekmez**

## 0 - Termux paketlerini güncelleyin

```
pkg update && pkg upgrade -y
```

## 1 - PRoot'u kurun

```
pkg install proot-distro -y
```

## 2 - PRoot içine `Ubuntu` kurun

```
proot-distro install ubuntu
```

## 3 - `Ubuntu`'ya giriş yapın

```
proot-distro login ubuntu
```

Artık **root** kullanıcısı olarak Ubuntu içindesiniz.

## 4 - `Ubuntu` sistem paketlerini güncelleyin

```
apt update && apt upgrade -y
```

## 5 - Grafik arayüz kurun (isteğe bağlı)

### Termux:X11 ile (daha iyi performans için önerilir)

1. Android'e Termux:X11 uygulamasını kurun.
2. Termux'ta (PRoot dışında) destek paketlerini kurun: `pkg install x11-repo termux-x11-nightly`.
3. Ubuntu içinde grafik ortamını kurun: `apt install xfce4 xfce4-goodies -y`.

### VNC ile

1. Ubuntu'da kurun: `apt install xfce4 tigervnc-standalone-server -y`.
2. VNC parolasını ayarlayın ve sunucuyu `vncserver` ile başlatın, ardından bir VNC istemci uygulamasıyla (AVNC veya VNC Viewer gibi) `127.0.0.1:5901` adresine bağlanın.

## Faydalı PRoot-Distro Komutları

- Ubuntu'dan çıkmak: `exit` yazın.
- Desteklenen dağıtımları listelemek: `proot-distro list`.
- Ubuntu'nuzu yedeklemek: Termux'ta çalıştırın: `tar -zcvf ubuntu-backup.tar.gz -C $PREFIX/var/lib/proot-distro/installed-rootfs/ubuntu .`
