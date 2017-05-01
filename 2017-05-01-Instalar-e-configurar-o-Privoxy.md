---
layout: post
title: "Instalando e configurando o Privoxy + Tor no ArchLinux e derivados."
image: ''
date: 2017-05-01 09:14:58
tags:
- Linux
- Anonimato
- Segurança
- Privacidade
description: "O Privoxy é um proxy web com recursos avançados de filtragem para proteger a privacidade, filtrar conteúdo da página da Web, gerenciar cookies e é amplamente usado em combinação com o Tor."
categories:
- Privacidade
serie: Privacidade na internet
---

# Introdução

O ***Privoxy*** é um proxy web com recursos avançados de filtragem para proteger a privacidade, filtrar conteúdo da página da Web, gerenciar cookies e várias outras coisas. Ele é amplamente usado em conjunto com o Tor. E hoje, irei ensinar a como instalar e configurar o ***Privoxy*** + ***Tor***. Então vamos lá.

## Instalando o Privoxy e Tor

Primeiro, devemos instalar o ***Privoxy*** e o ***Tor***. Então de este comando:

~~~
$ sudo pacman -S privoxy tor
~~~

Depois de instalado, vamos iniciar o Tor:

~~~
$ sudo systemctl start tor
~~~

Se deseja habilitar o ***Tor*** para que ele inicie junto ao sistema, de este comando:

~~~
$ sudo systemctl enable tor
~~~

E se também quiser habilitar o ***Privoxy*** para iniciar junto ao sistema, de este comando:

~~~
$ sudo systemcl enable tor
~~~

Agora, devemos configurar o ***Privoxy***, então vamos lá.

## Configurando o Privoxy

Agora, vamos configurar o ***Privoxy***, para isto, devemos configurar o arquivo ***/etc/privoxy/config***:

~~~
$ sudo vim /etc/privoxy/config
~~~

Agora, devemos ir até a linha 1336, para isto, de este comando dentro do ***Vim***:

> :1336

Agora, descomente a linha, para isto, apague a hashtag que tem no início da linha, aperte a tecla "**ESC**" e depois, de este comando:

> :wq

Agora, o ***Privoxy*** já está devidamente configurado. Para utilizarmos ele, devemos iniciar o serviço dele com este comando:

~~~
$ sudo systemctl start privoxy
~~~

Agora que o ***Privoxy*** já está iniciado, podemos usa-lo no navegador, no meu caso, será o ***Firefox***. Então abra o ***Firefox*** e clique no menu de hamburger.

![Firefox](/assets/img/menu.png)

Depois de clicar no menu, clique na engrangem para ir até as configurações.

![Firefox2](/assets/img/engrenagem.png)

Agora, vá até a aba "*Advanced*" e depois clique em "*Network*".

![Firefox3](/assets/img/firefox.png)

Clique em "Settings" e depois irá abrir este menu:

![Connection](/assets/img/connection.png)

Selecione a opção de "***Manual proxy configuration***". E adicione o Proxy do ***Privoxy***, que é "***127.0.0.1/8118***":

![Proxy](/assets/img/proxy.png)

Agora, feche o ***Firefox*** e abra-o denovo e você já irá estar utilizando o ***Privoxy*** no teu ***Firefox*** e estará anonimo utilizando o ***Tor + Privoxy***.

# Final

Obrigado a todos que leram o post. Se você tiver alguma dúvida, pode me perguntar diretamente no [Telegram](https://t.me/pao_de_queijo "Pão de Queijo").

[ArchWiki - Privoxy](https://wiki.archlinux.org/index.php/Privoxy "Privoxy")
