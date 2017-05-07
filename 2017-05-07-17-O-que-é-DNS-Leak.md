---
layout: post
title: "O que é DNS Leak?"
image: ''
date: 2017-05-07
tags:
- Privacidade
- Segurança
- VPN
- DNS
- DNS Leak
description: "O que é o DNS Leak?"
categories:
- Privacidade
serie: Privacidade na internet
---

# Introdução

O ***DNS Leak*** é uma grande ameaça para quem utiliza uma VPN. E irei explicar o que é ele.

## O que é?

O ***DNS Leak*** é uma falha de segurança que permite que o verdadeiro endereço de IP seja descoberto.

O ***DNS*** (*Domain Name System*) é um sistema de gerenciamento de nomes hierárquico e distribuido para computadores. Se você não entendeu, deixe eu explicar melhor, com um exemplo.

Quando você acessa um determinado site, como por exemplo o *google.com*, você digita o endereço dele que no caso é "*google.com*", você é direcionado para o site do Google. O **DNS** serve exatamente para isto, para ao invés de tu ter que digitar o IP do Google, você apenas digitar o endereço dele e ele irá lhe levar ao site, levando os pacotes de internet até o IP do Google. Sem o **DNS** não seria possivel acessarmos o endereço "*google.com*" ou outros endereços.

Agora que entendemos o que é o **DNS**, vamos entender o ***DNS Leak***.

O ***DNS Leak*** ocorre quando o usuário acessa um site e o determina o endereço de IP verdadeiro do usuário usando o WebRTC, que é usado na maioria dos browsers.

Sob certas condições, mesmo quando se utiliza uma VPN, o OS (Operation System) utiliza os seus servidores DNS padrões em vez dos servidores DNS da VPN.

![DNS Leak](/assets/img/what-is-a-dns-leak.png)

## Como posso saber se estou sofrendo de DNS Leak.

Você pode verificar se você está sofrendo de DNS Leak através do site [DNS Leak Test](https://dnsleaktest.com/ "DNS Leak Teste"), [IpLeak](https://ipleak.net/ "IP Leak") e outros serviços.

Quando é detectado um ***DNS Leak***, você tem duas opções, trocar a tua VPN ou utilizar o ***DNSCrypt-Proxy***, na qual já ensinei a instalar e configurar [aqui](https://linuxroot1.github.io/DNSCRYPT-Proxy/ "Instalando e configurando o DNSCrypt-Proxy").

# Final

E este foi o post de hoje, espero que tenham gostado e entendo o grande risco que corremos ao utilizar uma VPN na qual da ****DNS Leak***.

[DNS Leak - Wikipedia](https://en.wikipedia.org/wiki/DNS_leak "DNS Leak")

[O que é DNS Leak e porque devo me importar?](https://dnsleaktest.com/what-is-a-dns-leak.html "O que é DNS Leak e porque devo me importar?")

[Instalando e configurando o DNSCrypt-Proxy](https://linuxroot1.github.io/DNSCRYPT-Proxy/ "Instalando e configurando o DNSCrypt-Proxy")
