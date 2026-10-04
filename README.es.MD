# TermuxUbuntuPRoot

> 🌐 [Otros idiomas / Other languages](README.md)

Guía de cómo instalar Ubuntu dentro de Termux usando PRoot.

**NOTA: No necesitas root en tu dispositivo para seguir esta guía**

## 0 - Actualizar los paquetes de Termux

```
pkg update && pkg upgrade -y
```

## 1 - Instalar PRoot

```
pkg install proot-distro -y
```

## 2 - Instalar `Ubuntu` dentro de PRoot

```
proot-distro install ubuntu
```

## 3 - Iniciar sesión en `Ubuntu`

```
proot-distro login ubuntu
```

Ahora estás dentro de Ubuntu con el usuario **root**.

## 4 - Actualizar los paquetes del sistema `Ubuntu`

```
apt update && apt upgrade -y
```

## 5 - Instalar una interfaz gráfica (opcional)

### Con Termux:X11 (recomendado para mejor rendimiento)

1. Instala la aplicación Termux:X11 en Android.
2. En Termux (fuera de PRoot), instala el soporte: `pkg install x11-repo termux-x11-nightly`.
3. Dentro de Ubuntu, instala el entorno gráfico: `apt install xfce4 xfce4-goodies -y`.

### Con VNC

1. En Ubuntu, instala: `apt install xfce4 tigervnc-standalone-server -y`.
2. Configura la contraseña de VNC e inicia el servidor con `vncserver`, conectándote mediante una aplicación cliente de VNC (como AVNC o VNC Viewer) en la dirección `127.0.0.1:5901`.

## Comandos Útiles de PRoot-Distro

- Salir de Ubuntu: escribe `exit`.
- Listar distribuciones soportadas: `proot-distro list`.
- Hacer una copia de seguridad de tu Ubuntu: ejecuta en Termux: `tar -zcvf ubuntu-backup.tar.gz -C $PREFIX/var/lib/proot-distro/installed-rootfs/ubuntu .`
