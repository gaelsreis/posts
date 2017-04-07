---
layout: post
title: "Vim - Como configurar"
image: ''
date: 2017-04-07 16:59:17
tags:
- Linux
- Terminal
- Vim
description: "O vim é um ótimo editor de texto, e hoje iremos aprender a como configura-lo."
categories:
- Linux
serie: Linux
---

# Introdução

Dando continuação ao [último post](https://linuxroot1.github.io/Vim/ "Como usar o Vim"), que falei sobre como usar o **vim**, agora, iremos aprender a como configurar, instalar plugins e etc. Então vamos lá.

## Configurando

O arquivo de configuração do **vim**, o **.vimrc**, geralmente fica na tua */home*, então vamos abrir o teu **.vimrc** e configurar.

~~~
$ vim ~/.vimrc
~~~

No caso de ele não existir, fique tranquilo, é só escrever as configurações normalmente e salvar, que o teu **vim** estará configurado. Então vamos lá configurar ele.

O **set** serve para atribuir valores à variáveis, podem ser colocadas no **.vimrc**:

~~~
set number "Mostra as numerações das linhas
set mouse=a "Ativa configurações do mouse
set history=1000 "Histório de 100 linhas.
syntax on "Habilita as cores.
set aw "Gravação automatica a cada alteração no arquivo
set ts=4 "Número de caracteres do TAB.
~~~

Este é um exemplo básico de como usar o **set** no **.vimrc**. Basta colocar estas linhas no teu **.vimrc**, que o teu **vim** já estará legal.

Os mapeamentos permitem o usuário criar atalhos de teclas para quase tudo. Tudo depende da criatividade do usuário e de quanto ele conhece o **Vim**.

A sintax para criar teclas mapeadas é:

~~~
modo teclas comando
~~~

Exemplo:

~~~
nmap <s-O> :tabnew "Só funciona no modo normal. Quando é apertado as teclas shift + O, é dado o comando "tabnew".
~~~

Com isto, vamos criar alguns atalhos:

~~~
nmap <s-O> :tabnew "Abre uma nova aba.
nmap <c-p> gT "Movimenta entre as abas.
nmap <C-n> gt "Movimenta entre as abas.
nmap <s-c> :tabc "Fecha uma aba.
nmap <C-s> <Esc>:wq!<cr> "Salva e fecha o arquivo.
~~~

# Final

E este foi o post de hoje, espero que tenham gostado. Irei deixar minha configuração do meu **vim**, para quem quiser dar uma olhada. No próximo post, irei ensinar como adicionar os plugins.

Para entender sobre o **set** e sobre **mapeamentos**, recomendo ler [este livro](/assets/livros/vimbook.pdf "PDF"), leia da página 168 até a 185, para poder aprender.

[Vim Book](/assets/livros/vimbook.pdf "PDF")

[Vim - Aurélio](http://aurelio.net/vim/ "Vim")

[Minha configuração do Vim](https://github.com/linuxroot1/dotfiles/blob/master/vim/vimrc "Meu .vimrc")

[Vim - Opções úteis de configuração](http://www.dicas-l.com.br/arquivo/vim_opcoes_uteis_de_configuracao.php#.WOgINGfLdhE "Configurando o Vim")

[Melhorando o visual do Vim](https://www.vivaolinux.com.br/dica/Melhorando-o-visual-do-VIM-(Vi-Improved "Melhorando o visual do Vim")

[Melhorando o editor Vim](http://cooperati.com.br/2012/02/02/melhorando-o-editor-vim/ "Melhorando o editor Vim")


