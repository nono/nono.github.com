---
date: 2015-04-03
title: "Un terminal dans Neovim"
categories:
- vim
---

Comme je l'ai indiqué dans [un précédent
billet](http://blog.menfin.info/posts/2015-03-20-ma-config/), je suis passé à
Neovim. En pratique, cela reste très proche de Vim. Mais, on commence à voir
de nouvelles fonctionnalités très intéressantes. J'avais déjà parlé de
l'exécution asynchrone des plugins, ce qui leur permet de faire des
traitements longs sans bloquer complètement l'éditeur.

Plus récemment, [@tarruda](https://github.com/tarruda) a ajouté [la prise en
charge des vraies couleurs](https://github.com/neovim/neovim/pull/2198) dans
Neovim. Pour les terminaux qui supportent cette possibilité, il est maintenant
possible d'utiliser des couleurs avec des code hexadécimaux, sans se
restreindre à une palette de 16, 88 ou 256 couleurs comme c'est trop souvent
le cas. Cela devrait notamment plaire aux créateurs de thèmes, vu que ceux-ci
respecteront mieux les couleurs désormais.

Une autre fonctionnalité qui me semble très intéressante vient d'arriver dans
Neovim : c'est [l'émulation d'un terminal](https://github.com/neovim/neovim/pull/2076).
Grâce à la [libvterm](http://www.leonerd.org.uk/code/libvterm/), il est
possible de lancer un terminal dans Neovim, avec `:terminal` par exemple. Cela
créée un buffer en mode édition. Il est alors possible d'utiliser ce terminal
pour faire différentes actions (comme un terminal normal), mais également de
profiter des autres modes de vim. Au hasard, la sélection rectangulaire peut
être bien pratique !

Pour sortir du mode édition, il faut utiliser la combinaison `<C-\> <C-n>`. Ce
n'est pas très intuitif, mais comme le mode terminal propose son propre
binding de touches avec `:tnoremap`, on peut ajouter ces lignes à son fichier
`/.nvimrc` pour utiliser `Esc` :

```vim
if has("nvim")
    tnoremap <Esc> <C-\><C-n>
endif
```

Cette fonctionnalité va ouvrir des portes aux développeurs de plugins, pour
intégrer plus facilement Neovim et des outils externes. À titre d'exemple,
il existe un [plugin pour
gdb](https://github.com/tarruda/neovim/blob/refactor-job-api-3/contrib/neovim_gdb/neovim_gdb.vim),
qui permet depuis la vue terminal de Neovim de contrôler le déboggeur et
d'avoir quelques fonctionnalités bien pratiques :

- Sauter dans le fichier / ligne quand gdb atteint un point d'arrêt
- Garder l'état en cours d'exécution / en pause
- Contrôler l'exécution de gdb depuis n'importe quelle fenêtre de l'éditeur et
  inspecter des expressions.

Pour finir, voici une petite capture d'écran :

![Capture d'écran de Neovim avec un terminal](/public/Neovim-term.png)
