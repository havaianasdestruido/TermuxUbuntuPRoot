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
