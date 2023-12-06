---
title: "Développez un programme logiciel en Python - Gestion de tournois d'échecs"
date: 2022-12-01
tags: ["python", "script", "web scraping", "Git", "GitHub", "request", "BeautifulSoup", "Pandas", "csv", "html"]
draft: false
---


<h3 align="center">

## Vous trouverez ici le projet complet [GitHub Repository](https://github.com/Mickael-Salmon/OCP2) 👋

</h3>

<h2 align="center">

# Utilisez les bases de Python pour l'analyse de marché 💻 !

</h2>

> Scénario 💬
> ###

Vous êtes analyste marketing chez Books Online, une importante librairie en ligne spécialisée dans les livres d'occasion. Dans le cadre de vos fonctions, vous essayez de suivre manuellement les prix des livres d'occasion sur les sites web de vos concurrents, mais cela représente trop de travail et vous n'arrivez pas à y faire face : il y a trop de livres et trop de librairies en ligne ! Vous et votre équipe avez décidé d'automatiser cette tâche laborieuse via un programme (un scraper) développé en Python, capable d'extraire les informations tarifaires d'autres librairies en ligne.



<p align="center" href="" class="oc-imageLink oc-imageLink--disabled"><img src="https://user.oc-static.com/upload/2020/09/22/1600779540759_Online%20bookstore-01.png"></p>


</br>


> Livrables attendus 🔭
> ##

1.  Un document TXT ou PDF contenant le lien vers le **repository GitHub** public qui doit contenir les éléments suivants:

-   l'ensemble de votre code d'application ;
-   le fichier requirements.txt, mais pas l'environnement virtuel lui-même ;
-   un fichier README.md expliquant comment créer et activer l'environnement virtuel, puis exécuter le code d'application ;
-   les données/images extraites ne doivent pas faire partie du repository lui-même.

3.  Un fichier compressé ZIP contenant toute la **data** : les **données extraites et les images associées** dans un format ou une structure facile à suivre.
4.  Un **mail** (pas plus d’une page) **au responsable d’équipe**, Sam, décrivant comment l’application permet d’établir un pipeline ETL, au format PDF.

</br>


<h2> Installation et démarrage du projet</h2>
<h3>Windows</h3>

Depuis un terminal , se déplacer dans le dossier applicatif souhaité :

<h3>Récupération du projet</h3>

$ git clone https://github.com/MicSa/public/

<h3>Activer l'environnement virtuel </h3>

#### Création de l'environnement virtuel

```cd public```
```python -m venv env```
```source env/bin/activate```

#### Installation des packages/modules

```pip install -r requirements.txt```

### Utilisation
Lancer le script ```codeSHOW.py```

4 options sont proposées :
- Télécharger par URL
- Télécharger par catégorie
- Télécharger l'intégralité
- Quitter

Les fichiers csv sont ouvrables avec un tableaur.

### Version Python
Python 3.10.9 (main, Dec 19 2022, 17:35:49) [GCC 12.2.0] on linux

<h2>MacOS et Linux : </h2>

#### Création de l'environnement virtuel

```cd public```
```python -m venv env```
```source env/bin/activate```

#### Installation des packages/modules

```pip install -r requirements.txt```

### Utilisation
Lancer le script ```codeSHOW.py```

4 options sont proposées :
- Télécharger par URL
- Télécharger par catégorie
- Télécharger l'intégralité
- Quitter

Les fichiers csv sont ouvrables avec un tableaur.

### Version Python
Python 3.10.9 (main, Dec 19 2022, 17:35:49) [GCC 12.2.0] on linux
<h3>Lancer le programme </h3>

$ python ```codeSHOW.py```
