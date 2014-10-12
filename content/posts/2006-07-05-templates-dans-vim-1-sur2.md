---
layout: post
date: 2006-07-05
title: "Templates dans vim 1 / 2"
aliases:
- "/Vim/2006/07/05/templates-dans-vim-1-sur2"
categories:
- Vim
---
Hop, pour ce premier tips, je vais vous montrer comment utiliser des templates dans Vim. Par exemple, supposons que je veuille avoir ces quelques lignes :

```ruby
#!/usr/bin/env ruby
# Author: Bruno Michel <bmichel@menfin.info>
# Licence: MIT <http://www.opensource.org/licenses/mit-license.html>
```

au début de chaque nouveau script ruby.


Mode d'emploi
-------------

Pour cela, nous allons faire simple :

1. créer un fichier avec ce template, et le placer dans le répertoire `~/vim/templates` :

```
$ mkdir -p ~/.vim/templates
$ echo "#!/usr/bin/env ruby" > ~/.vim/templates/ruby
$ ...
$ echo  "#-------------------------------------------------------------------" >> ~/.vim/templates/ruby
```

2. modifier son fichier de configuration de vim :

```
$ vim ~/.vimrc
```

et rajouter la ligne suivante :

```vim
au BufNewFile *.rb 0r ~/.vim/templates/ruby
```

3. quitter et vérifier que cela fonctionne :

```
:wq
$ vim foo.rb
```


Explications 
------------

La ligne ajoutée au fichier vimrc peut se décomposer en :

* `au` : indique une commande qui sera automatiquement
* `BufNewFile` : l'exécution automatique se fera sur la création d'un nouveau fichier
* `*.rb` : ce paramètre indique que le fichier doit avoir l'extension .rb pour que la commande soit éxécutée
* `0r ~/.vim/templates/ruby` : cette commande ruby insère le contenu du fichier après la 0ème ligne, c'est-à-dire avant la 1ère ligne.

Voilà, c'est tout pour ce billet. Mais il y aura une suite avec comment avoir des templates un peu plus dynamiques. On verra par exemple comment insérer la date dans les templates.
