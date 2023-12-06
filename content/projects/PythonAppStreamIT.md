---
title: "Développez une interface utilisateur pour une application web Python"
date: 2023-08-01
tags: ["python", "django", "BD", "backend", "frontend", "HTML", "CSS", "Bootstrap", "JavaScript","Git", "GitHub"]
draft: false
---

<div align="center">
  <a href="" target="_blank" rel="noreferrer">
    <img src="https://www.python.org/static/community_logos/python-logo-master-v3-TM.png">
  </a>
</div>


<h3 align="center">

## Vous trouverez ici le projet complet [GitHub Repository](https://github.com/Mickael-Salmon/OCP6) 👋

</h3>

<h2 align="center">

Développez une interface utilisateur pour une application web Python 💻 !

</h2>

> Scénario
##

L’association JustStreamIt est connue pour ses newsletters de classement de films. Ces classements ont sauvé bien des soirées à ses abonnés toujours plus nombreux, comme le dit leur slogan : “Tu ne sais pas quoi regarder pour passer une bonne soirée ? Alors JustStreamIt”.

</br>

<div align="center">
  <a href="" target="_blank" rel="noreferrer">
    <img src="https://user.oc-static.com/upload/2020/09/18/16004298163529_P5.png">
  </a>
</div>



</br>


💬 Objectif :
- L’objectif est de récupérer les données des films depuis l’API à l’aide de requêtes ajax et de les afficher sur une interface web. Il faudra filtrer les données en fonction des critères que je te mentionnerai juste après. La mise à jour des données doit se faire automatiquement.

Nous te laissons choisir les trois catégories. Seule la catégorie “Films les mieux notés” est imposée et doit correspondre aux films les mieux notés selon le score Imdb. Les films qui appartiennent à plusieurs catégories (par exemple Avatar, inclus dans les catégories “Action, Adventure, Fantasy, Sci-Fi”) peuvent apparaître dans chacune de ces catégories distinctes.

</br>
💬 Fonctionnalités:

##
- L’interface doit comprendre les zones suivantes :
##

- “Meilleur film” : Cette zone affiche la photo du film qui a la meilleur note Imdb toutes catégories confondues, ainsi que son titre, un bouton et le résumé du film sous le bouton.
- “Films les mieux notés” : Cette zone affiche les 7 autres films les mieux notés toutes catégories confondues. On pourra les faire défiler avec une flèche à gauche et à droite comme sur la maquette pour tous les parcourir.
- “Catégorie 1” : Montre les 7 films les mieux notés d’une catégorie donnée.
- “Catégorie 2” : Montre les 7 films les mieux notés d’une autre catégorie.
- “Catégorie 3” : Idem sur une autre catégorie !

##
Les catégories 1, 2 et 3 sont au choix. Elles doivent être différentes et être indiqué au dessus de la zone des films à la place de “Catégorie 1”, 2 et 3 dans la maquette.
##

Lorsqu’on clique sur le bouton du film en vedette ou sur l’image d’un des films une fenêtre modale s’ouvre. Dans cette fenêtre les informations suivantes doivent être présente :

L’image de la pochette du film
Le Titre du film
Le genre complet du film
Sa date de sortie
Son Rated
Son score Imdb
Son réalisateur
La liste des acteurs
Sa durée
Le pays d’origine
Le résultat au Box Office
Le résumé du film

Un bouton permet de refermer la fenêtre modale. Il faudra utiliser de vanilla JavaScript pour gérer les événements de la page web.

</br>

💬 Contraintes techniques:

</br>

Le site doit fonctionner de façon similaire sur les trois navigateurs les plus utilisés actuellement.

En ce qui concerne les données nous utiliserons une API maison que nous avons baptisée OCMovies-API. Cette dernière n’est pas encore en ligne, mais le développeur qui s’est occupé du développement nous a fourni une version locale pour pouvoir faciliter la réalisation du front-end de notre application. Cette version de test de OCMovies-API se trouve sur [le dépôt de code suivant](https://github.com/OpenClassrooms-Student-Center/OCMovies-API-EN-FR).

> Livrables attendus 🔭
##

Code source complet du projet (HTML, CSS, JS).

</br>

> Structure de dossiers du projet
##

```
├── HTML
│   ├── Index.html
├── CSS
│   ├── JustStreamIT/style.css
└── JS
    ├── JustStreamIT/main.js



```


<h2> Installation et démarrage du projet</h2>

<h3>Démarrer le server en local </h3>
L'utilisation de l'API RestFull OCMovies-API est nécessaire pour le bon fonctionnement de l'application.</br>
Se référer à la documentation pour démarrer le server en local.</br>
[Lien vers la documentation](https://github.com/OpenClassrooms-Student-Center/OCMovies-API-EN-FR)



<h3>Récupération du projet</h3>

$ git clone https://github.com/Mickael-Salmon/OCP6/

<h3>Lancer le programme </h3>

Depuis un terminal , se déplacer dans le dossier applicatif souhaité :</br>
$ Ouvrir Index.html dans un navigateur web
