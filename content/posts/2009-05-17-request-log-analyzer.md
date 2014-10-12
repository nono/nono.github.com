---
layout: post
date: 2009-05-17
title: "Request-log-analyzer"
aliases:
- "/Rails/2009/05/17/request-log-analyzer"
categories:
- Rails
---
Dans la série des outils pour Rails que j'apprécie, je vais vous parler de [request-log-analyzer](http://github.com/wvanbergen/request-log-analyzer/tree/master).
Pourquoi lui ? Parce qu'il m'a rendu bien service cette semaine.

Request-log-analyser est un outil très simple qui permet d'analyser les logs de Rails pour découvrir les requêtes HTTP qui consomment du temps CPU.
En pratique, ça s'installe simplement avec gem, puis on le lance pour générer un rapport (j'aime bien la version HTML) :

```
gem install request-log-analyzer
request-log-analyzer --output HTML --file report.html log/production.log
firefox report.html
```

Le rapport nous fournit un certain nombres d'informations que les hits sur chaque page, les codes HTTP renvoyés, les requêtes les plus lourdes.
Pour ma part, je me sers surtout du tableau des 20 requêtes HTTP les plus longues en temps cumulé (_Request duration - top 20 by cumulative time_).
Cela me donne une liste d'actions à bencher pour lesquelles une optimisation est toujours bonne à prendre.
Je passe également un peu de temps à regarder si ces requêtes apparaissent dans les 20 requêtes les plus lourdes pour la base et les 20 requêtes avec le temps de rendering le plus long (toujours en temps cumulé).
Je peux ainsi avoir une idée de ce qui prend du temps, et de valider ainsi que les résultats du bench collent avec ça.
Si je vois qu'une requête HTTP passe beaucoup de temps sur la base de données, mais que les résultats du bench ne montrent pas ça, je vais probablement importer la base de données du serveur de production et l'utiliser pour refaire les benchs.

Un autre tableau intéressant est la liste des requêtes bloquantes (_Process blockers (> 1 sec duration)_).
Si je vois des requêtes faire pas mal de hits dans cette liste, je sais qu'il va falloir les surveiller de près.

Voilà, request-log-analyzer n'est pas un outil magique. Il ne fait qu'une chose, mais il le fait bien. Et c'est très utile pour savoir par où commencer à optimiser un site.
