---
layout: post
title: "Comandos básicos para começar a usar o terminal - Parte 2"
image: ''
date: 2017-02-24 18:47
tags:
- Linux
- Terminal
- Comandos
- Bash
- ZSH
description: "Comandos básicos para começar a usar o terminal - Parte 2"
categories:
- Linux
serie: Linux
---

# Introdução

Dando continuação à nossa [primeira aula sobre](https://linuxroot1.github.io/comandos-b%C3%A1sicos/ "Comandos básicos para começar a usar o terminal - Parte 1"), hoje vamos falar mais sobre alguns comandos que eu considero importante usar no terminal e os comandos que eu mais uso.

---

# Comandos

Um comando amplamente utilizado pelos usuarios é o comando **sudo**, que é usado para dar permissões de um comando para ser executado com permissões de usuário *Root*.

Para usa-lo, deve-se usar a seguinte sintaxe:

> sudo comando

*Exemplo*:

> sudo apt-get install firefox

Neste caso, o comando **apt-get** que é utilizado para instalar programas no Debian e derivados, será executado com permissões do usuário *Root*.

---

O comando **mv** é para mover arquivos de um diretorio para o outro:

> mv ~/script.sh ~/scripts/

Desta forma, o arquivo *script.sh* que está em */home/user* será movida para a */home/user/scripts/*.

---

O comando **cp** serve para copiar arquivos de um diretorio para o outro:

> cp ~/scripts/script.sh ~/Documentos

Desta maneira, o arquivo que *script.sh* que está em */home/user/scripts/* será copiado para o diretorio */home/user/Documentos*.

Para copiar um diretorio inteiro, só usar o comando **cp** com o parametro **-r**:

> cp -r ~/scripts/ ~/Documentos

Desta forma, toda o diretorio */home/user/scripts/* será copiado para a */home/scripts/Documentos*.

---

O comando **lsblk** é para ver as partições existentes no computador:

> lsblk

saida será parecido com esta:

~~~
NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
sda      8:0    0 465,8G  0 disk 
├─sda1   8:1    0   100M  0 part 
├─sda2   8:2    0 231,3G  0 part 
├─sda3   8:3    0     1K  0 part 
├─sda5   8:5    0  30,5G  0 part /
├─sda6   8:6    0  89,6G  0 part /home
├─sda7   8:7    0    55G  0 part 
└─sda8   8:8    0     2G  0 part 
sr0     11:0    1   1,2M  0 rom  
~~~

Na saida do comando **lsblk** é mostrado todas as partições existentes e quais partições estão montadas, que nesta caso é a partição */dev/sda5* & */dev/sda6*.

---

Se você deseja ver as partições mas não quer usar o comando **lsblk**, só usar o **fdisk**:

> fdisk -l

A saida do comando será semelhante a esta:

~~~
Disco /dev/sda: 465,8 GiB, 500107862016 bytes, 976773168 setores
Unidades: setor de 1 * 512 = 512 bytes
Tamanho de setor (lógico/físico): 512 bytes / 4096 bytes
Tamanho E/S (mínimo/ótimo): 4096 bytes / 4096 bytes
Tipo de rótulo do disco: dos
Identificador do disco: 0x932b1549

Dispositivo Inicializar    Início       Fim   Setores Tamanho Id Tipo
/dev/sda1   *                2048    206847    204800    100M  7 HPFS/NTFS/exFAT
/dev/sda2                  206848 485251071 485044224  231,3G  7 HPFS/NTFS/exFAT
/dev/sda3               485253101 976771071 491517971  234,4G  f Estendida W95 (LBA)
/dev/sda5   *           485253120 549136383  63883264   30,5G 83 Linux
/dev/sda6               549138432 737101823 187963392   89,6G 83 Linux
/dev/sda7   *           857208832 972598143 115389312     55G 83 Linux
/dev/sda8               972601344 976771071   4169728      2G 82 Linux swap / Solaris

A partição 3 não inicia em um limite de setor físico.
~~~
---

O comando **ls**, assim como mostrado na primeira parte do post, é para ver os arquivos de um diretorio, mas ele mostra apenas os arquivos que podem ser vistos e não mostra os arquivos ocultos, mas existe uma maneira de ver estes arquivos:

> ls -a

*Ou*:

> lsa

Com o comando **ls -a**, será mostrado apenas os arquivos ocultos, e com o comando **lsa** será mostrados **todos** os arquivos, inclusive os arquivos ocultos.

---

O comando **rm**, é um comando muito util e serve para apagar diretorios e arquivos, então, irei mostrar algumas de suas opções:

Para apagar um determinado arquivo, só dar o comando:

> rm -f arquivo

*Exemplo*:

> rm -f ~/scripts/script.sh

Desta forma, o arquivo *script.sh* que esta em */home/user/scripts/* será apagado.

E também é possivel apagar diretorios, só dar o comando:

> rm -rf diretorio

*Exemplo*:

> rm -rf ~/scripts/

Desta forma o diretorio */home/user/scripts* será apagado e todos os seus arquivos juntos.

E há também um comando **muito** perigoso e que muitos users falam para dar este comando, mas se alguém o mandar fazer este comando, não o faça, o comando é:

> sudo rm -rf --no-preserve-root /

Pois desta forma, o diretorio raiz será apagado e tudo o que há dentro dele também e você irá ficar sem o seu sistema. Só de o comando, se você realmente sabe o que está fazendo.

---

Compactar e descompactar arquivos *.zip* no Linux, é muito fácil e só é necessario o **zip** e **unzip** instalado:

Compactar:

> zip nome.zip arquivo

*Exemplo*:

> zip script.zip ~/scripts/script.sh

Desta forma, um arquivo será compactado em ".zip".

Para compactar uma pasta toda, só usar o "-r":

> zip -r nome.zip pasta

*Exemplo*:

> zip -r desktop.zip ~/scripts/

---

Baixar arquivos, páginas e outras coisas no Linux pelo terminal, é fácil e eu realmente uso quase sempre o **wget** e/ou **curl**.

Para usar o **wget** é fácil, esta é a sintaxe:

> wget -opção link

*Exemplo*:

> wget -c http://www.qygjxz.com/data/out/144/4574317-linux-wallpaper.png

O parametro *-c* é para continuar o download mesmo quando é cancelado. É como um *pause* do **Wget**.

---

Para mudar a *password* (senha) do usuario no Linux através do terminal, só dar este comando:

> passwd

E a saida dele será semelhante a esta:

~~~
$ passwd

Mudando senha para User.
Current password:
Nova senha:
~~~

Desta forma, você irá mudar a senha do teu usuario. Se deseja mudar a senha do usuario *Root*, só logar no *Root* e dar o comando **passwd**.

OBS: No comando *passwd* não é mostrado o que está sendo digitado.

---

Se você deseja adicionar um novo usuario ao teu sistema, só usar o comando **useradd**:

> useradd nome_do_user

Desta forma, será adicionar mais um usuario com o nome de **nome_do_user**.

---

O comando **man** é para abrir o manual de um determinado programa:

> man ls

Desta forma, será aberto o manual do comando **ls**. Existe vários outros comandos que tem manual, só ve-lo com o **man**.

---

Para criar diretorios pela shell, existe o comando **mkdir** na qual cria um diretorio no diretorio especificado:

> mkdir diretorio

*Ou*:

> mkdir ~/Desktop/scripts

Desta forma, a pasta *scripts* será criada em */home/user/Desktop*.

---

Para criar arquivos com a shell, só usar o comando **touch**, mas, o comando **touch** não é especificamente para criar arquivos.

> touch arquivo

*Exemplo*:

> touch ~/scripts.sh

Desta meneira, será criado o arquivo *scripts.sh* em */home/user/*.

---

Para exibir a quanto tempo o sistema está rodando, quando ele foi ligado e mais algumas informações, use o comando **uptime**:

> uptime

---

Uma dica que dou aos novatos no mundo Linux que desejam saber algumas informações do sistema, só usar o **screenfetch** ou o **neofetch**.

> screenfetch
Desta forma, o **screenfetch** irá mostrar a quantidade de *RAM* gasta, o *hostname*, o *uptime*, a *versão do kernel* e várias outras informações.

---

# Final e livros

E este é o final do post de hoje, se você gostou, compartilhe nos seus grupos e contatos. E para quem deseja estudar mais sobre Linux e deseja aprender mais comandos, irei deixar alguns *.pdf* aqui.

[Biblia Linux](https://mega.nz/#!BhwHVKSJ!uq1Y60xTDBOQJq7D36Iy5E32aEe3S0cl4dqSwOkVH6Q "Biblia Linux pdf")
[Certificação Linux LPI 1](https://mega.nz/#!k95hRJKD!88YYQr00MUpBXeu6jULQHRGu7ygU1Xqw6uhKujdtWFc "Certificação Linux LPI 1")
[Certificação Linux LPI 2](https://mega.nz/#!90p3ACAR!SjoO5aTeN1yit5j3N2P_7EOYdfV8tP0xJ2s_-ybV_mE "Certificação Linux LPI 2")
[Manual Linux Completo](https://mega.nz/#!EsBR3B6S!2E-5ffn_sF-AXNkYq-gw9y1euDXEX_rNSteL5blxybM "Manual Linux Completo")
[Caixa de ferramentas Unix](https://github.com/gabrielscosta/caixaDeFerramentasDoUnix "Caixa de ferramentas Unix")
