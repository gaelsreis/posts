---
layout: post
title: "Instalando plugins no Vim"
image: ''
date: 2017-04-08 11:03:15
tags:
- Linux
- Terminal
- Vim
description: "Instalando plugins no editor de texto Vim"
categories:
- Linux
serie: Linux
---

# Introdução

Hoje, iremos aprender a como instalar plugins no **vim**.

Como vocês já sabem, o **vim** é um editor de texto muito poderoso e altamente configurável. Mas para ele se tornar mais poderoso, podemos, além de configurar as keybinds e set, adicionar plugins para deixa-lo cada vez mais legal e poderoso, e é hoje que iremos fazer isto, então vamos lá.

## Instalando o Vundle

Neste tutorial, iremos usar o ***Vundle***, para instalar os plugins. Não irei falar muito sobre o ***Vundle***, por isto irei deixar [este link](https://github.com/VundleVim/Vundle.vim "Vundle"), para você aprender mais sobre ele.

Primeiramente, vamos instalar o ***Vundle***, para isto, você precisa estar com o ***git*** instalado. Então, vamos dar este comando:

~~~
$ git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
~~~

Depois de ter instalado o ***Vundle***, vamos até o arquivo de configuração do **vim**:

~~~
$ vim ~/.vimrc
~~~

No teu arquivo de configuração do **vim**, adicione as seguintes linhas:

~~~
set nocompatible
filetype off
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#bebin()
Plugin 'VundleVim/Vundle.vim'


call vundle#end()
filetype plugin indent on
~~~

Para adicionar os plugins que você deseja, você deve colocar o nome do plugin entre as linhas "***call vundle#begin()*** e ***call vundle#end()***. Desta maneira:

~~~
set nocompatible
filetype off
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#bebin()

Plugin 'plugin/que/deseja'

call vundle#end()
filetype plugin indent on
~~~

Como o ***Vundle*** faz uso do ***Git*** para instalar os plugins, você tem que colocar no "***plugin/que/deseja***", o usuário e o repositório do plugin. Exemplo, quero instalar o plugin "***vim-fugitive***", para isto, preciso ver qual é o usuário e o repositório que ele está no ***GitHub***. No caso, o link para o "***vim-fugitive***" é [este aqui](https://github.com/tpope/vim-fugitive "Vim-Fugitivi GitHub"). Para adicionar este plugin, você deve colocar da seguite forma:

~~~
Plugin 'tpope/vim-fugitive'
Plugin 'tpope/vim-sorround'
~~~

Desta forma, os plugin ***vim-fugitive*** e ***vim-sorround*** irá ser instalado, na próxima vez que você der o comando:

~~~
$ vim +PluginInstall +qall
~~~

Ou se preferir fazer tudo de dentro do **vim**, de este comando de dentro dele:

~~~
:PluginInstall
~~~

Depois deste comando, os plugins serão instalados. O teu arquivo de configuração irá ficar parecido com este:

~~~
set mouse=a "Ativa configurações do mouse
set history=1000
set autoread
set number
syntax enable
set wrap
set laststatus=2
set ai
set ic
set showmatch
set bg=light

" ====== Keybinds ====== 

" ====== Tabs ======
map <s-O> :tabnew 
map <C-p> gT
map <C-n> gt
map <s-c> :tabc
nmap <s-s> <Esc>:split 

" ====== Git Keybinds ======
nmap ga <Esc>:Git add -A<cr>
nmap gs :Gstatus<CR>
nmap gc :Gcommit
nmap gp :Gpush

" Configuração do Vundle
set nocompatible
filetype off
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
Plugin 'VundleVim/Vundle.vim'

" Plugins

" Github Plugin

Plugin 'tpope/vim-fugitive'
Plugin 'tpope/vim-sorround'
call vundle#end()
filetype indent on
~~~

Como você pode perceber, este é o meu arquivo de configuração atual do **vim**, na qual os plugins ***vim-fugitive*** e ***vim-sorround*** estão instalados. Para poder instalar mais plugins, basta pesquisar por novos plugins pelo [DuckDuckGo](https://duckduckgo.com "DuckDuckGo") ou outro buscador de tua preferencia.

Para mais informações sobre o ***Vundle***, de este comando de dentro do **vim**:

~~~
:h vundle
~~~

# Final

E este foi mais um post sobre o **vim**, espero que vocês tenham gostado.

[Vundle Vim](https://github.com/VundleVim/Vundle.vim "Vundle.vim")
