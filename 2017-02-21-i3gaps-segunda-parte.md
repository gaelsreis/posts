---
layout: post
title: "Instalando e configurando o i3gaps no ArchLinux e derivados - 2° Parte" 
image: "assets/img/i3-gaps.jpg"
date: 2017-02-21 21:29:10
tags:
- ArchLinux
- Linux
- i3-gaps
description: "Instalando e configurando o i3gaps no ArchLinux e derivados - 2° Parte"
categories:
- Linux
serie: Linux
---

# Configurando as cores do i3gaps

O **i3gaps** é altamente configuravel, e por isto, hoje, iremos aprender a mudar as cores da barra, do foco das janelas e as workspaces ativas e inativas, então vamos lá.

Vamos, primeiro, alterar o background (plano de fundo) da barra de status. Procure pela linha:

> background #

Depois de procurar pela linha, logo o *"#"* , coloque a cor que desejar.

**Exemplo**:

> background #232323

Desta forma, o *background* da barra será a cor **232323**.

---

Agora, vamos configurar a workspace ativa, para isto, procure pela linha:

> focused_workspace

Vamos então mudar as cores, da seguinte forma:

> focused_workspace #cor #cor #cor

**Exemplo**:

> focused_workspace #232323 #aa4d29 #FFFFFF

---

# Configurando a cor do foco de janelas

Para mudar a cor do fodo das janelas abertas, é só procurar pela linha:

> clien.focused

E trocar pelas cores que desejar.

Exemplo:

> client.focused #232323 #aa4d29 #fdf6e3 $859900

---

# Configurando o i3gaps com as funcionalidades do i3gaps

O **i3gaps** é uma fork não oficial do **i3wm** e tem diversas funcionalidas que o **i3wm** não tem, então, agora vamos configurar o **i3gaps** com estas funcionalidades.

No final do arquivo de configurações do **i3gaps**, adicione a seguinte linha:

> gaps inner 8

> gaps outer 10

Estas linhas é para dar o espaço entre as janelas abertas.

Se você deseja usar este espaço apenas quando estiver mais de uma janela aberta, adicione a seguinte linha:

> smart_gaps on

Se não quiser, coloque *off*

> smart_gaps off

Para colocar bordas apenas se tiver mais de uma janela ativa, adicione a seguinte linha:

> smart_borders on

Para usar bordas quando estiver 1 janela ativa, coloque *off*:

> smart_borders off

Para colocar bordas nas janelas ativas, adicione a seguinte linha:

> for_window [class="^.*"] border pixel 2

Desta forma, estaremos setando o tamanho da bordar, que é de 2 pixels. Você pode colocar o que desejar.

---

# Links

[i3gaps](https://github.com/Airblader/i3 "i3gaps")
[i3status_git](https://github.com/i3/i3status "i3status github")
[i3status](https://i3wm.org/i3status "i3status")

---

E é isto pessoal, para quem desejar ver a minha configuração do **i3gaps** só ir [neste link](https://github.com/linuxroot1/i3gaps "github i3gaps")

:)
