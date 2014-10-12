---
layout: post
date: 2011-06-27
title: "Rails ou Sinatra ?"
aliases:
- "/Rails/2011/06/27/Rails-ou-sinatra"
categories:
- Rails
---
[Ruby on Rails](http://rubyonrails.org/) ou
[Sinatra](http://www.sinatrarb.com/), comment choisir entre les deux ? C'est
une question que j'entends régulièrement et pour laquelle, je suis toujours un
peu embêté d'avoir un pointeur tout prêt vers un article qui expliquerait
cela. Encore aujourd'hui, la question [m'a été
posée](https://twitter.com/#!/delaBruyne/status/85433554179342336) et j'ai eu
beau chercher, je n'ai rien trouvé de bien concluant.

On est jamais mieux servi que par soi-même, et c'est donc l'occasion de
réveiller ce blog qui commençait à prendre la poussière.

Donc Rails ou Sinatra ? Ça dépend mais la plupart du temps, il est assez
facile de choisir l'un ou l'autre. Ils ont des philosophies assez différentes
et couvrent ainsi des problématiques différentes.

Commençons par Ruby on Rails. Il a été développé par [David Heinemeier
Hansson](http://en.wikipedia.org/wiki/David_Heinemeier_Hansson) pour
développer des applications web rapidement mais en gardant du code
maintenable. Rails est donc fait pour permettre aux personnes dont le métier
est de construire des applications web (développeurs, intégrateurs, etc.) de
pouvoir faire ça le plus efficacement possible. On retrouve ainsi le
_scaffold_ qui permet de gagner du temps en début de projet et de nombreuses
conventions pour aller plus vite dans les cas courants. Mais cela a aussi des
inconvénients : Rails est un gros framework et apprendre à s'en servir
correctement demande un investissement initial en temps qui est loin d'être
négligeable. Si on veut vraiment être efficace, il faut respecter l'_esprit_
de Ruby on Rails et ses manières de faire, mais aussi connaître les
bibliothèques qui vont bien, les fameuses _gems_ comme
[Devise](https://github.com/plataformatec/devise) ou
[Sass](http://sass-lang.com/).

De l'autre coté, Sinatra a des ambitions toutes autres : il veut juste
permettre à des développeurs Ruby de faire des applications web simples avec
le minimum d'efforts. Cela commence avec une API extrêmement simple qui permet
de démarrer tout de suite sans avoir à apprendre grand chose. Pour cela,
Sinatra se contente du minimum et n'essaye pas d'offrir plein de choses dès le
départ. C'est ainsi un projet avec une taille beaucoup plus réduite mais qui
offre plus de libertés. Là où les projets Rails sont toujours organisés d'une
façon semblables pour permettre aux développeurs et intégrateurs de passer
facilement d'un projet à l'autre, Sinatra est bien plus souple et peut, par
exemple, venir ajouter une interface web à un projet déjà existant. Sa
simplicité est également intéressante pour les débutants qui peuvent ainsi
[faire très rapidement des choses](http://www.sinatrarb.com/intro-fr.html)
sans avoir, au préalable, à lire un bouquin complet. Et rien n'interdit de
passer à Rails plus tard.

Pour résumer, Ruby on Rails est un rouleur compresseur qui permet de
construire très rapidement des applications web de qualité pour les personnes
dont c'est le métier, alors que Sinatra couvre d'autres besoins : il permet de
découvrir Ruby ou le développement web en douceur pour les débutants et offre
une souplesse incroyable pour les hackers confirmés.

