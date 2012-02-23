---
layout: post
title: "Annotez vos modèles"
category: Rails
---
Quand je travaille sur des modèles dans Rails, j'ai souvent besoin de regarder la liste des champs de ce modèle.
Vous savez, ces petites questions toutes bêtes que l'on se pose tous : c'est `firstname` ou `first_name` ? `phone` ou `mobile` ? `name` ou `title` ? `description` ou `body` ?

Pour répondre à ces questions, il faut aller chercher dans `db/schema.rb`, fichier que l'on a rarement sous les yeux.
Mais j'ai mieux à vous proposer : [Annotate](http://github.com/ctran/annotate_models/tree/master).
C'est un gem qui ajoute un commentaire en haut de chacun de vos modèles (et tests unitaires) avec la déclaration du modèle en question.

Voici un exemple tiré de ma réécriture de [LinuxFr.org](http://linuxfr.org/) en Rails :

```ruby
# == Schema Information
# Schema version: 20090120005239
#
# Table name: news
#
#  id          :integer(4)      not null, primary key
#  state       :string(255)     default("draft"), not null
#  title       :string(255)
#  body        :text
#  second_part :text
#  section_id  :integer(4)
#  created_at  :datetime
#  updated_at  :datetime
#
```

Pour l'utiliser, c'est on ne peut plus simple.
On fait un `gem install annotate` pour l'installer, puis on lance `annotate` quand on veut mettre à jour les commentaires.
Pour ma part, je fais ça après chaque `rake db:migrate`, mais libre à chacun de le lancer quand il le souhaite.
