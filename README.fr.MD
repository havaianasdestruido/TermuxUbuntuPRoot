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
