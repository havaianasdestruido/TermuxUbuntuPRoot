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

## Termux, Android ve Ubuntu hakkında sık sorulan sorular

Bu sorular, **Termux** için Google Trends'te görülen “termux android”, “android termux”, “termux download”, “apk termux”, “github termux”, “termux python” ve “termux pc” gibi başlıca aramaları yanıtlar. Ayrıca [Termux Google Trends karşılaştırmasına](https://trends.google.com/trends/explore?date=all&q=Termux) bakabilirsiniz.

### Termux Android veya Android Termux nedir?

Termux, Android için bir terminal ve Linux ortamıdır. Telefonda Git, Python ve SSH gibi araçları çalıştırmanızı sağlar. Bu kılavuz, cihazda root erişimi gerektirmeden kullanıcı alanında Ubuntu çalıştırmak için Termux'u PRoot ile birleştirir.

### Termux nereden indirilir ve güvenli Termux APK nerede bulunur?

Güvenli bir **Termux download** için [GitHub'daki resmi Termux deposunu](https://github.com/termux/termux-app) veya [F-Droid'u](https://f-droid.org/packages/com.termux/) kullanın. Bunlar **Termux APK** için önerilen kaynaklardır. “termux apk download”, “download apk termux”, “download termux apk” veya “termux download apk” sunan üçüncü taraf sitelerden kaçının; dosyalar değiştirilmiş veya eski olabilir. Farklı kaynaklardan yapılan kurulumları karıştırmayın.

### Root olmadan Termux'a Ubuntu nasıl kurulur?

Termux'u güncelleyin, `proot-distro` paketini kurun, `proot-distro install ubuntu` komutunu çalıştırın ve `proot-distro login ubuntu` ile giriş yapın. PRoot kullanıcı alanında bir uyumluluk katmanı sağlar; Android'e gerçek root erişimi vermez.

### Termux veya Ubuntu'ya Python nasıl kurulur?

**Termux Python** için Termux'ta `pkg update && pkg install python -y` komutunu çalıştırın. Ubuntu içinde `apt update && apt install python3 python3-pip -y` kullanın. Doğru komut, Python'u hangi ortamda kurmak istediğinize bağlıdır.

### Termux bir PC'nin yerini tutabilir mi?

**Termux PC** araması genellikle Android telefonu hafif bir Linux iş istasyonu olarak kullanmak anlamına gelir. Termux ve PRoot ile Ubuntu; geliştirme, otomasyon, Git ve SSH için kullanışlıdır, ancak masaüstü bilgisayarın yerini tamamen tutmaz ve performans, izinler ve donanım erişimi bakımından sınırlı olabilir.

### Resmi Termux GitHub adresi nedir ve en son sürüm nasıl bulunur?

TermuxUbuntuPRoot, topluluk tarafından hazırlanan bir kılavuzdur. Uygulamanın resmi kaynak kodu ve sürümleri [GitHub'daki termux/termux-app](https://github.com/termux/termux-app) adresindedir. **GitHub Termux**, **Termux GitHub**, **Termux Android 5** veya **Termux latest version** aramalarında güncel gereksinimleri ve [resmi sürümleri](https://github.com/termux/termux-app/releases) kontrol edin; APK aynalarına güvenmeyin. “Termex”, “Termax” ve `termux indir` de yaygın arama varyasyonlarıdır.
