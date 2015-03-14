---
date: 2015-03-13
title: "Hash Code, fnf-detect et HTML Truncator"
categories:
- code
---

## Hash Code 2015

Google France organise un concours nommé [Hash
Code](https://sites.google.com/site/hashcode2015/home). J'ai participé avec 2
colllègues d'af83 à l'édition 2015. Les qualifications pour la finale avait
lieu hier soir. [Les
règles](https://docs.google.com/a/google.com/file/d/0B8xe9y1rGAQXRXZjSXl6THBDZXc/view?sle=true)
sont assez simples : il faut disposer des serveurs dans un datacenter de la
meilleure façon possible pour résister aux pannes d'électricité.

Notre code est disponible sur
[github.com/AF83/hashcode-2015](https://github.com/AF83/hashcode-2015). Il
fonctionne de la façon suivante :

1. Lire les données du problème

2. Placer les serveurs dans le datacenter
   1. Trier les serveurs par efficacité décroissante (le rapport entre la
      capacité et la place qu'il prend)
   2. Pour chaque serveur, parcourir les lignes de la moins remplie à la plus
      remplie, et regarder s'il y a un emplacement pour le mettre
   3. S'il y a un emplacement, mettre le serveur dans cet emplacement
   4. Passer au serveur suivant

3. Puis, on assigne les serveurs à des groupes
   1. Trier les serveurs par capacité décroissante
   2. Pour chaque serveur, trouver le groupe avec la capacité garantie la plus
      faible et qui ne soit pas déjà très présent sur la ligne du serveur
   3. Assigner le serveur à ce groupe

4. Écrire notre solution

Avec ce fonctionnement et quelques ajustements, nous avons obtenu le score
très honorable de 379. Nous avons ensuite essayé d'ajouter une phase
d'optimisation entre les étapes 3 et 4, en échangeant des serveurs entre 2
groupes. Mais cela a été un échec : nous avons obtenu de moins bons résultats
que précédement.

Bref, ce fût une soirée bien fun et j'espère que nous serons qualifiés pour la
finale.

**Mise à jour** : oui, nous sommes bien qualifiés pour la finale !


## fnf-detect

J'ai joué un peu avec des bibliothèques de _Computer Vision_ la semaine
dernière. Je me suis servi d'[OpenCV](http://opencv.org/) et de
[ccv](http://libccv.org/) pour détecter des visages sur les photos. Cela
permet ensuite de retailler les photos en gardant les visages dessus, même
quand ces visages sont sur les bords.

Le fruit de ces expérimentations est visible sur [le dépôt
fnf-detect](https://github.com/AF83/fnf-detect). La version avec OpenCV donne
des résultats corrects et est rapide. La version avec ccv est un peu plus
lente, mais améliore grandement les résultats. Au final, nous allons utiliser
cette seconde version pour un client, car cela donne un aspect mieux fini à
leur produit.


## HTML Truncator

[HTML Truncator](https://github.com/nono/HTML-Truncator), ma bibliothèque Ruby
pour tronquer des textes présents sous forme d'HTML, semble être de plus en
plus utilisée. J'ai des retours via les issues de github. Certains sont des
questions, mais j'ai également eu un rapport de bug sur les entités HTML
récemment. J'ai donc corrigé le bug et sorti une nouvelle version.
