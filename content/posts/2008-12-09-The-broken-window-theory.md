---
layout: post
date: 2008-12-09
title: "The broken window theory"
aliases:
- "/Divers/2008/12/09/The-broken-window-theory"
categories:
- Divers
---
La théorie des fenêtres cassées (« The broken window theory ») a inspiré les forces de police de New York et d'autres villes importantes pour lutter contre la criminalité.

Cette théorie postule que la différence entre un immeuble propre et joli, et un autre en très mauvais état peut être la conséquence d'une simple fenêtre cassée.
Cette simple fenêtre cassée laisse une impression de négligence et d'impunité.
Des personnes commencent à laisser traîner des détritus, puis des tags apparaissent, et en un rien de temps, l'immeuble est devenu insalubre et mal fréquenté.
La morale ? Il ne faut pas laisser traîner des fenêtres cassées, mais au contraire, les réparer de suite pour éviter que des dégâts plus sérieux n'arrivent.
Jusqu'à récemment, cette théorie n'était qu'une hypothèse, mais [des études récentes](http://www.economist.com/science/displaystory.cfm?story_id=12630201&CFID=31056247&CFTOKEN=41038121) viennent soutenir cette théorie.

Chose intéressante, [les pragmatics programmers](http://www.pragprog.com/titles/tpp/the-pragmatic-programmer) ont appliqué cette théorie au développement logiciel.
Les fenêtres cassées sont alors tous les _code smells_ : le test unitaire qui ne passe pas, le module mal documenté, le FIXME qui traîne, la fonction mal implémentée...
Il est alors important de corriger au plus vite ces petits défauts, sans quoi ils vont s'accumuler et donner une mauvaise impression de la qualité du code.
Et alors, ce seront des défauts de plus en plus en gros qui vont arriver, chaque développeur se disant que ce n'est pas grave s'il introduit un nouveau code louche pour gagner du temps, car d'autres développeurs l'ont déjà fait ailleurs.
Le même développeur qui aurait une base de code propre, sans _fenêtres cassées_, n'aurait pourtant pas osé être le premier à écrire du code sale (surtout s'il sait que son code fera l'objet d'un code review, mais c'est un autre sujet).

Pour avoir déjà rencontré souvent ce cas de figure, je sais que cette analogie est très pertinente.
__Ne laissez pas des fenêtres cassées dans votre code !__

