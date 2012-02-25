---
layout: post
title: "Mise à jour de FrenchRails"
category: Rails
---
J'ai un petit plugin pour Rails qui permet de localiser facilement une application Rails : [FrenchRails](http://github.com/nono/french-rails/tree/master).
Pour ceux qui auraient raté [l'épisode précédent](http://blog.menfin.info/post/2009/03/18/Un-plugin-RoR-nomme-FrenchRails), en gros, ça permet de prendre en compte le fait que 0 est un singulier en français (alors que c'est pluriel en anglais).

Je viens de mettre à jour ce plugin pour qu'il traduise également les 'new' et 'edit' qui se balladent dans les URL générées par Rails.
Maintenant, ce sera 'nouveau' et 'modifier', ai-je décidé.

Enfin, tant qu'à resortir ce plugin du grenier, j'en ai également profité pour faire quelque chose que j'aurais dû faire depuis un certain temps : le passer en gem.
Il est disponible sur [Rubygems](http://rubygems.org/gems/french_rails) et peut donc s'installer d'un simple `gem install french_rails`.
