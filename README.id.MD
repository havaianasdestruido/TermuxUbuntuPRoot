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

## Pertanyaan umum tentang Termux, Android, dan Ubuntu

Pertanyaan berikut menjawab pencarian Google Trends utama tentang **Termux**, termasuk “termux android”, “android termux”, “termux download”, “apk termux”, “github termux”, “termux python”, dan “termux pc”. Lihat juga [perbandingan Google Trends untuk Termux](https://trends.google.com/trends/explore?date=all&q=Termux).

### Apa itu Termux Android atau Android Termux?

Termux adalah terminal dan lingkungan Linux untuk Android. Anda dapat menjalankan Git, Python, dan SSH di ponsel. Panduan ini menggabungkan Termux dengan PRoot untuk menjalankan Ubuntu di ruang pengguna tanpa memerlukan akses root pada perangkat.

### Di mana mengunduh Termux dan mendapatkan APK Termux yang aman?

Untuk **Termux download** yang aman, gunakan [repositori resmi Termux di GitHub](https://github.com/termux/termux-app) atau [F-Droid](https://f-droid.org/packages/com.termux/). Keduanya adalah sumber yang direkomendasikan untuk **APK Termux**. Hindari situs pihak ketiga yang menawarkan “termux apk download”, “download apk termux”, “download termux apk”, atau “termux download apk”, karena berkasnya mungkin sudah usang atau telah dimodifikasi. Jangan mencampur instalasi dari sumber yang berbeda.

### Bagaimana cara memasang Ubuntu di Termux tanpa root?

Perbarui Termux, pasang `proot-distro`, jalankan `proot-distro install ubuntu`, lalu masuk dengan `proot-distro login ubuntu`. PRoot menyediakan lapisan kompatibilitas di ruang pengguna; PRoot tidak memberikan akses root yang sebenarnya ke Android.

### Bagaimana cara memasang Python di Termux atau Ubuntu?

Untuk **Termux Python**, jalankan `pkg update && pkg install python -y` di Termux. Di dalam Ubuntu, gunakan `apt update && apt install python3 python3-pip -y`. Perintah yang digunakan bergantung pada lingkungan tempat Anda ingin memasang Python.

### Apakah Termux dapat menggantikan PC?

Pencarian **Termux PC** biasanya berarti menggunakan ponsel Android sebagai workstation Linux ringan. Termux dan Ubuntu melalui PRoot berguna untuk pengembangan, otomasi, Git, dan SSH, tetapi tidak sepenuhnya menggantikan PC desktop dan dapat memiliki keterbatasan kinerja, izin, serta akses perangkat keras.

### Apa GitHub resmi Termux dan bagaimana mendapatkan versi terbaru?

TermuxUbuntuPRoot adalah panduan komunitas. Kode sumber dan rilis resmi aplikasi ada di [termux/termux-app di GitHub](https://github.com/termux/termux-app). Untuk pencarian seperti **GitHub Termux**, **Termux GitHub**, **Termux Android 5**, dan **Termux latest version**, periksa persyaratan terbaru dan [rilis resmi](https://github.com/termux/termux-app/releases), bukan situs APK mirror. Anda juga dapat melihat variasi ejaan seperti “Termex”, “Termax”, `termux indir`, `تيرمكس`, dan `термукс`.
