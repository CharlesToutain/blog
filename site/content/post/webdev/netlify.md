---
title: Netlify
description: Article de blog qui décrit les avantages et fonctionnalités qu'offre l'hébergeur netlify. C'est un hébergeur spécialisé dans les sites statiques et architectures à base de JAM stack.
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
date: '2014-06-03T00:41:00+02:00'
image: >-
  https://res.cloudinary.com/ctinformatique/image/upload/q_100/v1528234756/blog/netlify.jpg
---
# Netlify hébergeur spécialisé 

En quelques temps Netlify est devenu un acteur majeur de l’écosystème JAMstack - ils sont d’ailleurs à l’origine de cette appellation - et des sites statiques. Actuellement le blog que vous lisez est hébergé sur un CDN de netlify, c'est le genre d'entreprise qui a réussie à convertir ses clients en véritables ambassadeurs !

 la contraction de Net et Simplify (netlify) a pour but de simplifier la mise en production et de fournir tous les outils modernes nécessaires à des stratégies de déploiement agiles à tout un chacun, sans avoir besoin pour cela d’être un devops confirmé. Ce n’est pas simplement une solution pour héberger vos sites statiques à moindre frais, le passage de Smashing Magazine à une architecture JAMstack hébergée par Netlify a montré que ça pouvait aller bien au delà en faisant appel à différentes APIs et microservices.

Phil Hawksworth, nouvellement en charge des relations avec les développeurs chez Netlify a publié une liste de fonctionnalités disponibles quelle que soit la formule utilisée, même celle entièrement gratuite.

Donc en résumé netlify c'est un hébergeur spécialisé dans les sites statiques ! 

## Mais comment on héberge ?

Si vous ne connaissez pas encore ce service, sachez que c’est extrêmement simple d’héberger un site chez Netlify. Nul besoin de connaître toutes les fonctionnalités avancées pour vous lancer.

La manière la plus simple d’héberger un site chez Netlify est de glisser-déposer un dossier contenant vos fichiers dans un navigateur sur <https://app.netlify.com.>

Vous pouvez visionner ce tuto youtube ;)

<https://www.youtube.com/watch?v=fiw2P-UAlII>

Vous pouvez aussi déployer via le protocole git ! Compatible avec gitlab, github et bitbucket.

## 1. Déploiements intergalactiques !

Si vous avez déjà rencontré des problèmes de mise en production ou de déploiement sur des projets de développement web, vous apprécierez grandement cette fonctionnalité.

Chaque génération réussie sur Netlify entraîne le déploiement d’une nouvelle instance de votre site. La publication sur les différents extrémités des nœuds du réseau de CDN de Netlify et l’invalidation de cache se font automatiquement et de manière quasi-instantanée, à tel point que que je trouve inutile de mesurer combien de temps ça prend.

Les déploiements sont immutables. Cela signifie que chaque résultat de déploiement correspond à une version du site qui ne changera jamais. Les mises à jour créent de nouvelles instances du site pour remplacer les versions précédentes (qui sont gentiment remerciées pour leur service et mises au repos, sans être supprimées pour autant). Cela veut dire que vous pouvez revenir à tout moment à une version précédente de votre site d’un simple clic dans l’interface d’administration ou via l’API.

En fait, tout ce que vous pouvez faire dans l’interface d’administration, vous pouvez le faire aussi avec l’API. La documentation de l’API vous explique comment faire tout cela. 

Netlify est synchronisé avec votre dépôt git ! Vous avez exactement la même chose en local et en ligne.

## 2. Notifications et permaliens

Une fois encore, il y a plus d’une fonctionnalité dans cet élément de ma liste, il faudra vous y faire.

Netlify vous permet de configurer des notifications en fonction des différents types d’évènement liés à un déploiement. Vous pouvez définir qui sera informé en cas de nouveau déploiement, ou lorsqu’un déploiement réussit, échoue, est verrouillé ou déverrouillé (je ne vous ai pas dit mais on peut aussi choisir de faire pointer la version du site vers un déploiement en particulier).

Vous pouvez envoyer des notifications par mail ou sur un canal Slack (je suis fan, tous mes projets ont un canal Slack dédié à l’intégration continue). Vous pouvez même décider qu’une notification va déclencher un webhook, ajouter des messages à des commits Git ou commenter sur des pull requests.

Ce qui rend ces notifications encore plus utiles, c’est qu’elles incluent un lien unique vers le déploiement en question. Je vous ai dit que tous les déploiements sont immutables et toujours actifs. Cela signifie que chacun d’eux possède sa propre URL pour qu’on puisse y accéder et voir ce déploiement en particulier.

Avoir des liens uniques pour chaque déploiement c’est énorme. Vous pouvez partager à tout moment n’importe quelle version de votre site avec votre équipe en charge des tests, votre client, ou n’importe qui d’autre. « À quoi ressemblait la version 3.2.14 du site déjà ? Tiens, voilà le lien. »

Et cet accès instantané vous est partagé directement à chaque notification.

 Vous pouvez aussi grâce à cela faire de l'AB testing ! En effet il suffit de définir des branches de déploiements différents pour un même site.

## 3. Sous-domaines et branches

C’est bien pratique de pouvoir déployer d’autres branches que celle de production. Pouvoir développer de nouvelles fonctionnalités dans des branches dédiées et ensuite pouvoir les tester et les passer en revue sur votre environnement de production, c’est incroyablement puissant.

Netlify vous permet de garder le contrôle sur la façon dont vous déployez. Vous pouvez choisir de déployer uniquement la branche de production, toutes vos branches, ou seulement certaines branches.

Une fois déployée, chaque branche sera accessible depuis un sous-domaine généré en fonction du nom de la branche utilisée. Ça donne un truc comme ça :

ma-branche--mon-site.netlify.com

Grâce à la gestion des DNS de Netlify, vous pouvez aussi choisir d’affecter vos propres sous-domaines à des branches. Vous avez une liberté totale pour définir comment les différentes branches vont pousser du contenu sur les différents sous-domaines de votre site.

## 4. Tests A/B, Tests A/B avec plusieurs variantes ou tests séparés

Il existe plusieurs variantes et termes pour désigner les tests A/B, Netlify appelle cela le split testing parce que c’est ce que ça fait : découper le trafic de votre site entre les différentes branches de votre choix.

Vous pouvez partager le trafic de votre site en autant de branches que vous le souhaitez et définir le pourcentage de trafic attribué à chacune des branches.

L’approche de Netlify c’est de servir chaque variante de test directement depuis son CDN optimisé. Tous les trucs comme la répartition du trafic, les variantes de tests et l’assurance de la consistance d’utilisation se passent au niveau du CDN - sur les nœuds les plus proches possibles de l’utilisateur.

## 5. Gestion des certificats SSL et SSL gratuit avec Let’s Encrypt

Même si ce n’est pas forcément évident à première vue, il est très important de servir les sites web en HTTPS plutôt qu’en HTTP, même si ce sont des sites servis en statique.

Un des créateurs de Netlify explique tout ça très bien en donnant cinq bonne raisons de servir votre site en HTTPS et Google a également publié de bons articles qui expliquent pourquoi HTTPS est si important, quelle que soit l’architecture utilisée.

Vous êtes convaincu et vous voulez acheter un certificat numérique ? N’ayez crainte, l’opération peut être bien plus simple que vous ne pourriez le penser.

Netlify rend triviale la configuration de HTTPS sur vos noms de domaines.Vous avez le choix entre la gestion automatisée de SSL, la gestion personnalisée de SSL et même une adresse IP dédiée SSL pour les entreprises qui en ont besoin.

La plupart des gens peuvent se contenter de la gestion automatisée grâce aux certificats offerts par Let’s Encrypt. La configuration se fait en 1 min . En plus le certificat est renouvelé automatiquement, pour que vous n’ayez pas à le faire tous les ans.

## 6. Lancer des tests avec l’intégration continue de Netlify

Une des choses qui fait que Netlify est très puissant c’est qu’en plus d’un réseau optimisé de CDN pour héberger vos sites, ils fournissent aussi un environnement de conteneurs pour lancer vos builds. Cela signifie que n’importe quel build lancé dans votre environnement de développement ou sur un serveur d’intégration continue peut en fait être directement exécuté sur Netlify.

Si votre script de déploiement inclus des tests, Netlify les exécutera pour vous et qu’il en résulte un succès ou un échec, vous serez prévenus de l’issue finale.

## 7. Gestion des formulaires

Si votre site a besoin d’intégrer des formulaires, vous vous êtes peut-être dit par le passé que ce n’était pas compatible avec un site statique. Pourtant Netlify propose une solution simple pour régler ce problème.

Si vous avez besoin d’ajouter un formulaire sur votre site qui récolte des informations entrées par vos utilisateurs, Netlify peut s’en charger pour vous. En ajoutant un simple attribut au code HTML de votre formulaire, Netlify va exposer le point d’accès qui va bien pour le formulaire et rendre toutes les données postées accessibles pour vous depuis l’interface d’administration et l’API.

Comme les données sont accessibles via l’API, vous pouvez accéder à ces contenus lors de l’étape de génération afin de les utiliser sur votre site. Avec un peu d’imagination, cela ouvre pas mal de possibilités intéressantes.

Les soumissions de formulaires peuvent aussi déclencher des notifications. Tout devient alors possible : des messages Slack, des webhooks ou même des intégrations Zapier.

Actuellement j'utilise Formspree <https://formspree.io/> qui est très simple d'utilisation et d'intégration, cependant pour avoir regardé le service forms de netlify celui-ci me semble plus complet. Je vais donc prochainement tester la solution de formulaire de netlify;

## 8. Redirection 

En ajoutant un fichier _redirects dans votre dossier déployé nous avez accès à tout plein d’options de configuration en ce qui concerne les redirections et les réécritures d’URLs. Elles sont déclenchées sur les nœuds finaux des CDN, ce qui les rend particulièrement rapides et efficientes.

Vous avez aussi la possibilité de préciser le code de réponse HTTP dans le fichier _redirects, ce qui vous permet de personnaliser vos erreurs 404 ou même de rendre d’autres ressources accessibles au travers d’un proxy.

## 9. En tête HTTP

Celui là ravira toux ceux qui ont hébergé leur site sur GitHub Pages et qui ont couru après le score parfait sur Lighthouse ou Page Speed Insights. Vous avez tout bien fait, mais vous avez besoin de pouvoir définir vos entêtes de cache HTTP pour bénéficier de cette dernière optimisation de performance qui vous manque tant… malheureusement vous n’en avez pas la possibilité.

Netlify utilise  une approche similaire à celle de la gestion des redirections que nous venons de voir plus haut. Grâce à un fichier _headers déposé dans votre dossier de déploiement, vous pouvez ainsi contrôler les entêtes HTTP de toutes les ressources de votre site.

Vous avez la possibilité de configurer vos entêtes à l’aide de fichier _headers vous permet de définir votre politique de sécurité en matière de contenu (CSP), vos options X-Frame et plein d’autres choses toutes aussi importantes pour vous aider à contrôler la sécurité de votre site.

## 10. Nom de domaine

Vous pouvez utiliser votre propre nom de domaine pour cela Vous devrez pointer les enregistrements DNS du domaine sur les serveurs de Netlify. Vous pouvez aussi utiliser un nom de domaine gratuit entièrement personnalisable seulement l'extension .netlify sera présente.

## 11. Netlify CMS

En effet netlify à développer son propre CMS headless ( développé en REACT ).  Ce CMS permet de ce relié à n'importe quel dépôt git, cependant il reste optimisé pour github mais des travaux sont en cours pour gitlab et bitbucket.  Le cms permet via une interface user friendly d'ajouter du contenu  textuelles ou images. 

On peut créer des customs post field, types via netlify CMS de manière à pouvoir personnaliser à volonté le CMS. A l'heure actuelle j'écrit avec ce CMS et il me sert en production déjà pour plusieurs sites. Un article complet sera fait sur ce CMS.

## 12. Bonus 

J'ai parlé des fonctionnalités de netlify, j'aimerai vous parler rapidement d'autres services que j'utilise régulièrement pour mes sites avec une architectures jam stack.

### Disqus
C'est un service de gestion des commentaires qui permet de gérer les commentaires laissé sur votre site ( actuellement ce qui est utilisé pour mon blog ). 

### Snipcart
Un panier d'achat e-commerce en javascript ! Il suffit de relié snipcart à votre site statique et vous bénéficiez d'une boutique en ligne, il me servira prochainement quand je mettrais à la vente mes formations.

### Cloudinary
Possibilité d'héberger vos images sur cloudinary ! Ce service web met à disposition vos images et les optimises pour vous.

## A retenir 
Même si vous optez pour un site avec une architecture JAM stack, il existe énormément de services et d'APIS à relier sur votre site statique pour gérer les différentes parties dynamiques. Cependant même si vous externaliser l'expertises métiers vous avez moins la main sur vos données, alors bien penser à choisir les prestataires et sauvegarder les données.

Voila maintenant vous connaissez netlify et vous en savez plus sur les possibilités de stack statique. Si vous êtes intéressé n'hésitez pas à laisser un commentaire ou à me contacter.
