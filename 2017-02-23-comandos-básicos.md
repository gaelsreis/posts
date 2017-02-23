---
layout: post
title: "Comandos básicos para começar a usar o terminal"
image: ''
date: 2017-02-23 21:41:50
tags:
- Linux
- Terminal
- Comandos
- Bash
- ZSH
description: "Um post mostrando alguns comandos básicos no Linux."
categories:
- Linux
serie: Linux
---

# O que é shell

 O shell é a ligação entre o usuário e o sistema. É ele quem interpreta os comandos entrados para outros aplicativos ou diretamente em chamadas de sistema. Além disso, os recursos do shell são indispensáveis para lidar com muitos arquivos ao mesmo tempo, para realizar uma tarefa repetidamente ou para programar uma ação para determinada ocasião, entre outros recursos. Começamos apresentando os tipos de shell mais difundidos e depois definindo alguns conceitos que serão úteis na sua utilização, para então tratarmos de exemplos práticos.

# Comandos básicos da shell

A shell padrão de muitas distribuições Linux é o *bash*, por isto, iremos trabalhar com ela.
Então vamos mostrar alguns comandos:

> ls 
ou
> ls pasta

O comando **ls** é para ver o que há dentro de um diretorio.

---

O comando **cat** é para ver o que há dentro de um arquivo.

> cat arquivo

*Exemplo*:

> cat ~/script.sh

Desta forma ele irá mostrar tudo o que há dentro do script.

---

O comando **cd** serve para *navegar* entre os diretorios.

> cd pasta

*Exemplo*:

> cd ~/Documentos/livros

Desta maneira iremos ir da **/home/user** para a **/home/user/Documentos/livros**.

---

O comando **grep** é para filtrar saída de comandos.

> primeiro comando | grep "palavra"

*Exemplo*:

> cat ~/script | grep "#!/bin/bash"

Desta forma, a saída do comando **cat** só irá mostrar o *"#!/bin/bash"*

---

O comando **locate** serve para localizar arquivos em toda a partição raiz (Popularmente conhecida como **/**.)

> locate arquivo

*Exemplo*:

> locate script.sh

Desta maneira, ele irá mostrar onde está todos os arquivos que tenha *"script.sh"* no nome. Há também a possibilidade de tu usar o *"grep"* com o comando locate.

> locate script.sh | grep "/home/user/script.sh"

---

O comando **tar** é para compactar e descompactar arquivos no Linux pela shell.

Criar um arquivo .tar com o conteudo de um diretório:

> tar cvf documentos.tar ~/Documentos

Extrair arquivos de um arquivo em *.tar*:

> tar xfv arquivo.tar

Ver o que tem dentro de um arquivo *.tar*:

> tar tvf arquivo.tar

---

O comando **shutdown** serve para desligar o computador:

> shutdown -h now

Com esta comando, ele irá desligar o computador imediatamente.

Desligar o computador depois de 10 minutos:

> shutdown -h +10

---

Dar reboot no computador:

> reboot

---

O comando **free** é para verificar o comsumo de *ram* e *swap* no computador:

> free -m

O parametro **-m** é para ver o consumo em *MB*.

---

O comando **su** é um comando muito usado para usar o usuario *root*, mas muitas pessoas se enganam como ele funciona. O comando **su** é para trocar de usuario:

> su

Com este comando, o usuario *root* será usado.

Mudar do usuario *linuxroot1* para o usuario *linuxroot2*:

> su linuxroot2

---

O comando **mount** é para montar partições.

> sudo mount /dev/sda2

Desta forma a partição */dev/sda2* será montada.

---

Estes foram alguns comandos que eu achei util, se quiserem adicionarem mais comandos aqui, só ir [neste link](https://github.com/linuxroot1/posts "GitHub postagens").

---

# Links e outros posts

Alguns links sobre comandos:

[grep](https://elias.praciano.com/2013/02/linux-como-usar-o-comando-grep/ "Grep")
[tar](http://elias.praciano.com/2014/02/o-comando-tar-em-9-exemplos/ "Tar")
[mount](https://elias.praciano.com/2016/01/como-usar-o-comando-mount-para-visualizar-montar-e-desmontar-sistemas-de-arquivos-no-linux/ "mount")
[ls](https://www.vivaolinux.com.br/artigo/O-comando-LS-de-A-a-Z "ls")
[cat](https://www.vivaolinux.com.br/dica/Utilizacao-do-comando-cat "cat")
[su](http://www.bosontreinamentos.com.br/linux/certificacao-lpic-1/comando-su-trocando-o-usuario-na-linha-de-comandos-lpic-1/ "su")
[Comandos básicos Linux](http://elias.praciano.com/2013/12/linux-comandos-basicos/ "Comandos básicos Linux")
