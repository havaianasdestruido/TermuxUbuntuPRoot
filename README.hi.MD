# TermuxUbuntuPRoot

> 🌐 [अन्य भाषाएँ / Other languages](README.md)

PRoot का उपयोग करके Termux के अंदर Ubuntu इंस्टॉल करने की गाइड।

**नोट: इस गाइड का पालन करने के लिए आपके डिवाइस पर root की आवश्यकता नहीं है**

## 0 - Termux पैकेज अपडेट करें

```
pkg update && pkg upgrade -y
```

## 1 - PRoot इंस्टॉल करें

```
pkg install proot-distro -y
```

## 2 - PRoot के अंदर `Ubuntu` इंस्टॉल करें

```
proot-distro install ubuntu
```

## 3 - `Ubuntu` में लॉगिन करें

```
proot-distro login ubuntu
```

अब आप **root** उपयोगकर्ता के रूप में Ubuntu के अंदर हैं।

## 4 - `Ubuntu` सिस्टम पैकेज अपडेट करें

```
apt update && apt upgrade -y
```

## 5 - GUI इंस्टॉल करें (वैकल्पिक)

### Termux:X11 के साथ (बेहतर प्रदर्शन के लिए अनुशंसित)

1. Android पर Termux:X11 ऐप इंस्टॉल करें।
2. Termux में (PRoot के बाहर), सपोर्ट पैकेज इंस्टॉल करें: `pkg install x11-repo termux-x11-nightly`।
3. Ubuntu के अंदर, ग्राफिकल एनवायरनमेंट इंस्टॉल करें: `apt install xfce4 xfce4-goodies -y`।

### VNC के साथ

1. Ubuntu में इंस्टॉल करें: `apt install xfce4 tigervnc-standalone-server -y`।
2. VNC पासवर्ड सेट करें और `vncserver` से सर्वर शुरू करें, फिर किसी VNC क्लाइंट ऐप (जैसे AVNC या VNC Viewer) से `127.0.0.1:5901` पते पर कनेक्ट करें।

## PRoot-Distro के उपयोगी कमांड

- Ubuntu से बाहर निकलें: `exit` टाइप करें।
- समर्थित डिस्ट्रीब्यूशन की सूची देखें: `proot-distro list`।
- अपने Ubuntu का बैकअप लें: Termux में चलाएँ: `tar -zcvf ubuntu-backup.tar.gz -C $PREFIX/var/lib/proot-distro/installed-rootfs/ubuntu .`

## Termux, Android और Ubuntu के बारे में अक्सर पूछे जाने वाले प्रश्न

ये प्रश्न **Termux** के बारे में Google Trends की प्रमुख खोजों का उत्तर देते हैं, जैसे “termux android”, “android termux”, “termux download”, “apk termux”, “github termux”, “termux python” और “termux pc”। [Termux के लिए Google Trends तुलना](https://trends.google.com/trends/explore?date=all&q=Termux) भी देखें।

### Termux Android या Android Termux क्या है?

Termux Android के लिए एक टर्मिनल और Linux एनवायरनमेंट है। इससे आप फोन पर Git, Python और SSH जैसे टूल चला सकते हैं। यह गाइड Termux को PRoot के साथ उपयोग करके डिवाइस पर root की आवश्यकता के बिना user space में Ubuntu चलाती है।

### Termux कहाँ से डाउनलोड करें और सुरक्षित Termux APK कहाँ मिलेगा?

सुरक्षित **Termux download** के लिए [GitHub पर आधिकारिक Termux रिपॉज़िटरी](https://github.com/termux/termux-app) या [F-Droid](https://f-droid.org/packages/com.termux/) का उपयोग करें। **Termux APK** के लिए यही अनुशंसित स्रोत हैं। “termux apk download”, “download apk termux”, “download termux apk” या “termux download apk” देने वाली थर्ड-पार्टी साइटों से बचें, क्योंकि फ़ाइलें पुरानी या बदली हुई हो सकती हैं। अलग-अलग स्रोतों की इंस्टॉलेशन को आपस में न मिलाएँ।

### बिना root के Termux में Ubuntu कैसे इंस्टॉल करें?

Termux अपडेट करें, `proot-distro` इंस्टॉल करें, `proot-distro install ubuntu` चलाएँ और `proot-distro login ubuntu` से लॉगिन करें। PRoot user space में compatibility layer देता है; यह Android को वास्तविक root access नहीं देता।

### Termux या Ubuntu में Python कैसे इंस्टॉल करें?

**Termux Python** के लिए Termux में `pkg update && pkg install python -y` चलाएँ। Ubuntu के अंदर `apt update && apt install python3 python3-pip -y` का उपयोग करें। सही कमांड इस बात पर निर्भर करती है कि Python किस एनवायरनमेंट में इंस्टॉल करना है।

### क्या Termux PC की जगह ले सकता है?

**Termux PC** खोज का मतलब आमतौर पर Android फोन को हल्के Linux workstation की तरह उपयोग करना है। Termux और PRoot के साथ Ubuntu development, automation, Git और SSH के लिए उपयोगी हैं, लेकिन desktop PC का पूरा विकल्प नहीं हैं और performance, permissions तथा hardware access में सीमाएँ हो सकती हैं।

### आधिकारिक Termux GitHub कौन-सा है और नवीनतम संस्करण कैसे मिलेगा?

TermuxUbuntuPRoot समुदाय की एक गाइड है। ऐप का आधिकारिक source और releases [GitHub के termux/termux-app](https://github.com/termux/termux-app) में हैं। **GitHub Termux**, **Termux GitHub**, **Termux Android 5** और **Termux latest version** खोजते समय मौजूदा requirements और [आधिकारिक releases](https://github.com/termux/termux-app/releases) जाँचें, APK mirror पर भरोसा न करें। “Termex”, “Termax”, `termux indir`, `تيرمكس` और `термукс` भी सामान्य search variants हैं।
