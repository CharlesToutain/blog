---
title: JAM stack
description: >-
  Article qui parle des bénéfices qu'apportent les architectures web à bases de
  Jam stack. Nous abordons différents points : La sécurité, le SEO les
  performances.
tags:
  - go
  - golang
  - hugo
  - development
  - webdev
categories:
  - Development
  - golang
nomenu: main
date: '2014-06-02'
image: >-
  https://res.cloudinary.com/ctinformatique/image/upload/v1528225017/jamstack.png
---
Qu'est ce qu'une stack ?
  une stack c'est un ensemble de logiciels ou composants nécessaires pour créer une plate-forme complète.
  Au début des années 2000 la stack populaire ressemblait à LAMP ou encore WAMP. Pour avoir un site internet il fallait une stack complète avec Linux, Apache MySQL et php. Le web a changé, JavaScript a évolué. En effet grâce au JS et à son evolution il est dès à présent possible d'avoir recour à une JAMstack.

## La JAMstack

- - -

![image correspondant à la JAMstack](https://avatars2.githubusercontent.com/u/17439288?v=3&s=200 title)

### Qu'est ce que JAM stack

_JavaScript :_
Tout partie dynamique est généré par le javascript uniquement coté client ! Cela permet de gérer toute la partie dynamique, requête et élément de programmation. Les librairies, framework et javascript vanilla rentrent dans le cadre de la jam stack.

_API's :_
Les processus côté serveur ou les actions de base de données sont abstraites en API réutilisables, accessibles via HTTP avec JavaScript.
Cela peut être des API personnalisées ou utiliser des services tiers.

_Markup :_
Un générateur de site statique va permettre de build et générer le site afin de pouvoir l'envoyer directement en production.

## Quelle projet ne sont pas une JAMstack ?

_Un site dévéloppé avec un CMS WordPress, Drupal, Joomla, Prestashop_. Bien que aujourd'hui WordPress et Drupal peuvent être utilisés comme CMS headless, ce qui permet à l'aide d'une API REST de venir récupérer le contenu et de l'afficher sur plusieurs plateformes Web statiques.

![image qui décrit la différence entre cms headless et cms](https://res.cloudinary.com/ctinformatique/image/upload/c_scale,q_100,w_813/v1528739391/blog/cms_headless_vs_cms.png)

_Une application Web developpée_ avec un langage serveur.(PHP, NodeJS, Ruby..). Je tiens à nuancer ce propos, en effet j'utilise nodeJS comme environnement de développement afin de **build mes fichiers. ** Pour donner un autre exemple **Jekyl** est un générateur de site statique en ruby.

Créer un site uniquement en HTML/CSS/JS respecterait l'idée de la Jam stack, cependant aujourd'hui nous avons des outils bien plus puissant à l'instar des GSS ( générateurs de sites statiques ). 

## Ok mais pour quoi utiliser une JAMstack ?

### Le référencement

Développer un site statique présente des bénéfices pour améliorer le référencement naturel de votre site. 

En premier lieu, les URLs et l'architecture du site est simplifié avec un site statiques ( jam stack ) que avec un site dynamique et un CMS. En effet avec un CMS vous pouvez utiliser des règles de réécritures d'URLs coté serveur pour afficher des URLS compréhensibles. Avec un site en jam stack les URLs sont telles que vous les définissez elle reflètent l'emplacement de vos fichiers.  

Le duplicate content est également réduit, en effet certains CMS génèrent de manière automatique des pages pour les tags et les catégories. Des directives noindex et des URLs canoniques sont ajoutés de manière automatique à l'aide de modules. Les GSS ( générateurs de sites statiques ) permettent de créer vos propres taxonomies et de créer des pages simplement.Si besoins certains GSS propose des logiques de filtre, pagination et archivages. 

Pour finir un avantage lors de la conception de site qui utilisent le rendu coté client et frameworks JS. Le mécanisme consistant à servir des versions pré-rendues aux moteurs de recherches s'en trouve facilité. Pour donner un exemple : [Netlify](https://www.netlify.com/) qui est un hébergeur spécialisés dans l'hébergement de sites statique proposes le service de pré-rendue en quelques clics. 

### Performance accrue

D'un coté un serveur qui attend une requête afin de l’interpréter, puis de la construire pour enfin l'envoyer au client. Ou d'un autre coté une page déjà construite qui attend juste d'être envoyée, d'après vous la quelle est plus rapide ?
Si vous avez répondu la deuxième solution, alors vous devez déjà être convaincu par la JAMstack ;)

mais aussi quand il faut minimiser le temps d’attente pour le téléchargement du premier byte, rien n’égale des fichiers pré-construits servis par un CDN.

Quand votre déploiement consiste à rassembler des fichier pour être distribués depuis n'importe où, l’elasticité d’une plateforme consiste à servir ces fichiers depuis d’autres endroits.
De plus cela demande moins de ressources CPU/GPU au serveur qui pourront supporter des montés en charges plus aiséments. 

![photo des performances du blog-du-web sur pingdom tools](https://res.cloudinary.com/ctinformatique/image/upload/c_fit,q_100,w_366/v1528741069/blog/capture_perf_pingdomstools.png)

### Sécurité accrue

Avec une architecture serveur éclatée en microservices et abstraite en APIs, les zones d’attaques sont réduites.
Vous pouvez également tirer parti de l’expertise métier en utilisant des services tiers spécialisés.

Plus besoin de mettre à jour votre faille critique de Drupal car il n’y a pas de base de données. Les certificats SSL sont également faciles à installer et disponibles gratuitement grâce à des services comme LetsEncrypt.

Cependant le site peut être attaqué via les différents appels API. Assurez-vous que vos scripts non pas était détournés et altérés et que chaque échange est sécurisé via HTTPS. De plus le fait de déléguer certaines services, peut-être un risque de dépendance à ce service donc pensez à inspecter les garanties contractuelles et à tester la duré et le sérieux d'un service externe.

### Deploiement et Workflow

Un des principes de base du développement avec la JAMstack c’est que tout vit dans un dépôt Git, que ce soit les composants de notre site statique, les fichiers de configuration de notre générateur, nos fichiers CSS et JS, nos contenus écrits (sauvegardés sour forme de documents Markdown en texte brut). Avec votre service de déploiement et d’hébergement configuré pour refléter en permanence l’état de la branche de votre dépôt, appliquer une modification est aussi simple que de pousser un commit sur un dépôt GitHub. L’ensemble de votre site Web **le code et le contenu** vit dans un endroit centralisé, protégé par un versionnement robuste et peut être configuré pour être déployé en continu.

Oui mais et les clients dans tout ça ? Quid des utilisateurs non techniques ? Les experts de la production de contenu qui sont à l’aise avec des éditeurs comme celui de WordPress mais qui ne connaissent pas Markdown et GitHub ?

Le problème a été identifié il y a maintenant plusieurs années et beaucoup de solutions réjouissantes commencent à apparaître. Certaines sont extraodinairement simples. Si les éditeurs de vos contenus sont déjà familiers avec les bases de Markdown - c’est à dire # titre, **gras**, _italique_ - alors il n’y a aucune raison qu’il ne puissent éditer le dépôt sous-jacent. Des outils comme Prose.io s’intègrent à GitHub pour proposer une interface utilisateur plus adaptée pour les auteurs non techniques. Créez une branche pour les éditeurs de contenu puis fusionnez simplement leurs modifications pour publier de nouveaux contenus.

Sinon il y a aussi des dizaines de CMS “headless” qui sont parfaits pour les sites Web statiques. Ce sont avant tout des gestionnaires de contenus reposant sur une API qui permettent de dissocier vos contenus du côté client chargé de l’affichage de votre site. Siteleaf, par exemple qui fonctionne avec Jekyll et GitHub propose une édition dans le cloud compatible avec vos outils existants — comme c’est écrit sur leur site les sites Web devraient survivre à leurs CMS.

Comme je le disais, c’est un secteur qui se développe rapidement, vous serez confrontés à des challenges pour vous adapter à un workflow statique, particulièrement pour les projets ambitieux. Quiconque s’intéresse à l’utilisation de sites statiques pour un projet commercial ou à grande échelle devrait aller lire l’article de Stefan Baumgartner sur Smashing Magazine.

### Alors ce blog comment il est fait ?

Auparavant j'utilisais **WordPress**. 
Depuis que j'ai découvert la JAM stack, je ne cesse de l'utiliser dans mes projets perso/pros. En effet je me suis formé sur Hexo et Hugo qui sont deux générateurs de sites statiques performants et puissants, aujourd'hui je commence à me former sur Gatsby qui s'apparente à un framework react.

**Ce blog est créé avec HUGO et hébergé chez netlify le tout versionné sur github. Par ailleurs j'ai relié le CMS netlify avec lequel j'écrit cet article :). Afin de garder de meilleur performance j'utilise cloudinary pour le stockages et l'optimisations des images.**

### Conclusion

La mouvance statique évolue et de nombreuses JAM stack émergent et certaines ce consolident. Bien sur la jam stack ne convient pas pour tous les projets, mais convient je le pense pour un certains nombres de projets (site vitrine, blog, petits e-commerces). 

N’hésitez pas à laisser un commentaire et à lire l'article sur [netlify](http://blog-du-web.com/post/netlify/)
