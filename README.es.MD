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

## Preguntas frecuentes sobre Termux, Android y Ubuntu

Estas preguntas responden a las principales búsquedas de Google Trends sobre **Termux**, como “termux android”, “android termux”, “termux download”, “apk termux”, “github termux”, “termux python” y “termux pc”. Consulta también la [comparación de Google Trends para Termux](https://trends.google.com/trends/explore?date=all&q=Termux).

### ¿Qué es Termux Android o Android Termux?

Termux es un terminal y entorno Linux para Android. Permite usar herramientas como Git, Python y SSH en el teléfono. Esta guía combina Termux con PRoot para ejecutar Ubuntu en el espacio de usuario, sin necesidad de root en el dispositivo.

### ¿Dónde descargar Termux y el APK de Termux?

Para descargar Termux de forma segura, utiliza el [repositorio oficial de Termux en GitHub](https://github.com/termux/termux-app) o [F-Droid](https://f-droid.org/packages/com.termux/). Son las fuentes recomendadas para el **APK Termux**. Evita sitios de terceros que prometan “termux apk download”, “download apk termux”, “download termux apk” o “termux download apk”, porque pueden distribuir archivos modificados o desactualizados. No mezcles instalaciones de fuentes diferentes.

### ¿Cómo instalar Ubuntu en Termux sin root?

Actualiza Termux, instala `proot-distro`, ejecuta `proot-distro install ubuntu` y entra con `proot-distro login ubuntu`. PRoot ofrece una capa de compatibilidad en el espacio de usuario; no concede acceso root real a Android.

### ¿Cómo instalar Python en Termux o Ubuntu?

Para **Termux Python**, ejecuta `pkg update && pkg install python -y` en Termux. Dentro de Ubuntu, utiliza `apt update && apt install python3 python3-pip -y`. El comando depende del entorno en el que quieras instalar Python.

### ¿Puede Termux sustituir a un PC?

La búsqueda **Termux PC** suele referirse a usar un teléfono Android como estación Linux ligera. Termux y Ubuntu mediante PRoot son útiles para programación, automatización, Git y SSH, pero no sustituyen por completo a un PC de escritorio y pueden tener limitaciones de rendimiento, permisos y acceso al hardware.

### ¿Cuál es el GitHub oficial de Termux y cómo obtener la última versión?

TermuxUbuntuPRoot es una guía de la comunidad. El código y las versiones oficiales de la aplicación están en [termux/termux-app en GitHub](https://github.com/termux/termux-app). Para búsquedas como **GitHub Termux**, **Termux GitHub**, **Termux Android 5** y **Termux latest version**, comprueba los requisitos actuales y las [versiones oficiales](https://github.com/termux/termux-app/releases), no un espejo de APK. También puedes ver `Termex`, `Termax`, `termux indir`, `تيرمكس` o `термукс` como variantes de búsqueda.
