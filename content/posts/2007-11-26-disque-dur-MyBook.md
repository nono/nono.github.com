---
layout: post
date: 2007-11-26
title: "Nouveau disque dur : MyBook World Edition"
aliases:
- "/Mat%C3%A9riel/2007/11/26/disque-dur-MyBook"
categories:
- Matériel
---
Je viens de m'acheter un disque dur externe Western Digital MyBook World
Edition. La bête doit principalement me servir pour mes sauvegardes, mais avec
ses 500 Go, je devrais avoir de la place pour d'autres choses. J'ai choisi ce
modèle car je voulais un disque dur branché sur de l'ethernet, pas en usb, et
qu'en plus j'avais lu sur
http://jeromeandrieux.blogspot.com/2007/06/nastty-convi-wd-mybook.html qu'il
avait le bon goût de tourner sous linux (les sources du firmware sous licence
GPL sont disponibles sur
http://support.wdc.com/download/index.asp?cxml=n&pid=30&swid=64 ).


Ce que j'ai déjà fait
---------------------

* le brancher
* aller sur l'interface web : http://admin:123456@<l'adresse IP du Mybook>
* rajouter un utilisateur sur cette interface
* activer l'accès ssh grâce à [la méthode de Martin Hinner|http://martin.hinner.info/mybook/sshaccess.php]
* se logger en ssh dessus avec l'utilisateur créé précédement
* désactiver mionet toujours grâce à [http://martin.hinner.info/mybook/disable_mionet.php|Martin Hinner]
* faire joujou avec l'interface web
* et finalement commencer mes sauvegardes à la main (à coups de scp)


Ce qu'il reste à faire
----------------------

Visiblement, il est possible de faire des choses bien sympathiques comme
installer [vsftpd](http://vsftpd.beasts.org/|vsftpd) (un serveur FTP bien secure),
[rsync](http://samba.anu.edu.au/rsync/) ou encore [PHP](http://php.net) (en
réutilisant le lighttpd de l'interface web) dessus :

* http://martin.hinner.info/mybook/packages.php
* http://mybookworld.wikidot.com/hacks-and-howto
* http://chayden.dyndns.info/info/mybookworld:top
* http://www.welped.com/2007/08/29/hacking-the-mybook-world-edition-into-a-php-powered-web-server/

Il est également possible de mettre en veille le disque dur d'après
http://kyyhkynen.net/stuff/mybook/ .

