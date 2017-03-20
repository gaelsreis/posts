---
layout: post
title: "IPFS, o que é e como usa-lo?"
image: ''
date: 2017-03-20 10:50
tags:
- Privacidade
- Anonimato
- Segurança
- Software Livre
description: "IPFS, o que é? Como funciona? Como usa-lo?"
categories:
- Privacidade
serie: Privacidade na internet.

![ipfs](/assets/img/ipfs.jpg)

## Introdução

O [ipfs](https://ipfs.io "ipfs")(Inter-Planetary File System) é um protocolo peer-to-peer (p2p), para tornar a naveção na web mais rápida, segura e aberta. Tem diversas implementações já existentes.



# IPFS x HTTP

Algumas vantagnes do **ipfs** em relação ao **HTTP** são:

**HTTP** é inecifiente e caro. O HTTP faz o download de um arquivo de um único computador de cada vez, em vez de pegar de peças de vários computadores simultaneamente. Com a entrega de vídeo, uma abordagem P2P poderia economizar 60% em custos de largura de banda.

**IPFS** é mais segura, por ser p2p, reduzindo assim o controle e centralização do poder. Além da **IPFS** ser OpenSource e ter diversas implementações.

A **IPFS** também pode ser usada como uma espécie de nuvem (cloud) P2P, onde você pode subir (upar) arquivos e o **IPFS** gera um link para você poder mandar para outras pessoas ou para você baixar o arquivo em outro computador, o que é bem legal.

Pela **IPFS** ser P2P, qualquer coisa que você colocar na rede, sempre ficará lá, pois é imuavel, por ser P2P, o que é bem legal. Com isto, você *NUNCA* poderá ser sensurado.

# Como funciona

A **IPFS** é uma rede descentralizada, P2P e muito fácil de usar. Cada arquivo e todos os blocos dentro dele são dados de impressão digital única chamada um Hash criptográfico.

Cada arquivo existente no **IPFS** teria um hash exclusivo para poder presentá-lo, e qualquer alteração minuciona resultaria em um novo hash sendo gerado.  Esses hashes são como o conteúdo pode ser visto. Um cliente consulta o sistema para um hash e qualquer nó que tenha esse conteúdo disponível pode atendê-lo a pares. O "enxame" fornece uma experiência semelhante a uma torrent, em que os pares são capazes de servir um ao outro conteúdo.

Esse sistema permitirá que o conteúdo seja veiculado de forma rápida e precisa para os clientes, independentemente da proximidade com o host original do conteúdo. Além disso, porque hashes são empregados, ambas as extremidades da troca pode ser verificado para o conteúdo correto, como um único bit fora do lugar resultaria em um hash diferente.

O Sistema de Nomenclatura Interplanetária (IPNS) pode ser usado para atribuir um nome a um conteúdo mutável (mutável), de modo que seu nó publique um pedaço de conteúdo, tenha um nome anexado a ele e então seja capaz de republicar as alterações com o mesmo nome. Isso, naturalmente, pode resultar em perda de conteúdo disponível, de modo IPNS entidades, de acordo com os desenvolvedores, pode algum dia funcionar mais como um Git commit log, permitindo que um cliente iterar de volta através de versões do conteúdo publicado.

# Instalando

Nesta instalação, irei abordar a instalação da **IPFS** no **ArchLinux**, então, se você usa Windows, o método de instalação será um pouco diferente.

Primeiramente, iremos baixar o arquivo do **ipfs**, para isto, iremos até o site do mesmo: https://ipfs.io/docs/install/

Depois, iremos selecionar para qual sistema oeracional iremos baixar, no meu caso é **Linux 64bits**. No meu caso, irei pegar o link do arquivo de download e irei baixar usando o **wget**, então, abra o terminal e de o comando:

> wget https://dist.ipfs.io/go-ipfs/v0.4.7/go-ipfs_v0.4.7_linux-amd64.tar.gz

Agora, iremos descompactar o arquivo:

> tar -xzvf arquivo.tar.gz

Depois de descompactar, iremos até o diretório do mesmo:

> cd go-ipfs

Depois, iremos executar o arquivo "*install.sh*":

> sudo ./install.sh

Agora, o **ipfs** já está instalado, então, vamos usa-lo.

# Usando

Primeiramente, iremos executar o seguinte comando:

> ipfs init

Aparecerá algo parecido com isto:

~~~
initializing IPFS node at /home/USER/.ipfs
generating 2048-bit RSA keypair...done
peer identity: QmWeqpHKFH9hv1ixLomM5CZLHQAbTHnRtopYpPbFrdetiH
to get started, enter:

	ipfs cat /ipfs/QmVLDAhCY3X9P2uRudKAryuQFPM5zqA3Yij1dY8FpGbL7T/readme
~~~

Agora, execute o seguinte comando:

> ipfs /ipfs/hash

OBS: Onde está escrito "**hash**", é a tua hash.

A saida será parecida com esta:

~~~
Hello and Welcome to IPFS!

██╗██████╗ ███████╗███████╗
██║██╔══██╗██╔════╝██╔════╝
██║██████╔╝█████╗  ███████╗
██║██╔═══╝ ██╔══╝  ╚════██║
██║██║     ██║     ███████║
╚═╝╚═╝     ╚═╝     ╚══════╝

If you're seeing this, you have successfully installed
IPFS and are now interfacing with the ipfs merkledag!

 -------------------------------------------------------
| Warning:                                              |
|   This is alpha software. Use at your own discretion! |
|   Much is missing or lacking polish. There are bugs.  |
|   Not yet secure. Read the security notes for more.   |
 -------------------------------------------------------

Check out some of the other files in this directory:

  ./about
  ./help
  ./quick-start     <-- usage examples
  ./readme          <-- this file
  ./security-notes
~~~

Agora, vamos ficar online. Para ficarmos online, precisamos iniciar o daemon do **ipfs**, para isto, execute o comando:

> ipfs daemon

Agora, já estamos online, então podemos jogar alguns arquivos na **ipfs**, para isto, vamos criar um arquivo:

> echo -e "Testando a rede IPFS" > ipfs.txt

Depois de ter o arquivo criado, vamos adicionar ele à **ipfs**:

> ipfs add test.txt

A saida será parecida com esta:

~~~
added Qmdv37GXrDC15ctweMbYr7Rs8y1Rv3QFYBtEJx2uDRqEXY test.txt
~~~

Com isto, o arquivo *test.txt* foi adicionar à **ipfs**. Agora, vamos baixar este arquivo:

> curl "https://ipfs.io/ipfs/hash"

Onde está escrito *hash*, coloque a hash do arquivo.

# Final e links

E este é mais um post, espero que tenham gostado. Se você chegou até aqui, não pare de ler, se você usa algum outro sistema operacional que não seja Linux, então, deixarei alguns links da wiki do **ipfs** para vocês:

[Site oficial](http://ipfs.io/ "IPFS")
[Docs](http://ipfs.io/docs/ "docs")
[Instalação](http://ipfs.io/docs/install/ "Instalação do IPFS para outros sistemas operacionais")
[Usando a IPFS](https://ipfs.io/docs/getting-started "Usando a IPFS")
[GitHub do projeto](https://github.com/ipfs/go-ipfs/ "GitHub IPFS")
