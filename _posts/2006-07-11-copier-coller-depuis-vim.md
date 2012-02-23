---
layout: post
title: "Copier-Coller depuis ViM"
category: Vim
---
Dans mon dernier billet, j'écrivais que je rédige mes billets avec ViM, puis que je fais un copier-coller vers l'interface web de Dotclear.
Pour cela, je fais la combinaison de touches suivantes :

```
gg      Aller au début du fichier et
"*      utiliser le registre "* pour ...
yG      ... copier le texte jusqu'à la fin du fichier.
```

Et comme le registe `"*` correspond au _clipboard_, je peux ensuite coller mon texte dans mon navigateur web (firefox).

Mais pour ce post, j'ai décidé de suivre
[le conseil de Romuald](http://blog.menfin.info/post/2006/07/09/Coloration-syntaxique-dans-Vim-pour-les-billets-Dotclear#c45302)
et d'utiliser l'extension [Mozex](http://mozex.mozdev.org/), et à première vue, ca paraît pas mal.
