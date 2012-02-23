---
layout: post
title: "Coloration syntaxique dans Vim pour les billets Dotclear"
category: Vim
---
Je ne sais pas pour vous, mais moi, j'ai horreur de devoir taper du texte dans mon navigateur web.
Aussi, dès que je tape plus de quelques lignes, j'utilise ViM, puis je fais un copier-coller vers firefox.
Cela me permet par exemple de profiter de la coloration syntaxique.

En particulier, je tape mes billets sous ViM, et je me suis donc créé le fichier de syntaxe pour là aussi avoir la coloration syntaxique.
Ce fichier est téléchargeable ici : [dotclear.vim](http://blog.menfin.info/public/dotclear.vim)
Il faut le placer dans le répertoire `~/.vim/syntax/`.

Et pour que ViM sache automatiquement que les fichiers avec l'extension `.dc` sont au format `dotclear`, il suffit de créer un fichier `~/.vim/ftdetect/dotclear.vim` avec le contenu suivant :

```vim
au BufRead,BufNewFile *.dc  set ft=dotclear
```

