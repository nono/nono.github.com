---
layout: post
date: 2008-12-02
title: "Le navigateur web Arora"
aliases:
- "/Outils/2008/12/02/la-navigateur-web-Aroha"
categories:
- Outils
---
J'ai récemment eu besoin de résoudre des bugs sur [LinuxFr.org](http://linuxfr.org/) qui était lié au moteur javascript de Safari
(les [#883](https://linuxfr.org/tracker/883.html) et [#900](https://linuxfr.org/tracker/900.html) si vous voulez tout savoir).
Étant sous GNU/Linux, je ne pouvais pas installer Safari, et bien entendu, je n'arrivais pas à reproduire les bugs sous Firefox.
Toutefois, le moteur de Safari, Webkit, est libre, et il en existe des ports sous GNU/Linux.

J'ai d'abord essayé epiphany-webkit, et j'ai pu constaté le problème mais pas faire grand chose de plus.
Epiphany ne me donnait pas accès à un débugger javascript et ne me donnait même pas accès à l'erreur js.
Après une phase de recherche sur google, j'ai tenté un navigateur web que je ne connaissais pas (même de nom) : [Aroha](http://code.google.com/p/arora/).
Il dispose de l'outil [Web Inspector](http://mapopa.blogspot.com/2008/07/enabling-webkits-webinspector-in-arora.html) (en gros, un équivalent de Firebug pour Safari), ce qui m'a donné l'erreur javascript et permis de faire quelques tests dans la console intégrée.
Bref, même si ce navigateur n'a rien de révolutionnaire, je suis bien content de pouvoir utiliser le Web Inspector de Webkit sous linux.
