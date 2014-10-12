---
layout: post
date: 2009-02-08
title: "LinuxFr.org avec des commentaires et des réponses aux commentaires, et des réponses aux réponses, etc."
aliases:
- "/LinuxFr/2009/02/08/Commentaires-LinuxFr"
categories:
- LinuxFr
---
Les développements continuent d'avancer pour la refonte en Rails de [LinuxFr.org](http://linuxfr.org).
Je me suis attaqué à un refactoring des commentaires.
Les fils de discussions de LinuxFr.org sous forme d'arbres sont une des forces du site : ils permettent de suivre les discussions très intéressantes (et les trolls, bien sûr).
Malheureusement, c'est aussi une structure qui se prête assez mal aux bases de données relationnelles.
J'étais d'abord sur une technique d'ensembles imbriqués (« nested set »), avec le plugin rails [awesome nested set](http://github.com/collectiveidea/awesome_nested_set), mais celui-ci ne fournissait pas les méthodes qui m'intéressaient.
Par exemple, je veux pouvoir construire tout un arbre de discussions en effectuant une seule requête SQL.
J'aurais pu compléter ce plugin, mais quitte à écrire du code, j'ai préféré partir sur une structure plus adaptée à mon cas :
le chemin matérialisé (« materialized path ») consiste à garder pour chaque commentaire la liste de tous les IDs des commentaires parents dans un champs sérialisé.
J'ai fait cela aujourd'hui et j'ai déjà une version fonctionnelle.
La preuve en images :
[Les threads de commentaires en cours de développement](/public/LinuxFr_refonte_commentaires.png)

Dans les jours qui viennent, je pense me concentrer sur les dépêches et les commentaires (nettoyer le code, rajouter les fonctionnalités vraiment essentielles, corriger un ou deux bugs que j'ai remarqué, etc.).
Je pourrais ensuite me pencher sur une nouvelle partie (la tribune ou le tracker, je ne sais pas encore).

