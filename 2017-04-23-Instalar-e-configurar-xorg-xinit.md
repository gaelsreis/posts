---
layout: post
title: "Instalar e configurar o Xorg-xinit no archLinux"
image: ''
date: 2017-04-23 03:27:09
tags:
- Linux
- Terminal
- Xorg
- Lightdm
description: "O Xorg-xinit é um front-end para o Starx e que pode muito bem substituir o Lightdm e outros display-managers. E neste tutorial iremos aprender a como instalar e configurar o Xorg-xinit"
categories:
- Linux
serie: Linux
---

# Introdução

O ***Xorg-xinit*** é um front-end para o **startx** e uma opção muito boa para quem não deseja mais utilizar o **Lightdm** ou outro display-manager.

Eu passei a usar o ***Xorg-xinit*** a algum tempo atrás, depois que o **Lightdm** ficou com um bug na qual não iniciava a interface gráfica. Depois deste bug, o pessoal do grupo de [ArchLinux no Telegram](https://t.me/archlinuxbr "Grupo brasileiro de ArchLinux") me aconselhou a desinstalar o **Lightdm** e instalar o ***Xorg-xinit*** e foi exatamente isto que eu fiz. E com base no que eu aprendi, hoje irei ensinar à vocês como instalar e configurar o ***Xorg-xinit***. Então vamos lá.

# Instalação

Primeiramente, devemos desabilitar a inicialização do **Lightdm** e logo após desinstalar o mesmo:

~~~
$ sudo systemctl disable lightdm && sudo pacman -Rsc lightdm
~~~

Logo após desabilitar a inicialização do **Lightdm** e desintala-lo, devemos instalar o ***Xorg-Xinit***, para isto, devemos dar este comando:


~~~
$ sudo pacman -S xorg-xinit
~~~

Depois de instalado, devemos configura-lo.

# Configuração

Para configura-lo, primeiramente devemos criar o arquivo "***.xserverrc***" na **/home**. Neste tutorial, eu irei usar o **vim** como editor de texto. Se você não sabe como usa-lo, leia [este post](https://linuxroot1.github.io/Vim/ "Como usar o Vim").

~~~
$ vim ~/.xserverrc
~~~

Depois, coloque isto aqui dentro do arquivo:

~~~
#!/bin/sh
exec /usr/bin/X -nolisten txp "$@"
~~~

Depois disso, devemos configurar o arquivo "***.xinitrc***", para isto, iremos abri-lo:

~~~
$ vim ~/.xinitrc
~~~

Dentro do arquivos, devemos colocar qual interface iremos iniciar:

~~~
exec i3
~~~

Neste caso, quando for dado o comando "***startx***", será iniciado o **i3-gaps**, na qual já ensinei a [como configura-lo](https://linuxroot1.github.io/i3gaps/ "Instalar e configurar o i3-gaps").

Você pode colocar para iniciar o *xfce4*, para isto, coloque isto dentro do arquivo:

~~~
exec xfce4
~~~

Você ainda pode configurar o ***.xinitrc*** para poder selecionar qual interface deseja iniciar:

~~~
session=${1:-xfce}

case $session in
    i3|i3wm           ) exec i3;;
    kde               ) exec startkde;;
    xfce|xfce4        ) exec startxfce4;;
    *                 ) exec $1;;
esac
~~~

Se você configurou desta maneira, você precisa dar este comando:

> $ xinit session

***Exemplo***:

> $ xinit xfce

Você deverá mudar o "*session*" pela sessão deseja iniciar.

# Final

E este foi o post de hoje, espero que tenha gostado. Se você tiver alguma duvida, leia a wiki do ***Xorg-xinit***:

[Wiki do Xorg-xinit](https://wiki.archlinux.org/index.php/Xinit "Wifi do Xorg-xinit")

Se você tiver alguma duvida, podem também falar diretamente comigo, no grupo de ArchLinux no Telegram:

[Grupo de ArchLinux no Telegram](https://t.me/archlinuxbrasil "Grupo de ArchLinux no Telegram")
