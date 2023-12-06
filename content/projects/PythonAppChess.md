---
title: "Développez un programme logiciel en Python - Gestion de tournois d'échecs"
date: 2023-01-01
tags: ["python", "django", "BD", "backend", "frontend", "HTML", "CSS", "Bootstrap", "JavaScript","Git", "GitHub"]
draft: false
---


<div align="center">
  <a href="" target="_blank" rel="noreferrer">
    <img src="https://www.python.org/static/community_logos/python-logo-master-v3-TM.png">
  </a>
</div>

## Vous trouverez ici le projet complet [GitHub Repository](https://github.com/Mickael-Salmon/OCP7) 👋


## Scénario

Vous êtes un développeur junior depuis deux mois et vous travaillez en freelance pour écrire des scripts simples afin d’aider les petites entreprises locales à gérer leur inventaire. 

Elie, votre amie et elle aussi développeuse Python, est membre du club d'échecs local. Elle vous a expliqué que les tournois du club sont actuellement organisés à la main, mais que les membres du club aimeraient pouvoir les gérer avec un logiciel. Le club avait trouvé une application convenable, mais elle avait besoin d’une connexion Internet – qui n'est pas disponible pour tous les tournois – et l'abonnement mensuel était trop cher.

<p align="center" <a href="" class="oc-imageLink oc-imageLink--disabled"><img src="https://user.oc-static.com/upload/2020/09/22/16007793690358_chess%20club-01.png" alt="Logo du club d'échecs"></a>>
</p>


</br>

- 💬 Vous suggérez que vous pourriez écrire un outil qui permette de gérer les tournois pour aider le club, mais qui fonctionne hors ligne. Elie aime bien votre idée et elle dit qu'elle en discutera la prochaine fois qu'elle se rendra au club. Comme elle s’occupe déjà de plusieurs contrats en freelance, elle accepte de vous recommander comme candidat idéal pour développer cette application.

## Livrables attendus 🔭


-   Le code de l'application, tel que prescrit dans la spécification technique
-   Un répertoire contenant un fichier HTML, généré par **flake8-html**, ne montrant aucune erreur de peluchage dans le code
-   Un fichier **README.md** contenant des instructions claires sur la manière d'exécuter le programme, de l'utiliser et de générer un nouveau fichier flake8-html

</br>


## Structure de dossiers du projet

```
├── controllers
│   ├── __init__.py
│   ├── menu_controller.py
│   ├── reports_controller.py
│   └── tournament_controller.py
│   └── user_Input_validation.py
├── models
│   ├── __init__.py
│   ├── player_model.py
│   ├── round_model.py
│   └── tournament_model.py
└── views
│   ├── __init__.py
│   ├── menu_view.py
│   ├── reports_view.py
│   └── round_view.py
└── database
│   ├── players.json
│   ├── tournaments.json

```

Les fichiers `__init__.py` sont nécessaires pour que Python reconnaisse le dossier comme un module.

Le dossier `controllers`, contient la logique de contrôle, tels que la gestion des tournois, la génération de rapports et le menu principal.

Le dossier `models` contient les modèles pour les entités dans votre programme, tels que les tournois, les rondes et les joueurs.

Le dossier `views` contient tous les fichiers qui concernent l'interface utilisateur, tels que les vues pour les rondes, les rapports et le menu principal.
Le dossier `database` contient tous les fichiers relatifs aux stockage d'information pour les joueurs et les tournois par TinyDB au format JSON.

## Installation et démarrage du projet
### Windows

Depuis un terminal , se déplacer dans le dossier applicatif souhaité :

### Récupération du projet

```
git clone https://github.com/Mickael-Salmon/OCP4/
```

### Activer l'environnement virtuel

```
cd OCP4
```
```
python -m venv .envOCP4
```
```
~env\scripts\activate
```


### Installer les paquets requis

```
pip install -r requirements.txt
```

### Lancer le programme

```
python main.py
```

## MacOS et Linux :

Depuis un terminal, se déplacer dans dossier souhaité.

### Récupération du projet

```
git clone https://github.com/Mickael-Salmon/OCP4/
```

### Activer l'environnement virtuel

```
cd OCP4
```

```
python3 -m venv .envOCP4
```

```
source .envOCP4/bin/activate
```

### Installer les paquets requis

```
pip install -r requirements.txt
```

### Lancer le programme

```
python main.py
```

### Générer un nouveau rapport flake8

```
flake8 --format=html --htmldir=flake8_reportv2 --exclude=.env/ --max-line-length=119
```