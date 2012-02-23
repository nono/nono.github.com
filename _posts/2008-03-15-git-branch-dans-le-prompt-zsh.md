---
layout: post
title: "Afficher la branche Git courante dans le prompt de ZSH"
category: Git
---
Je suis tombé sur un tips bien sympa :
[Show Your GIT Branch Name In Your Prompt](http://www.simplisticcomplexity.com/2008/03/13/show-your-git-branch-name-in-your-prompt/).
Il y est expliqué comment avoir la branche [Git](http://git.or.cz/) en cours dans son prompt avec [Bash](http://www.gnu.org/software/bash/).

J'ai adapaté ca pour [zsh](http://www.zsh.org/). Voici un extrait de mon `zshrc` :

```
export PS1='%~ $(git_branch)%# '

function git_branch {
  git branch --no-color 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1) /'
}

setopt PROMPT_SUBST
```

La seule difficulté fût de se rendre compte qu'il fallait activer une option pour que ca marche, et de savoir quelle était cette option (`PROMPT_SUBST` en l'occurence).

Ainsi que je suis sous un répertoire normal, j'ai un prompt de la forme `~/Desktop % `, et quand je suis dans un répertoire versionné sous Git, ca donne : `~/mon_projet (ma_branche) % `.
Ce n'est pas grand chose, mais comme il paraît que c'est une bonne pratique de faire des branches sous Git, autant avoir en permance le nom de la branche courante sous les yeux.

__PS__ : j'ai des invitations pour [GitHub](https://github.com/) si ca intéresse des gens.
