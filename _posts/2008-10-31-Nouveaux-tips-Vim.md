---
layout: post
title: "Encore plus de tips pour Vim"
category: Vim
---
Dans la série des astuces pour Vim, voici le troisième épisode ([le premier se trouve par ici](http://blog.menfin.info/post/2007/11/18/Tips-pour-Vim) et [le second par là](http://blog.menfin.info/post/2008/01/22/Nouveaux-tips-pour-vim)).

Jamis Buck, l'auteur de [Capistrano](http://www.capify.org/), revient sous Vim après plusieurs années de textmate.
La bonne nouvelle, c'est qu'il ne peut pas se passer de Cmd-T pour trouver des fichiers, et qu'[il a donc développé un plugin Vim pour faire cela](http://weblog.jamisbuck.org/2008/10/10/coming-home-to-vim) : [Fuzzy File Finder](http://github.com/jamis/fuzzy_file_finder/tree/master).
Je vous conseille fortement de l'essayer, ca simplifie vraiment la vie pour ouvrir des fichiers bien planqués dans des sous-répertoires.

----

La recherche sous Vim se fait en tapant `/` puis l'expression recherchée.
Je suppose que vous connaissiez cette commande, mais saviez-vous que l'on peut spécifier un déplacement en tapant un deuxième `/` puis le déplacement voulu ?
Par exemple, `/foo/e+1` placera le curseur sur le premier caractère après foo.
Ceci est très pratique quand on répète plusieurs fois la même recherche.

----

Si vous débuggez souvent des feuilles de style CSS, vous êtes amené à faire beaucoup d'allers-retours entre votre navigateur web et Vim.
Et à chaque fois que vous faîtes une modification, vous êtes obligés de taper <ESC>:w<CR> pour la tester.
Pour gagner quelques touches à chaque itération, je vous propose de rajouter la ligne suivante à votre fichier `.vimrc` :

```vim
autocmd FocusLost *.css :up
```

Elle enregistre automatiquement chaque fichier .css quand Vim perd le focus (et uniquement s'il y a des changements à enregistrer).

----

Le dernier truc n'en est pas vraiment un, je voulais juste vous faire part du dernier plugin que j'ai développé pour Vim.
Celui-ci permet d'avoir la coloration syntaxique pour [le framework Merb, la bibliothèque Datamapper](http://www.vim.org/scripts/script.php?script_id=2417) et [le framework javascript jQuery](http://www.vim.org/scripts/script.php?script_id=2416).
Voici un petit screenshot de ce que cela donne chez moi :

![Screenshot](http://blog.menfin.info/public/Gvim_merb_datamapper_jquery.png)
