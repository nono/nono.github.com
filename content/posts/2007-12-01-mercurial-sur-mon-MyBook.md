---
layout: post
date: 2007-12-01
title: "Mercurial sur mon MyBook"
aliases:
- "/Mat%C3%A9riel/2007/12/01/mercurial-sur-mon-MyBook"
categories:
- Matériel
---
J'ai installé [mercurial](http://www.selenic.com/mercurial/) sur mon MyBook.
Ce n'est pas très compliqué, mais voici quand même la méthode que j'ai utilisée pour ceux qui n'ont pas envie de chercher.
La première chose à faire, c'est se connecter en ssh (si sshd n'est activé, vous pouvez le faire grâce à [la méthode de Martin Hinner](http://martin.hinner.info/mybook/sshaccess.php)).
Ensuite, comme mercurial est en [Python](http://www.python.org/), il faut installer Python :

```
$ cd /tmp
$ wget http://www.python.org/ftp/python/2.5.1/Python-2.5.1.tar.bz2
$ tar xvjf Python-2.5.1.tar.bz2
$ cd Python-2.5.1
$ ./configure --disable-ipv6 --disable-shared --with-cxx=no --with-threads
$ make
$ sudo make install
```

Puis, on peut passer à l'install de mercurial proprement dit :

```
$ cd /tmp
$ wget http://www.selenic.com/mercurial/release/mercurial-0.9.5.tar.gz
$ tar xvzf mercurial-0.9.5.tar.gz
$ cd mercurial-0.9.5
$ make
$ sudo make install-bin
```

Un petit `hg -v` pour tester, et c'est déjà fini.
