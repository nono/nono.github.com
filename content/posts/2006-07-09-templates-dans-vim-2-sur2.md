---
layout: post
date: 2006-07-09
title: "Templates dans vim 2 / 2"
aliases:
- "/Vim/2006/07/09/templates-dans-vim-2-sur2"
categories:
- Vim
---
Comme promis, nous allons donc voir comment avoir des templates un peu plus dynamiques. Le langage de script de vim n'étant pas des plus sympathiques, je préfère appeler un programme externe.
Pour cela, nous allons remplacer la ligne que nous avions insérée dans le fichier vimrc par celle-là :

```vim
au BufNewFile * 0r! ~/.vim/skeleton.rb
```

Ici, c'est un script en ruby (`skeleton.rb`) qui est appelé.
Pour le moment, ce script ne reçoit aucun paramètre.
Pas terrible pour savoir quel template utiliser !
Pour régler ce problème, nous pouvons passer par exemple le nom du fichier, avec son chemin complet.
Il suffit de rajouter `%:p` toujours à la me ligne du fichier vimrc.
`%` indique le fichier courant, et `:p` est un modificateur pour avoir le chemin complet.

Mais, __ViM__ fait déjà de la détection de _filetype_, aussi il peut être intéressant de passer ce _filetype_ à notre script.
Pour cela, nous allons encore modifier notre ligne :

```vim
au BufNewFile * :exe("0r! ~/.vim/skeleton.rb %:p " . &filetype)
```

__Note__ : comme il n'est pas possible à ma connaissance de passer directement le filtype à la commande r!, je construit d'abord la chaîne de cractère avec toute la commande et le filetype, puis je l'éxécute.

Maintenant que nous pouvons appeller un script avec le chemin du fichier et son _filetype_, je pense qu'on peut dire que c'est gagné.
Voici à titre d'exemple le script que j'utilise :

```ruby
#!/usr/bin/env ruby
# Author: Bruno Michel <bmichel@menfin.info>
# Licence: MIT <http://www.opensource.org/licenses/mit-license.html>

require 'erb'


SKELETON_DIR = File.expand_path("~/.vim/skeleton");
EXTENSION  = "erb"

file, filetype = ARGV
filename  = File.basename(file)
skeletons = [filename, filetype]
skeleton  = skeletons.map { |s|
	File.join(SKELETON_DIR, "#{s}.#{EXTENSION}")
}.find { |s|
	File.exist?(s) && File.readable?(s)
}

exit if skeleton.nil?

File.open(skeleton) do |f|
	puts ERB.new(f.read, nil, '<>').result(binding)
end
```

__Note__ : si vous voulez utiliser ce script, n'oubliez pas de le rendre exécutable (`chmod a+x ~/.vim/skeleton.rb`)

Ce script va chercher un fichier `.erb` dans le répertoire `~/.vim/skeleton` dont le nom correspond soit au nom du nouveau fichier, soit à son filetype.
Et dans ce répertoire, on trouve, par exemple, `ruby.erb` :

```ruby
#!/usr/bin/env ruby
# Author: Bruno Michel <bmichel@menfin.info>
# Licence: MIT <http://www.opensource.org/licenses/mit-license.html>
```

ou `README.erb` :

```
<%= `figlet -c README` %>
<%# figlet: http://www.figlet.org %>

Author: Bruno Michel <bmichel@menfin.info>
Date: <%= Date.today.strftime("%d/%m/%y") %>
Time: <%= Time.now.strftime("%H:%M:%S") %>
<% directory = File.dirname(file) %>
Project: <%= File.split(directory).last %>
```

Et voilà, mission accomplie, nous avons des templates dynamiques, avec notamment la possibilité d'insérer la date ou l'heure courante.

