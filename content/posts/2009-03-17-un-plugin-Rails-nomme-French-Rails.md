---
layout: post
date: 2009-03-17
title: "Un plugin RoR nommé FrenchRails"
aliases:
- "/Rails/2009/03/17/un-plugin-Rails-nomm%C3%A9-French-Rails"
categories:
- Rails
---
Comme vous le savez déjà sûrement, je suis en train de re-écrire [LinuxFr.org](http://linuxfr.org) en [Rails](http://rubyonrails.org).
Et quand j'ai montré où j'en étais, on m'a remonté un bug étrange : j'affiche "0 commentaires" avec un s à la fin, ce qui est grammaticalement incorrect.

`<interruption culturelle>`
Pour ceux qui ne sont pas très calés en internationalisation, sachez que les règles qui définissent singulier et pluriel ne sont pas les mêmes selon les langues (en fait, certaines langues ont mêmes plusieurs sortes de pluriels).
En particulier, il y a une différence importante entre le français et l'anglais : en français, 0 est singulier, alors qu'il est pluriel en anglais.
Ruby on Rails utilisant par défaut l'anglais, on comprend mieux d'où vient le 's' à la fin de "0 commentaires".
`</interruption culturelle>`

J'utilise l'helper `pluralize`, et comme Rails a intégré une gestion de l'internationalisation à la version 2.2, je pensais qu'il suffirait de déclarer la locale pour que cela marche.
Hé bien, non.
Première surprise : l'helper `pluralize` ne passe pas par la partie I18n, mais utilise une règle en dure pour savoir si un nombre est singulier ou pluriel.
Bon, ce n'est pas grave, ce n'est pas ça qui va m'arrêter : un petit monkey-patching et c'est réglé.

Sauf que, deuxième surprise, cela ne marche toujours pas !
Le backend d'I18n fourni avec Rails (I18n::Backend::Simple) ne connaît que la règle pour l'anglais, et ne tient donc pas compte de la locale.
Après quelques errements et expérimentations, j'ai réussi à trouver un moyen relativement simple de corriger cela (créer un backend qui hérite de I18n::Backend::Simple, avec juste la méthode pluralize redéfinie).
Et là, joie, ça marche :-)

Comme tout cela m'a pris quelques heures, j'en ai fait un plugin : [FrenchRails](http://github.com/nono/french-rails/tree/master).
J'espère que cela pourra servir à d'autres personnes.
En tout cas, moi, je compte l'utiliser sur plusieurs projets.

Dernière chose : si vous avez des besoins plus compliqués que les miens (au hasard, gérer plusieurs langues), ne cherchez pas à utiliser ce plugin, parter plutôt sur une solution plus costaud comme [Globalize2](http://github.com/joshmh/globalize2/tree/master).
