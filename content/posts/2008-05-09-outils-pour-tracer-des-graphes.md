---
layout: post
date: 2008-05-09
title: "Outils pour tracer des graphes"
aliases:
- "/Outils/2008/05/09/outils-pour-tracer-des-graphes"
categories:
- Outils
---
Je cherche depuis un certain temps un outil pour tracer des graphes.
En général, j'utilise la suite [Graphviz](http://www.graphviz.org/) pour faire cela.
Le principe est relativement simple : on décrit le graphe dans un fichier au format dot, puis on utilise un des 5 outils (dot, neato, fdp, circo et twopi) pour générer une image.
Cela marche plutôt bien, mais les graphes générés sont sobres, pour ne pas dire moches (voir la [galerie](http://www.graphviz.org/Gallery.php)).

Je connaissais également [LGL](http://www.opte.org/maps/), mais il est surtout adapté pour tracer des graphes avec beaucoup de noeuds et/ou arêtes.
Il existe aussi des outils pour tracer des diagrammes (genre [Dia](http://live.gnome.org/Dia)) qui peuvent être utilisés pour tracer des graphes, mais je préfère de loin l'approche de graphviz.

Et récemment, je suis tombé sur [Nodebox](http://nodebox.net/code/index.php/Graphing) : le choc, des jolis graphes !
Malheureusement, Nodebox fonctionne sous MacOSX.
Il existe bien [un port pour GNU/Linux sous QT](http://dev.nodebox.net/wiki/Qt), mais je n'arrive pas à utiliser le module Graph avec celui-ci :/
[Shoebox](http://shoebox.sollec.org/) est une réécriture de nodebox (sous Cairo ce coup-ci), mais j'ai l'impression qu'il n'est pas encore assez avancé pour faire quelque chose d'utile avec.

Toujours à partir de Nodebox, j'ai découvert [NetworkX](https://networkx.lanl.gov/wiki), mais, si j'ai bien compris, c'est une surcouche à Graphviz.
[Les exemples de la gallerie](https://networkx.lanl.gov/wiki/gallery) me semblent quand même plus jolis que ceux de GraphViz.
Est-ce que l'auteur de NetworkX a passé du temps pour faire ces exemples ou est-ce que je me suis trompé sur NetworkX ?
Je ne saurais dire, mais cela vaudrait sûrement le coup que j'y rejette un coup d'oeil à l'occasion.

Enfin, la solution viendra peut être du Javascript.
Le [JavaScript Information Visualization Toolkit (JIT)](http://blog.thejit.org/?page_id=14) est une bibliothèque pour tracer des graphes.
Ce n'est pas aussi simple que GraphViz et, pour le moment, limité aux arbres, mais cela pourrait devenir une solution intéressante.
Le projet [Processing.js](http://dev.jquery.com/~john/processing.js/) montre que l'on peut utiliser la balise Canvas pour faire un rendu qui n'a rien à envier au Desktop.
Alors qui sait, peut être que JIT pourra vraiment devenir la solution pour tracer de jolis graphes même si l'utilisation de javascript peut surprendre pour cela...
