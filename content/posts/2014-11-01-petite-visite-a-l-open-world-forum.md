---
date: 2014-11-01
title: "Petite visite à l'Open World Forum"
categories:
- events
---

L'[Open World Forum](http://www.openworldforum.paris/fr/) est un événement qui
se tient une fois par an sur Paris, pour parler des enjeux de l'Open Source,
l'Open Data, l'Open Hardware, l'Open Web, etc. Cette édition était centrée sur
le thème « Take back control », reprendre le contrôle face à la NSA, aux
mastodontes américains que sont Google, Apple, Facebook et Amazon et, plus
généralement, à tous ceux qui veulent à notre vie privée et notre liberté.
Elle s'est tenue les 30 et 31 octobre et, si je n'ai pas pu m'y rendre jeudi,
j'ai néanmoins assisté aux conférences du vendredi.

Globalement, j'ai beaucoup aimé les présentations que j'ai pu regarder. Bien
sûr, certaines étaient meilleures que d'autres mais le niveau général pour les
_tracks_ que j'ai suivis était très bon. En voici 3 qui m'ont particulièrement
marqué.


## Software development analytics for the masses 

Le matin, j'ai été agréablement surpris par [les tableaux de bord produits par
bitergia](http://bitergia.com/dashboards/) pour des projets Open-Source
majeurs. Ils reprennent des statistiques extraites d'informations publiques
(dépôts git, listes de diffusion, canaux IRC, etc.) pour faire ressortir des
tendances. On peut voir quelques sont les entreprises qui participent à un
projet et si le temps pour qu'un patch soit accepté est similaire selon qu'il
provient de l'une ou l'autre de ses sociétés (cela peut s'expliquer par le
niveau d'expertise des développeurs de chaque société ou par des raisons
politiques). On peut également suivre le temps de résolution des bugs au fil
du temps et voir les effets de la mise en place d'une politique de gestion des
tickets. Bref, c'est un très bon moyen de mieux comprendre des communautés
autour d'un projet Open-Source et de se poser les bonnes questions pour
qu'elles puissent travailler plus efficacement.


## State Of the Art in Machine Learning

Juste après la pause de midi, j'ai pu assister à la géniale présentation
d'Olivier Grisel, [The state of deep learning in
2014](https://speakerdeck.com/ogrisel/the-state-of-deep-learning-in-2014).
Après une rapide introductionsur le _Machine Learning_, nous avons eu le droit
à 3 exemples d'application de _deep learning_ (= réseaux de neuronnes avec de
nombreuses couches) vraiment époustouflants. Il y avait d'abord la
reconnaissance d'objets, animaux et formes sur des photos. Le taux d'erreur
diminue très fortement d'année en année sur [le concours
ImageNet](http://image-net.org/challenges/LSVRC/2014/index) et le meilleur
algorithme est maintenant vraiment tout proche de faire aussi bien que les
humains sur cet exercice. Le deuxième exemple était la construction d'une
représentation du sens d'un texte indépendante de la langue. La première
application est la traduction d'une langue à une autre, mais plein d'autres
choses sont rendues possibles via cet outil. Enfin, Olivier nous a montré
qu'il était possible de construire un programme super fort sur les jeux Atari
à partir d'un apprentissage sans supervision avec un signal très faible.

Le _deep learning_ est vraiment très puissant, mais il requiert 3 choses :

1. Des compétences très pointues sur le sujet
2. Beaucoup de puissance de calcul
3. De très gros volumes de données pour entraîner les réseaux de neuronnes.

Or Google et Facebook rachètent toutes les startups dans ce domaine, ont les
plus gros datacenters au monde et on leur donne gentillement toutes nos
données. Ne devrait-on pas s'en inquiéter ?


## CaliOpen, correspondance sécurisée

La troisième conférence qui m'a vraiment marquée est la présentation de
[CaliOpen](https://www.caliopen.org/), par Laurent Chemla. L'objectif est de
redonner du contrôle sur sa vie privée, pour se protéger soi, mai surtout pour
protéger les autres autour de soi. Cela passe par un logiciel libre de
messagerie privée (emails, chat, SMS, etc.) qui va agir sur deux niveaux :

1. Redonner de la valeur à la vie privée
2. Rendre beaucoup plus coûteux l'espionnage en masse.

J'espère que ce projet et d'autres dans le même style vont réussir à faire
bouger les choses et réussir à atteindre d'autres personnes que le cercle très
restreint des geeks. D'ailleurs, si vous être un développeur front, sachez que
Caliopen aurait bien besoin de votre aide.


## Conclusion

J'ai apprécié cette édition de l'Open World Forum. Félicitations à Florent
Zara, le président de cette édition, et aux différents responsable de
_tracks_.

Le thème « Take back control » est le bienvenu. On voit qu'on est très loin
d'y arriver et qu'il reste beaucoup de choses à faire. À commencer par les
organisateurs de l'Open World Forum : le site piste les utilisateurs via
Google Analytics, propose de se connecter avec Twitter et Facebook et envoie
des emails via MailChimp (une société américaine utilisant la plateforme
Amazon). Bref, ce n'est pas gagné mais c'est un combat important pour notre
futur.
