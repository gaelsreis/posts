---
layout: post
title: "Como instalar e utilizar o GPA"
image: ''
date: 2017-05-02 03:16:50
tags:
- Privacidade
- Criptografia
- Segurança
- Anonimato
- GPG
- GPA
description: "O GPA é um software front-end do GnuPG"
categories:
- Privacidade
serie: Privacidade na internet
---

# Introdução

O ***GPA*** é um *Front-End* para o ***GPG*** (***GNU Privacy Guard***), que é uma implementação grátis e completa do ***OpenPGP***.

O ***GPG*** é utilizado, ainda que bem pouco por usuários comuns, para poder enviar mensagens criptografadas via Email.

O ***GPG*** funciona de uma forma bem diferente. Para que você possa enviar uma mensagem criptografada para uma pessoa, você deverá possuir a ***chave pública*** dela e ela deverá ter a sua ***chave pública***. Desta forma, só o destinatário poderá ler a mensagem.

Mas então, como se cria está tal ***chave pública*** ?? Para responder está mensagem, devemos baixar o ***GPA***. Então vamos lá.

## Baixando e instalando o GPA

O ***GPA*** é multiplataforma e está disponivel para ***Linux, Windows*** e diversos outros sistemas operácionais. Você pode baixar o ***GPA*** para o Windows, clicando [neste link](http://www.gpg4win.org/ "GPA para o Windows"). Se você utiliza alguma distribuição Linux, de este comando:

***ArchLinux e derivados***:

~~~
$ sudo pacman -S gpa
~~~

***Debian e derivados***:

~~~
$ sudo apt install gpa
~~~

Depois de ter instalado o ***GPA*** no teu sistema, devemos abri-lo. Tanto no Linux quando no Windows, é só ir até o menu e procurar por ***GPA***.

## Utilizando o GPA

Logo quando você abrir o ***GPA***, deverá aparecer esta mensagem:

![GPA](/assets/img/gpa.png)

Você deverá clicar em "***Gerar chave agora***", para poder gerar uma nova chave. Depois de clicar, deverá aparecer algo parecido com isto:

![GPA](/assets/img/gpa2.png)

Você deverá digitar o teu nome, depois clicar em avançar e irá aparecer esta tela:

![GPA](/assets/img/gpa3.png)

Você terá que colocar o endereço do teu email ali, por exemplo, "***linuxroot1@protonmail.com***". Depois de digitar o teu email, clique em "***Avançar***". Depois irá aparecer esta tela:

![GPA](/assets/img/gpa4.png)

A opção "***Criar uma cópia de backup***" já estará marcada, deixa ela ***MARCADA*** e clique em avançar. Depois de clicar em "***Avançar***", você deverá digitar uma senha e repeti-la e depois clicar em "***ok***". Depois de clicar em "***ok***", espere um tempo, para que tua chave possa ser gerada.

Agora que você já tem a tua chave gerada, para você poder enviar um email para alguém, você deverá possuir a ***chave pública*** deste alguém e este alguém deverá possuir também a tua chave pública. Mas então, como posso enviar minha chave pública para ele? Isto é bastante simples. Você deverá clicar com o botão direito na tua chave e depois clicar em "***Export keys...***". Depois de exportar tua chave para um arquivo, você deverá mandar este arquivo para a pessoa na qual você quer mandar o email e esta pessoa deverá mandar também a ***chave pública*** dela para você. Quando você receber a ***chave pública*** da pessoa, você deverá importa-la para o ***GPA***. Para isto, clique no menu superior em "***Keys***" e depois clique em "***Import Keys...***" e selecione o arquivo da key da pessoa. É bastante simples isto.

Mas então, já criei minha chave, importei a cheve da outra pessoa e agora, como posso enviar uma mensagem para a pessoa? Isto também é bastante simples. Você deverá ir até o menu superior e clicar em "***Windows***" e depois em "***Clipboard***". Depois disso, irá abrir o clipboard:

![Clipboard](/assets/img/clip.png)

No clipboard, você deverá digitar a tua mensagem. Depois de digitar tua mensagem, você deverá ir até o menu superior e clicar em "***File***" e depois em "***Assinar***", logo após, clique na tua chave e digite a sua senha. Agora, devemos criptografar a mensagem, para isto, vá até o menu superior e clique em "***File***" e logo após em "***Encriptar***". Agora, clique na ***chave pública*** do teu amigo e depois em "***Ok***".

![Chave](/assets/img/chave.png)

Agora, a mensagem já está criptografada, agora só mandar a mensagem criptografada por email para o teu amigo.

Agora que o teu amigo recebeu a mensagem criptografada, como ele poderá descriptografar a mensagem ?? Fácil, só ela ir até o clipboard e colar a mensagem criptografada, depois ir até o menu superior e clicar em "***File***" e em seguida, clicar em "***Decrypy***" ou "***Descriptografar***". Fácil, agora você deporá ver a mensagem que o teu amigo lhe enviou.

Para cada mensagem enviada, a mensagem criptografada será completamente diferente.

# Final

E este foi o post de hoje, espero que vocês tenham gostado. Se você quiser, existem diversos plugins de email, como o [Enigmail](https://www.enigmail.net/index.php/en/ "Enigmail").

[GnuPG](https://gnupg.org/ "GnuPG")

[Lista de front-ends para o GnuPG](https://gnupg.org/software/swlist.html "Lista de front-ends para o GnuPG")

[GPA for Windows](http://www.gpg4win.org/ "GPA para o Windows")

[Enigmail](http://www.enigmail.net/ "Enigmail")
