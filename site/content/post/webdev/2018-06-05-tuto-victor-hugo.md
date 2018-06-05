---
title: Tuto Victor-Hugo
tags: 'List [ "go", "golang", "hugo", "webdev", "jamstack", "gss" ]'
categories: 'List [ "Development", "golang" ]'
nomenu: main
date: '2018-06-05T23:03:20+02:00'
image: >-
  https://res.cloudinary.com/ctinformatique/image/upload/c_mfit,h_405,q_100,w_533/v1528232729/blog/C-IWWnkVoAAeqjJ.jpg
---
# Victor-Hugo et HUGO

## Qu'est ce que hugo ?

Hugo est un GSS ( générateur de site statique ) 

_Histoire de Hugo_

Hugo est un logiciel Open Source qui a été créé en 2013 et qui est hébergé sur la plateforme Github.

La première particularité de Hugo vient de son mode de développement. Il utilise un langage de programmation assez récent appelé Golang et créé par Google.

Ne partez pas ! Vous n’avez pas besoin de connaître ce langage de programmation car le logiciel s’utilise (presque) comme n’importe quel logiciel : avec un exécutable. D’ailleurs, Hugo est compatible avec Windows, Linux, Freebsd et MacOSX. Cependant lors de ce tuto nous utiliserons un environnement nodejs ! 

D’un point de vue technique, vous n’avez pas de base de données avec Hugo. Lorsque vous utilisez le logiciel, il va créer un ensemble de fichiers HTML et vous n’aurez plus qu’à déposer ces fichiers sur l’hébergement de votre choix. Contrairement à un CMS comme Wordpress, vous ne pouvez pas directement proposer des interactions avec les utilisateurs d’un site basé sur Hugo (comme des commentaires par exemple). Cependant, vous gagnez grandement en sécurité et vous faites des économies sur l’hébergement puisque vous n’avez plus besoin de PHP, de MySQL, etc. De plus l'interêt de cette stack est de pouvoir plug des services tiers, par exemple disqus pour gérer les commentaires de votre blog.

## Qu'est ce victor hugo ?

Victor hugo c'est une configuration de hugo, vous pouvez le télécharger à ce lien : <https://github.com/netlify/victor-hugo.>

En gros vous avez GULP et WEBPACK de configuré et prêt à être utilisé avec HUGO.

## Commençons ?

Tous d'abord vous devez avoir téléchargé :

* NodeJS
* cmder ( c'est un terminal pour windows , car nous utiliserons des commandes shell) 
* victor hugo 

## On commence par victor hugo

dézippée victor hugo dans un dossier, ensuite à l'aide votre terminal rendez-vous sur votre dossier en faisant :

`cd /chemin_vers_le_dossier/`

une fois ceci fait et que vous êtes sur votre dossier via le terminal vous allez taper : 

```
npm install
```

Cela aura pour effet ( via node ) d'installer toutes les dépendances lié à victor-hugo ( webpack,babel,gulp ).

Une fois ceci fait toujours depuis le terminal lancer la commande :

```
npm install -g hugo-cli
```

Cela installera hugo sur tout votre pc/mac ( via -g ) et -cli permet d'avoir accès aux commandes hugo.

Maintenant vous allez tester en tapant : 

```
npm start
```

Cela lancera le serveur nodejs qui généra les fichiers et vous l'affichera sur votre navigateur.
