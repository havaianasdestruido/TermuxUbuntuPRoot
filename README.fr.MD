# TermuxUbuntuPRoot

> 🌐 [Autres langues / Other languages](README.md)

Guide d'installation d'Ubuntu dans Termux avec PRoot.

**REMARQUE : Vous n'avez pas besoin de root sur votre appareil pour suivre ce guide**

## 0 - Mettre à jour les paquets Termux

```
pkg update && pkg upgrade -y
```

## 1 - Installer PRoot

```
pkg install proot-distro -y
```

## 2 - Installer `Ubuntu` dans PRoot

```
proot-distro install ubuntu
```

## 3 - Se connecter à `Ubuntu`

```
proot-distro login ubuntu
```

Vous êtes maintenant dans Ubuntu avec l'utilisateur **root**.

## 4 - Mettre à jour les paquets système d'`Ubuntu`

```
apt update && apt upgrade -y
```

## 5 - Installer une interface graphique (optionnel)

### Avec Termux:X11 (recommandé pour de meilleures performances)

1. Installez l'application Termux:X11 sur Android.
2. Dans Termux (hors PRoot), installez les paquets de support : `pkg install x11-repo termux-x11-nightly`.
3. Dans Ubuntu, installez l'environnement graphique : `apt install xfce4 xfce4-goodies -y`.

### Avec VNC

1. Dans Ubuntu, installez : `apt install xfce4 tigervnc-standalone-server -y`.
2. Définissez le mot de passe VNC et démarrez le serveur avec `vncserver`, puis connectez-vous avec une application cliente VNC (comme AVNC ou VNC Viewer) à l'adresse `127.0.0.1:5901`.

## Commandes utiles de PRoot-Distro

- Quitter Ubuntu : tapez `exit`.
- Lister les distributions prises en charge : `proot-distro list`.
- Sauvegarder votre Ubuntu : exécutez dans Termux : `tar -zcvf ubuntu-backup.tar.gz -C $PREFIX/var/lib/proot-distro/installed-rootfs/ubuntu .`

## Questions fréquentes sur Termux, Android et Ubuntu

Ces questions répondent aux principales recherches Google Trends sur **Termux**, notamment « termux android », « android termux », « termux download », « apk termux », « github termux », « termux python » et « termux pc ». Consultez aussi la [comparaison Google Trends pour Termux](https://trends.google.com/trends/explore?date=all&q=Termux).

### Qu’est-ce que Termux Android ou Android Termux ?

Termux est un terminal et un environnement Linux pour Android. Il permet d’utiliser Git, Python et SSH sur un téléphone. Ce guide associe Termux à PRoot pour exécuter Ubuntu dans l’espace utilisateur, sans avoir besoin des droits root sur l’appareil.

### Où télécharger Termux et trouver un APK Termux sûr ?

Pour un téléchargement Termux sûr, utilisez le [dépôt officiel Termux sur GitHub](https://github.com/termux/termux-app) ou [F-Droid](https://f-droid.org/packages/com.termux/). Ce sont les sources recommandées pour l’**APK Termux**. Évitez les sites tiers qui proposent « termux apk download », « download apk termux », « download termux apk » ou « termux download apk », car les fichiers peuvent être modifiés ou obsolètes. Ne mélangez pas les installations provenant de sources différentes.

### Comment installer Ubuntu dans Termux sans root ?

Mettez Termux à jour, installez `proot-distro`, exécutez `proot-distro install ubuntu`, puis connectez-vous avec `proot-distro login ubuntu`. PRoot fournit une couche de compatibilité dans l’espace utilisateur ; il ne donne pas un véritable accès root à Android.

### Comment installer Python dans Termux ou Ubuntu ?

Pour **Termux Python**, exécutez `pkg update && pkg install python -y` dans Termux. Dans Ubuntu, utilisez `apt update && apt install python3 python3-pip -y`. La commande dépend de l’environnement dans lequel vous souhaitez installer Python.

### Termux peut-il remplacer un PC ?

La recherche **Termux PC** désigne généralement l’utilisation d’un téléphone Android comme poste Linux léger. Termux et Ubuntu avec PRoot sont utiles pour le développement, l’automatisation, Git et SSH, mais ils ne remplacent pas complètement un PC et peuvent avoir des limites de performances, de permissions et d’accès au matériel.

### Quel est le GitHub officiel de Termux et comment obtenir la dernière version ?

TermuxUbuntuPRoot est un guide communautaire. Le code source et les versions officielles de l’application se trouvent dans [termux/termux-app sur GitHub](https://github.com/termux/termux-app). Pour les recherches « **GitHub Termux** », « **Termux GitHub** », « **Termux Android 5** » et « **Termux latest version** », vérifiez les exigences actuelles et les [versions officielles](https://github.com/termux/termux-app/releases), plutôt qu’un miroir APK. Vous pouvez aussi rencontrer les variantes « Termex », « Termax », `termux indir`, `تيرمكس` et `термукс`.
