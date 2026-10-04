# TermuxUbuntuPRoot

> 🌐 [Bahasa lainnya / Other languages](README.md)

Panduan cara menginstal Ubuntu di dalam Termux menggunakan PRoot.

**CATATAN: Anda tidak memerlukan root di perangkat Anda untuk mengikuti panduan ini**

## 0 - Perbarui paket Termux

```
pkg update && pkg upgrade -y
```

## 1 - Instal PRoot

```
pkg install proot-distro -y
```

## 2 - Instal `Ubuntu` di dalam PRoot

```
proot-distro install ubuntu
```

## 3 - Masuk ke `Ubuntu`

```
proot-distro login ubuntu
```

Sekarang Anda berada di dalam Ubuntu sebagai pengguna **root**.

## 4 - Perbarui paket sistem `Ubuntu`

```
apt update && apt upgrade -y
```

## 5 - Instal GUI (opsional)

### Dengan Termux:X11 (direkomendasikan untuk performa lebih baik)

1. Instal aplikasi Termux:X11 di Android.
2. Di Termux (di luar PRoot), instal paket pendukung: `pkg install x11-repo termux-x11-nightly`.
3. Di dalam Ubuntu, instal lingkungan grafis: `apt install xfce4 xfce4-goodies -y`.

### Dengan VNC

1. Di Ubuntu, instal: `apt install xfce4 tigervnc-standalone-server -y`.
2. Atur kata sandi VNC dan jalankan server dengan `vncserver`, lalu hubungkan menggunakan aplikasi klien VNC (seperti AVNC atau VNC Viewer) di alamat `127.0.0.1:5901`.

## Perintah PRoot-Distro yang Berguna

- Keluar dari Ubuntu: ketik `exit`.
- Melihat daftar distribusi yang didukung: `proot-distro list`.
- Mencadangkan Ubuntu Anda: jalankan di Termux: `tar -zcvf ubuntu-backup.tar.gz -C $PREFIX/var/lib/proot-distro/installed-rootfs/ubuntu .`
