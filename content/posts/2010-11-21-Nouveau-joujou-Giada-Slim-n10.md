---
layout: post
date: 2010-11-21
title: "Nouveau joujou : Giada Slim n10"
aliases:
- "/Lifehacks/2010/11/21/Nouveau-joujou-Giada-Slim-n10"
categories:
- Lifehacks
---
J'ai acheté un [Giada Slim n10](http://www.giadatech.com/index.php?app=product&act=show&id=37). Ça ressemble à ça :

![Giada Slim n10](/public/giada.jpg)

J'ai commencé à jouer avec en installant dessus :

* une debian (pas de problème particulier)
* [OpenSSH](http://www.openssh.com/), évidemment
* [Bip](http://bip.milkypond.org/), un proxy IRC
* [Nginx](http://wiki.nginx.org/Main), un serveur web
* [Sllh](http://www.rutschle.net/tech/sslh.shtml) pour avoir ssh ET https sur le port 443.

L'achat est tout neuf, donc je n'ai pas encore beaucoup de recul, mais dans l'ensemble, j'en suis très satisfait. Un seul regret, le ventilo n'est pas aussi silencieux que je le voudrais. J'ai trouvé sur [un forum](http://www.blogeee.net/forum/viewtopic.php?p=209248#p209248) comment régler ça dans le bios, mais ce n'est pas encore parfait. Pour mémoire, ça se règle dans le menu chipset > MCP fan control, et les valeurs à renseigner sont :

* SMART Fan0 Min temperature : 40 (la valeur se modifie avec les touches + et -)
* SMART Fan0 Max temperature : 90
* SMART Fan0 Min duty cycle : 30
* SMART Fan0 Max duty cycle : 255
