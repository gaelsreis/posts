---
layout: post
title: "Criando site na ZeroNet"
image: ''
date: 2017-03-26 10:13:14
tags:
- Privacidade
- Segurança
- DeepWeb
- OpenSource
- Criptografia
description: "Criando um site na ZeroNet"
categories:
- DeepWeb
serie: DeepWeb
---

# Introdução

No [primeiro post sobre a ZeroNet](https://linuxroot1.github.io/ZeroNet/ "ZeroNet"), eu dei uma breve explicação sobre o que era a **ZeroNet** e como usa-la. No post de hoje, irei ensinar a como criar um site na **ZeroNet**. Eu irei criar um site simples, apenas com uma *index*. Não será nada muito elaborado, pois eu não sei HTML/CSS. Então vamos lá.

## Criando o site

Primeiramente, devemos ir até a pasta onde a ZeroNet está. Depois de ir até a pasta, iremos executar o seguinte comando:

~~~
$ ./ZeroNet.sh siteCreate
~~~

Algo parecido com isto irá aparecer:

~~~
- Starting ZeroNet...
- OpenSSL loaded, version: 01000207F
- Version: 0.5.3 r2004, Python 2.7.11 |Continuum Analytics, Inc.| (default, Dec  6 2015, 18:08:32) 
[GCC 4.4.7 20120313 (Red Hat 4.4.7-1)], Gevent: 1.0.2
- Generating new privatekey...
- ----------------------------------------------------------------------
- Site private key: 5Ja2kRdq4DdFRqgGywbLkuozBp1GFQnACBcma3TE1sJtZ7z17JW
-                   !!! ^ Save it now, required to modify the site ^ !!!
- Site address:     1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL78
- ----------------------------------------------------------------------
? Have you secured your private key? (yes, no) > yes
~~~

Digite "yes" e depois irá aparecer algo assim:

~~~
- Starting ZeroNet...
- OpenSSL loaded, version: 01000207F
- Version: 0.5.3 r2004, Python 2.7.11 |Continuum Analytics, Inc.| (default, Dec  6 2015, 18:08:32) 
[GCC 4.4.7 20120313 (Red Hat 4.4.7-1)], Gevent: 1.0.2
- Generating new privatekey...
- ----------------------------------------------------------------------
- Site private key: 5Ja2kRdq4DdFRqgGywbLkuozBp1GFQnACBcma3TE1sJtZ7z17JW
-                   !!! ^ Save it now, required to modify the site ^ !!!
- Site address:     1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL78
- ----------------------------------------------------------------------
? Have you secured your private key? (yes, no) > yes
- Creating directory structure...
- Creating content.json...
Site:1LMF3W..UL78 Content.json not exist: data/1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL78/content.json
Site:1LMF3W..UL78 File content.json not exist yet, loading default values...
Site:1LMF3W..UL78 Opening site data directory: data/1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL78/...
Site:1LMF3W..UL78 - index.html (SHA512: e5f5379afbd78a49b7d557d1d757fbb3650080539b7a25172cceaab21c709940)
Site:1LMF3W..UL78 Adding timestamp and sha512sums to new content.json...
Site:1LMF3W..UL78 Verifying private key...
Site:1LMF3W..UL78 Correct 1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL78 in valid signers: ['1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL78']
Site:1LMF3W..UL78 Signing content.json...
Site:1LMF3W..UL78 Saving to content.json...
Site:1LMF3W..UL78 File content.json signed!
- Site created!
~~~

Depois de aparecer no final, "**- Site created!**", vamos até a **ZeroNet**, que está dentro do diretorio que você está agora:

~~~
$ cd ZeroNet/data/
~~~

Depois, pegue o endereço onde está escrito:

~~~
- Site address:     1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL78
~~~

Logo após o "*- Site address:*", pegue o endereço que está ali e copie, depois, de o seguinte comando:

~~~
$ cd 1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL78
~~~

Dentro do diretorio, provavelmente, estará criado uma *index.html* e mais outros arquivos, apague todos os arquivos dali. Depois crie uma nova *index.html*.

Eu irei criar uma index básica aqui.

~~~
<h1>Olá pessoas que usam a ZeroNet. Este é o meu site de teste!</h1>
</br>
</br>
</br>
<h2>Este site não é muito relevante, é apenas para fins de teste.</h2>
~~~

Depois de criar todo o site, vamos iniciar a ZeroNet.

~~~
$ cd .. && cd .. && cd ..
~~~

Agora, vamos inicar realmente a **ZeroNet**:

~~~
$ ./ZeroNet.sh
~~~

Agora, vamos até o endereço do teu site. No meu caso, o endereço do meu site é este:

~~~
http://127.0.0.1:43110/1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL78
~~~

E veja que o teu site foi criado:

![ZeroNet Site](/assets/img/ZeroNet.png "ZeroNet Site")

# Modificando o site

Agora, vamos colocar o site realmente para funcionar.

Primeiramente, iremos dar o comando:

~~~
$ ./ZeroNet.sh siteSign 1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL78
~~~

Irá aparecer algo parecido com isto:

~~~
- Starting ZeroNet...
- OpenSSL loaded, version: 01000207F
- Version: 0.5.3 r2004, Python 2.7.11 |Continuum Analytics, Inc.| (default, Dec  6 2015, 18:08:32) 
[GCC 4.4.7 20120313 (Red Hat 4.4.7-1)], Gevent: 1.0.2
SiteManager Deleting orphan site from content.db: 1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL80
- Signing site: 1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL78...
Private key (input hidden):
~~~

Onde está escrito "*Private Key*", tu deve pegar a tua key privada, no meu caso, a minha é:

~~~
5Ja2kRdq4DdFRqgGywbLkuozBp1GFQnACBcma3TE1sJtZ7z17JW
~~~

Depois de colocar a tua key privada, irá aparecer algo assim:

~~~
- Starting ZeroNet...
- OpenSSL loaded, version: 01000207F
- Version: 0.5.3 r2004, Python 2.7.11 |Continuum Analytics, Inc.| (default, Dec  6 2015, 18:08:32) 
[GCC 4.4.7 20120313 (Red Hat 4.4.7-1)], Gevent: 1.0.2
SiteManager Deleting orphan site from content.db: 1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL80
- Signing site: 1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL78...
Private key (input hidden):
Site:1LMF3W..UL78 Opening site data directory: data/1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL78/...
Site:1LMF3W..UL78 - [SKIPPED] content.json
Site:1LMF3W..UL78 - index.html (SHA512: b86118089099ad45936a2003549ef2924cced9fd002c965e8e6064af7f386ce3)
Site:1LMF3W..UL78 - i3.png (SHA512: 9bc82c0723cc6f96ccfa6961335dd778f121227f8d460cdb0bf3889efa1590db)
Site:1LMF3W..UL78 - Honeypot.pdf (SHA512: dc2628a208cf5d5c70864c4778263de9ded5881479593ce126d9e49ed37d6321)
Site:1LMF3W..UL78 - ZeroNet.png (SHA512: 89337f282ee4774f48a4ff50c8a9fc4cae05410492170909d18e2405b21b7153)
Site:1LMF3W..UL78 Adding timestamp and sha512sums to new content.json...
Site:1LMF3W..UL78 Verifying private key...
Site:1LMF3W..UL78 Correct 1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL78 in valid signers: ['1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL78']
Site:1LMF3W..UL78 Signing content.json...
Site:1LMF3W..UL78 Saving to content.json...
Site:1LMF3W..UL78 File content.json signed!
~~~

Agora, iremos dar este comando:

~~~
$ ./ZeroNet.sh sitePublish 1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL78
~~~

Irá aparecer algo parecido com isto:

~~~
- Starting ZeroNet...
- OpenSSL loaded, version: 01000207F
- Version: 0.5.3 r2004, Python 2.7.11 |Continuum Analytics, Inc.| (default, Dec  6 2015, 18:08:32) 
[GCC 4.4.7 20120313 (Red Hat 4.4.7-1)], Gevent: 1.0.2
SiteManager Deleting orphan site from content.db: 1LMF3W3URyKP9EC34uYM3zi3uZ77z1UL81
- Loading site...
- Creating FileServer....
TorManager Tor controller connect error: error: [Errno 111] Connection refused in TorManager.py line 159 > socket.py line 344
FileServer StreamServer bind error, must be running already: [Errno 98] Address already in use: ('0.0.0.0', 15441)
- Sending siteReload
- {'to': 1, 'cmd': 'response', 'ok': 'Reloaded'}
- Sending sitePublish
- {'to': 2, 'cmd': 'response', 'ok': 'Successfuly published to 0 peers'}
- Done.
~~~

Agora, teu site já está público e qualquer um pode acessa-lo.

## Final

Este foi um post meu ensinando a como criar um site na **ZeroNet**. Se você gostou, compartilhe. Creio que em breve irei fazer um video em um canal no Youtube ensinando a como criar um site na ZeroNet.
