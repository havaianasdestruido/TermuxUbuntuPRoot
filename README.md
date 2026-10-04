# TermuxUbuntuPRoot
Guide on how to install Ubuntu inside Termux using PRoot.

**NOTE: You don't need root on your device to follow this guide**

## 0 - Update Termux packages

```
pkg update && pkg upgrade -y
```

## 1 - Install PRoot

```
pkg install proot-distro -y
```

## 2 - Install `Ubuntu` inside PRoot

```
proot-distro install ubuntu
```

## 3 - Login into `Ubuntu`

```
proot-distro login ubuntu
```

Now you are into Ubuntu under the **root** user.

## 4 - Update `Ubuntu` system packages

```
apt update && apt upgrade -y
```
## 5 - Install a GUI (optional)

### Com Termux:X11 (recomendado para melhor desempenho)

	1. Instale o aplicativo Termux:X11 no Android.
	2. No Termux (fora do PRoot), instale o suporte: `pkg install x11-repo termux-x11-nightly`.
	3. Dentro do Ubuntu, instale o ambiente gráfico: `apt install xfce4 xfce4-goodies -y`.

### Com VNC

	1. No Ubuntu, instale: `apt install xfce4 tigervnc-standalone-server -y`.
	2. Configure a senha do VNC e inicie o servidor com `vncserver`, conectando via um aplicativo cliente de VNC (como o avnc ou VNC Viewer) no endereço `127.0.0.1:5901`.

## Comandos Úteis do PRoot-Distro
• Sair do Ubuntu: Digite exit.
• Listar distribuições suportadas: proot-distro list.
• Fazer backup do seu Ubuntu: Execute no Termux: tar -zcvf ubuntu-backup.tar.gz -C $PREFIX/var/lib/proot-distro/installed-rootfs/ubuntu .
