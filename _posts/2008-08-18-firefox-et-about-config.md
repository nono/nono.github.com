---
layout: post
title: "Firefox et about:config"
category: Astuces
---
[Firefox](http://www.mozilla-europe.org/fr/) est le navigateur que j'utilise tous les jours, et ce depuis un certain nombre d'années.
Au fil du temps, je me suis habitué à un certain nombre de préférences, dont certaines doivent être configurées depuis la page `about:config`.
Pour ceux qui ne connaissent pas cette page, je dirais juste qu'il suffit de taper about:config dans la barre d'adresse de firefox pour accéder à un écran qui permet de modifier de nombreuses fonctionnalités avancées.
Les noms et valeurs des préférences sont souvent obscurs.
Il existe une [liste relativement complète de ces préférences](http://preferential.mozdev.org/preferences.html), mais voici ceux que j'utilise le plus souvent :

* `browser.tabs.closeButtons` à `3` pour avoir un seul bouton fermer les onglets, tout à droite de la barre d'onglets, comme dans les anciennes versions de firefox.
* `browser.backspace_action` à `0` pour que la touche ??backspace](retour arrière?? permette de revenir en arrière dans l'historique.
* `middlemouse.contentLoadURL` à `true` pour pouvoir aller sur l'URL dans le presse-papier en cliquant juste sur le bouton du milieu de la souris (à la façon d'un coller sous UNIX).
* `browser.blink_allowed` à `false` pour désactiver les clignotements provoqués par les balises `<blink>`.
