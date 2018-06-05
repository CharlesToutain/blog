---
title: JAM stack
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
---
Tous d'abord qu'est ce qu'une stack ?
  une stack c'est un ensemble de logiciels ou composants nécessaires pour créer une plate-forme complète.
  Au début des années 2000 la stack populaire ressemblait à LAMP ou encore WAMP. Pour avoir un site internet il fallait une stack complète avec Linux, Apache MySQL et php. Le web a changé, JavaScript a évolué. En effet grâce au JS et à son evolution il est dès à présent possible d'avoir recour à une JAMstack.

## La JAMstack

- - -

![image correspondant à la JAMstack](https://avatars2.githubusercontent.com/u/17439288?v=3&s=200 title)

### 3 critères pour définir une JAMstack

_JavaScript :_
Toute programmation dynamique du cycle de requête / réponse est gérée par JavaScript, exécutée entièrement sur le client.
Cela peut être n’importe quel librairie, framework front-end ou encore JavaScript vanilla.

_API's :_
Les processus côté serveur ou les actions de base de données sont abstraites en API réutilisables, accessibles via HTTP avec JavaScript.
Cela peut être des API personnalisées ou utiliser des services tiers.

_Markup :_
Le balisage HTML doit être pré-construit au moment du déploiement, généralement à l’aide d’un générateur de site pour les sites de contenu ou un outil de création d’applications Web.

## Quelle projet ne sont pas une JAMstack ?

_Un site dévéloppé avec un CMS WordPress, Drupal, Joomla, Prestashop_. Bien que l'API REST de WordPress et drupal permette maintenant de transformer le CMS serveur en un CMS headless et donc cela est considéré comme une JAMstack.

_Une application Web developpée_ avec un langage serveur.(PHP, NodeJS, Ruby..). Je tiens à nuancer ce propos, en effet j'utilise nodeJS que environnement de développement afin de **build mes fichiers. **

Créer un site uniquement en HTML/CSS/JS respecterait l'idée de la Jam stack, cependant aujourd'hui nous avons des outils bien plus puissant à l'instar des GSS ( générateurs de sites statiques ). 

## Ok mais pour quoi utiliser une JAMstack ?

### Le référencement

Assurément, je vais commencer avec le référencement. Le développement statique présente une multitude de bénéfices pour la visibilité de votre site sur les moteurs de recherche et tous ne sont pas forcément toujours appréciés à leur juste valeur.

Premièrement, la simplification des URLs et de l’architecture du site est souvent plus simple avec la JAMstack qu’avec un site dynamique et un CMS. Plutôt que de se reposer sur des régles de réecritures complexes d’URLs côté serveur pour que votre contenu soit accessible via des URLS lisibles (example.com/?p=12345 → example.com/clair-et-net/), vos URLs sont ce que vous voulez qu’elles soient : elles reflètent simplement l’emplacement des fichiers de votre site1.

Le risque de duplication de contenus est également très réduit. Beaucoup de CMS génèrent automatiquement des pages pour les catégories, les tags et les archives par date alors que vous n’en avez peut-être pas besoin. Généralement des directives noindex et des URLS canoniques sont ajoutées à l’aide de plugins supplémentaires pour gérer tout ça. Les générateurs de site statique à l’inverse vous permettent de créer des pages finement et de mettre en place la taxonomie qui correspond à votre contenu. Si besoin, beaucoup de générateurs embarque des fonctions et une bonne logique pour créer, filtrer et paginer des pages d’archives.

### Performance accrue

D'un coté un serveur qui attend une requête afin de l'interpreter, puis de la construire pour enfin l'envoyer au client. Ou d'un autre coté une page déjà construite qui attend juste d'être envoyée, d'après vous la quelle est plus rapide ?
Si vous avez répondu la deuxième solution, alors vous devez déjà être convaincu par la JAMstack ;)

mais aussi quand il faut minimiser le temps d’attente pour le téléchargment du premier byte, rien n’égale des fichiers pré-construits servis par un CDN.

### Sécurité accrue

Avec une architecture serveur éclatée en microservices et abstraite en APIs, les zones d’attaques sont réduites.
Vous pouvez également tirer parti de l’expertise métier en utilisant des services tiers spécialisés.

Plus besoin de mettre à jour votre faille critique de Drupal car il n’y a pas de base de données. Les certificats SSL sont également faciles à installer et disponibles gratuitement grâce à des services comme LetsEncrypt.

### Moins cher, plus évolutif

Quand votre déploiement consiste à rassembler des fichier pour être distribués depuis n'importe où, l’elasticité d’une plateforme consiste à servir ces fichiers depuis d’autres endroits.
Les CDN sont parfait pour cela, et possèdent de base des solutions pour mettre à l’echelle rapidement.

### Deploiement et Workflow

Une fois que vous avez travaillé sur un site Web avec la JAMstack - que vous avez déployé des mises à jour et publié des contenus régulièrement - vous commencez à ressentir le potentiel disruptif de cette manière de développer. Ça évolue rapidement et on peut parfois se sentir un peu comme dans le Far West, avec tous ces nouveaux outils et ces nouveaux services qui arrivent tous les jours, mais ne vous y trompez pas : c’est puissant, flexible, on a atteint le stade de la maturité.

Un des principes de base du développement avec la JAMstack c’est que tout vit dans un dépôt Git, que ce soit les composants de notre site statique, les fichiers de configuration de notre générateur, nos fichiers CSS et JS, nos contenus écrits (sauvegardés sour forme de documents Markdown en texte brut). Avec votre service de déploiement et d’hébergement configuré pour refléter en permanence l’état de la branche de votre dépôt, appliquer une modification est aussi simple que de pousser un commit sur un dépôt GitHub. L’ensemble de votre site Web - le code et le contenu - vit dans un endroit centralisé, protégé par un versionnement robuste et peut être configuré pour être déployé en continu.

Oui mais et les clients dans tout ça ? Quid des utilisateurs non techniques ? Les experts de la production de contenu qui sont à l’aise avec des éditeurs comme celui de WordPress mais qui ne connaissent pas Markdown et GitHub ?

Le problème a été identifié il y a maintenant plusieurs années et beaucoup de solutions réjouissantes commencent à apparaître. Certaines sont extraodinairement simples. Si les éditeurs de vos contenus sont déjà familiers avec les bases de Markdown - c’est à dire # titre, **gras**, _italique_ - alors il n’y a aucune raison qu’il ne puissent éditer le dépôt sous-jacent. Des outils comme Prose.io s’intègrent à GitHub pour proposer une interface utilisateur plus adaptée pour les auteurs non techniques. Créez une branche pour les éditeurs de contenu puis fusionnez simplement leurs modifications pour publier de nouveaux contenus.

Sinon il y a aussi des dizaines de CMS “headless” qui sont parfaits pour les sites Web statiques. Ce sont avant tout des gestionnaires de contenus reposant sur une API qui permettent de dissocier vos contenus du côté client chargé de l’affichage de votre site. Siteleaf, par exemple qui fonctionne avec Jekyll et GitHub propose une édition dans le cloud compatible avec vos outils existants — comme c’est écrit sur leur site les sites Web devraient survivre à leurs CMS.

Comme je le disais, c’est un secteur qui se développe rapidement, vous serez confrontés à des challenges pour vous adapter à un workflow statique, particulièrement pour les projets ambitieux. Quiconque s’intéresse à l’utilisation de sites statiques pour un projet commercial ou à grande échelle devrait aller lire l’article de Stefan Baumgartner sur Smashing Magazine.

### Alors ce blog comment il est fait ?

Auparavant j'utilisais **WordPress**. 
Depuis que j'ai découvert la JAM stack, je ne cesse de l'utiliser dans mes projets perso/pro. En effet je me suis formé sur Hexo et Hugo qui sont deux générateurs de sites statiques performants et puissant, aujourd'hui je commence à me former sur Gatsby qui s'apparente à un framework react.

**Ce blog est créé avec HUGO et hébergé chez netlify le tous versionné sur github. Par ailleurs j'ai relié le CMS netlify avec lequel j'écrit cet article :). Afin de garder de meilleur performance j'utilise cloudinary pour le stockage et l'optimisation des images.**

La mouvance statique évolue grâce à l'émergence des technologies front-end, nous pouvons même créer des sites E-commerce en statique ! En effet grâce au service https://snipcart.com/fr nous connectons un panier d'achat en JS à notre site est le tour est joué ;).

Prochainement un article sur l'utilisation de la jam stack pour le e-commerce à bientôt.
