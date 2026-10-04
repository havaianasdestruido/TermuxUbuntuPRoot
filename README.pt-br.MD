# TermuxUbuntuPRoot

> 🌐 [Outros idiomas / Other languages](README.md)

Guia de como instalar o Ubuntu dentro do Termux usando o PRoot.

**NOTA: Você não precisa de root no seu dispositivo para seguir este guia**

## 0 - Atualizar os pacotes do Termux

```
pkg update && pkg upgrade -y
```

## 1 - Instalar o PRoot

```
pkg install proot-distro -y
```

## 2 - Instalar o `Ubuntu` dentro do PRoot

```
proot-distro install ubuntu
```

## 3 - Entrar no `Ubuntu`

```
proot-distro login ubuntu
```

Agora você está dentro do Ubuntu com o usuário **root**.

## 4 - Atualizar os pacotes do sistema `Ubuntu`

```
apt update && apt upgrade -y
```

## 5 - Instalar uma interface gráfica (opcional)

### Com Termux:X11 (recomendado para melhor desempenho)

1. Instale o aplicativo Termux:X11 no Android.
2. No Termux (fora do PRoot), instale o suporte: `pkg install x11-repo termux-x11-nightly`.
3. Dentro do Ubuntu, instale o ambiente gráfico: `apt install xfce4 xfce4-goodies -y`.

### Com VNC

1. No Ubuntu, instale: `apt install xfce4 tigervnc-standalone-server -y`.
2. Configure a senha do VNC e inicie o servidor com `vncserver`, conectando via um aplicativo cliente de VNC (como o AVNC ou VNC Viewer) no endereço `127.0.0.1:5901`.

## Comandos Úteis do PRoot-Distro

- Sair do Ubuntu: digite `exit`.
- Listar distribuições suportadas: `proot-distro list`.
- Fazer backup do seu Ubuntu: execute no Termux: `tar -zcvf ubuntu-backup.tar.gz -C $PREFIX/var/lib/proot-distro/installed-rootfs/ubuntu .`
