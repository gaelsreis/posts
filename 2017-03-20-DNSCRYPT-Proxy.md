---
layout: post
title: "Instalando e usando o DNSCrypt-Proxy"
image: ''
date: 2017-03-20
tags:
- Privacidade
- Linux
- Software Livre
- OpenSource
- Criptografia
description: "Neste post, irei explicar o que é o DNSCrypt-proxy, como instala-lo e usa-lo."
categories:
- Privacidade
serie: Privacidade na internet
---

# Introdução

O [DNSCrypt-Proxy](http://dnscrypt.org "DNSCrypt-Proxy") criptografa e autenfica o tráfego de DNS entre o usuário e o DNS resolver (resolvedor DNS). Ele é muito útil para previnir DNS Leak. Se você quiser saber mais sobre o **DNSCrypt-Proxy**, acesse a [ArchWiki do DNSCrypt-Proxy](https://wiki.archlinux.org/index.php/DNSCrypt "DNSCrypt-Proxy - ArchWiki").

## Instalando

Irei demonstrar como instalar o **DNSCrypt-Proxy** no *ArchLinux* e derivados e também no *Debian* e derivados do mesmo.

Primeiramente, iremo demonstrar a instalação do **DNSCrypt-Proxy** no *ArchLinux*.

Primeiramente, vamos instalar o **DNSCrypt-Proxy**, para isto, abra o terminal e digite:

~~~
$ sudo pacman -S dnscrypt-proxy
~~~

E já está instalado, agora, vamos habilitar o **DNSCrypt-Proxy** na inicialização do sistema:

~~~
$ sudo systemctl enable dnscrypt-proxy
~~~

Desta forma, iremos colocar o **dnscrypt-proxy** para iniciar com o sistema.

Agora, vamos instalar o **DNSCrypt-Proxy** no Debian.

### Instalando no Debian

Primeiramente, iremos baixar o pacote do **DNSCrypt-Proxy**, para isto, abra o terminal e digite:

~~~
$ wget -c https://download.dnscrypt.org/dnscrypt-proxy/dnscrypt-proxy-1.9.4.tar.gz
~~~

Depois de ter baixado o pacote, iremos descompacta-lo, para isto, de o comando:

~~~
$ tar -xzvf dnscrypt-proxy-1.9.4.tar.gz
~~~

Depois de descompactar, vamos à pasta do arquivo:

~~~
$ cd ~/dnscrypt-proxy-1.9.4
~~~

Agora, vamos instalar:

~~~
$ ./configure && make -j2
~~~

Depois, de o comando:

~~~
$ sudo make install
~~~

Espere instalar, depois de instalado, vamos habilitar o **DNSCrypt-Proxy** para iniciar com o sistema.

Para inicar o **DNSCrypt-Proxy** junto com o sistema, vamos dar o comando:

~~~
$ sudo systemctl enable dnscrypt-proxy
~~~

Depois de te-lo habilitado para iniciar junto com o sistema, vamos configura-lo.

## Configuração

Agora, vamos configurar o **DNSCrypt-Proxy**, para fazermos isto, iremos abrir o arquivo */etc/dnscrypt-proxy.conf*:

~~~
$ sudo gedit /etc/dnscrypt-proxy.conf
~~~

Onde está escrito "*ResolverName*", iremos trocar para o nosso servidor DNS, para escolher o servidores DNS, vá [neste site](https://github.com/jedisct1/dnscrypt-proxy/blob/master/dnscrypt-resolvers.csv "Dns"). Depois de selecionar o servidor DNS que você deseja, vamos setar ele na linha do *ResolverName*:

~~~
ResolverName cs-fr
~~~

**OBS**: Este é só um exemplo, tu pode colocar outro servidor no lugar de **cs-fr**.

Salve e feche o arquivo de configuração.

Agora, vamos configurar o servidor DNS na qual o sistem irá usar, para isto, abra o arquivo */etc/resolv.conf*:

~~~
$ sudo gedit /etc/resolv.conf
~~~

Então, vamos setar qual servidor DNS o sistema irá usar, para isto, coloque da seguinte maneira:

~~~
nameserver 127.0.0.1
nameserver 127.0.0.1
~~~

E pronto, o **DNSCrypt-Proxy** já está instalado e configurado no teu sistema.

## Final

E este foi o post de hoje, espero que ele tenha sido muito util, para você que usa Windows ou outros sistemas, irei deixar alguns links sobre como instalar o **DNSCrypt-Proxy** em outros sistemas:

[DNSCrypt](https://dnscrypt.org "DNSCrypt - Official WebSite")

[DNSCrypt-Proxy Wiki](https://github.com/jedisctl/dnscrypt-proxy/wiki "Wiki oficial do DNSCrypt-Proxy")

[DNSCrypt-Proxy - ArchWiki](https://wiki.archlinux.org/index.php/DNSCrypt "DNSCrypt-Proxy - ArchWiki")

[DNSCrypt-Proxy - Wiki - Instalação](https://github.com/jedisctl/dnscrypt-proxy/wiki/How-to-install-DNSCrypt "Como instalar o DNSCrytp-Proxy em outros sistemas")

[Servidores DNS para escolher](https://github.com/jedisct1/dnscrypt-proxy/blob/master/dnscrypt-resolvers.csv "Servidores DNS para escolher")

