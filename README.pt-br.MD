# TermuxUbuntuPRoot: Instalar Ubuntu no Termux com PRoot

> 🌐 [Outros idiomas / Other languages](README.md)

Guia prático para instalar o Ubuntu no Termux, no Android, usando PRoot e sem acesso root.

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

## Perguntas frequentes sobre Termux, Android e Ubuntu

Estas perguntas respondem às principais buscas relacionadas a **Termux** mostradas na [comparação do Google Trends para Termux](https://trends.google.com/trends/explore?date=all&q=Termux), incluindo “termux android”, “android termux”, “apk termux”, “termux download”, “github termux”, “termux python” e “termux pc”. As palavras-chave aparecem em um contexto útil, sem repetição artificial.

### O que é Termux no Android (Termux Android / Android Termux)?

O Termux é um terminal e ambiente Linux para Android. Ele oferece um shell e um gerenciador de pacotes para executar ferramentas como Git, Python e SSH no celular. Este guia combina o Termux com o PRoot para executar um ambiente de usuário Ubuntu sem exigir root no dispositivo.

### Onde fazer download do Termux e encontrar um APK Termux seguro?

Para fazer o **download do Termux**, use o [repositório oficial do aplicativo Termux no GitHub](https://github.com/termux/termux-app) ou a página do [F-Droid](https://f-droid.org/packages/com.termux/). Essas são as fontes recomendadas para o **APK Termux**. Evite páginas de terceiros com termos como “termux apk download”, “download apk termux”, “download termux apk” e “termux download apk”, pois o arquivo pode estar desatualizado ou modificado. Não misture instalações de fontes diferentes.

### Como instalar Ubuntu no Termux sem root?

Execute os comandos deste guia na ordem: atualize o Termux, instale o `proot-distro`, instale o Ubuntu e entre com `proot-distro login ubuntu`. O PRoot fornece uma camada de compatibilidade em espaço de usuário; ele não concede acesso root real ao Android. Consulte as instruções passo a passo acima.

### Como instalar Python no Termux ou no Ubuntu?

Para usar **Termux Python**, execute `pkg update && pkg install python -y` no Termux. Depois de entrar no Ubuntu, use `apt update && apt install python3 python3-pip -y`. O comando correto depende de você querer instalar o **Python no Termux** ou dentro do ambiente Ubuntu.

### O Termux pode ser usado como um PC?

A busca **Termux PC** normalmente significa usar o celular Android como uma estação Linux leve. Termux e Ubuntu via PRoot são úteis para desenvolvimento em linha de comando, scripts, automação, Git e SSH. Eles não substituem completamente um PC de mesa e podem ter limitações de desempenho, permissões, acesso ao hardware e aplicativos gráficos.

### Este é o repositório oficial do Termux no GitHub?

Não. O TermuxUbuntuPRoot é um guia da comunidade para instalar Ubuntu no Termux. O código-fonte e as versões oficiais do aplicativo estão no [termux/termux-app no GitHub](https://github.com/termux/termux-app). Ao pesquisar por **GitHub Termux** ou **Termux GitHub**, confira se o resultado aponta para esse repositório antes de baixar um APK.

### O Termux funciona no Android 5 e qual é a versão mais recente?

O suporte depende dos requisitos da versão oficial específica. Para a busca **Termux Android 5**, confira as informações atuais de compatibilidade antes de instalar, pois versões novas podem não oferecer suporte a versões antigas do Android. Para encontrar a **termux latest version**, use as [versões oficiais no GitHub](https://github.com/termux/termux-app/releases) ou a [página do F-Droid](https://f-droid.org/packages/com.termux/), e não um espelho de APK.

### Por que aparecem buscas como Termex, Termax e outras grafias?

**Termex** e **Termax** são variações comuns de escrita. Em turco, `termux indir` significa “baixar Termux”. Também existem buscas em árabe, como `تحميل`, `تيرمكس`, `termux تحميل`, `تحميل termux`, `تيرموكس`, `تريمكس`, `ترميكس`, `ترماكس`, `تنزيل termux` e `التريمكس`, e buscas em russo, como `термукс` e `термукс скачать`. Todas se referem ao aplicativo Termux; por isso, os links oficiais do GitHub e do F-Droid acima continuam sendo as fontes mais seguras para download.
