---
date: 2015-07-01
title: "Sur un petit nuage, Cozy"
categories:
- cozy
---

[Cozy](https://cozy.io/fr/) est un Cloud personnel que vous pouvez héberger,
personnaliser et entièrement contrôler. Il permet de reprendre la main sur ses
données personnelles, comme ses contacts, calendriers, courriels, fichiers,
plutôt que de les laisser aux mains des GAFA (Google, Apple, Facebook,
Amazon). En tant que fervent défenseur du respect à la vie privée, je suis le
projet Cozy depuis quelques temps. Avec [l'arrivée de la version
2.0](http://blog.cozycloud.cc/news/2015/06/16/releasing-cozy-2/) et [la loi
sur le renseignement](http://standblog.org/blog/tag/loirenseignement), j'ai
sauté le pas et j'ai installé mon instance de Cozy.

![Logo de Cozy Cloud](/public/cozy.png)

C'est un projet encore jeune. Dans ce billet, je vais détailler ce que j'aime
et les choses que j'aimerais voir améliorées. Je risque de paraître difficile,
mais c'est uniquement parce que j'ai de grands espoirs dans Cozy. Ces
critiques sont là pour encourager d'autres personnes à franchir le pas et
installer leur instance de Cozy en connaissance de cause, et pour donner un
retour à l'équipe Cozy pour permettre d'améliorer leur produit.

Commençons par **ce que j'aime**. L'application **Home** a été refaite. C'est
elle qui vous accueille et permet de naviguer entre les différentes
applications installées sur Cozy. En effet, Cozy possède un coeur, qui
s'occupe du stockage des données, des permissions d'accès pour celles-ci et de
la gestion des applications, mais toutes les fonctionnalités viennent dans des
applications séparées. Par exemple, nous avons une application pour les
calendriers, une autre pour gérer les contacts, etc. Et pour en revenir à
Home, c'est l'interface qui permet de passer d'une application à une autre. La
nouvelle version est plus jolie et plus pratique à mon goût. Ça pourrait être
pas mal de pouvoir reprendre des informations des applications sur Home
(afficher le nombre de mails non-lus ou le prochain rendez-vous), mais ça fait
déjà bien le boulot.

J'aime aussi l'aspect **applications séparées** où l'on installe que ce dont
on a besoin, et surtout qui permet d'installer toutes les applications que
l'on veut sans avoir à demander la permission sur un store. L'interface de
Cozy propose d'installer des applications depuis une liste mais a aussi une
option pour installer une application directement depuis un dépôt git. C'est
bien vu !

L'**installation** via [un paquet
debian](http://cozy.io/fr/host/install/install-on-debian.html) est très simple
et la gestion via l'interface web se fait facilement. On sent que de gros
efforts ont été faits sur ces points. Bien entendu, ce n'est pas parfait et il
y a toujours des petits trucs qui peuvent être améliorés, mais je suis
confiant que ça va continuer à se peaufiner. Et comme Cozy est un **Logiciel
Libre**, c'est encore plus facile de contribuer.

Petit à côté : vivement septembre, que l'on ait des certificats SSL simplement
avec [Let's Encrypt](https://letsencrypt.org/).

Enfin, pour ne rien gâcher, **l'équipe** derrière le projet est très sympa. On
sent qu'elle a à coeur les problématiques de respect de la vie privée et de
contrôle des données personnelles. Elle est très active, à l'écoute sur [les
forums](https://forum.cozy.io/) et organise régulièrement des [événements avec
la communauté](http://www.meetup.com/Meetup-des-utilisateurs-de-Cozy-Cloud-en-France/).
Un gros merci à vous !

Et maintenant, je vais aborder les points qui **me gênent** et dont j'espère
qu'ils pourront être corrigés dans le futur. Tout d'abord, je trouve très
dommage de ne pas avoir un tutoriel pour **sortir ces données de Cozy**. Une
des promesses de Cozy est de ne pas enfermer l'utilisateur. On peut
effectivement [supprimer son instance Cozy et les données
associées](https://cozy.io/fr/host/uninstall.html) (ce qui est déjà mieux que
pour les GAFA), mais franchement, si on met des données dans Cozy, c'est
qu'elles sont importantes et le jour où l'on veut sortir de Cozy (si jamais ce
jour arrive), on voudra pouvoir prendre nos données avec nous. On peut
exporter certaines données de Cozy de différentes façons, mais c'est loin
d'être aussi facile que d'installer une instance de Cozy. Ça mériterait d'être
unifié et documenté.

Ensuite, je regrette certains **choix techniques** et les conséquences
associées. CouchDB n'est plus très populaire ces derniers temps. Cela peut
compliquer la vie des développeurs (même si cet aspect est masqué en partie
par une couche d'abstraction, [cozy-db](https://github.com/cozy/cozy-db)).
Et je ne suis vraiment pas fan de l'idée de mettre des fichiers binaires
dedans. J'ai beaucoup de mal à synchroniser mes photos depuis mon smartphone
vers Cozy. Je spécule, mais je ne serais pas étonné que le problème vienne de
là (il faudra que j'investigue).

Et pour la partie authentification et autorisations, je trouve dommage que
l'architecture n'ait pas été plus loin. A priori, proposer du **oAuth2**
n'aurait pas été très compliqué et aurait permis d'avoir quelque chose de plus
standard et mieux fini que la solution actuelle. Ceci dit, je comprends que ce
n'est pas facile d'avancer sur ce sujet très complexe et qui bouge rapidement.

Pour finir, le point qui me dérange le plus est **le manque de traction**. Il
y a encore très peu d'applications disponibles. Du côté des applications
officielles, aucune ne me paraît pouvoir devenir une killer app. Je connais
peu de gens qui soient passé à Cozy. Et j'ai peur que l'équipe de Cozy
n'arrive pas à accélérer le rythme de développement pour pouvoir proposer
suffisamment de nouvelles choses pour réussir à faire naître un écosystème
autour d'eux. J'espère me tromper sur ce point et je souhaite vraiment à Cozy
de réussir. D'ailleurs, la prochaine étape pour moi sera de me lancer dans le
développement d'une app pour Cozy. Un premier pas pour aider Cozy ?
