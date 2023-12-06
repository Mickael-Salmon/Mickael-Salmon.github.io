---
title: "Mettez à l'échelle une application Django en utilisant une architecture modulaire - Déploiement CI/CD"
date: 2023-11-01
tags: ["python", "crm", "backend", "frontend", "postgresql", "CI/CD", "docker", "sentry", "readthedocs", "sphinx", "circleci", "render", "django", "django-rest-framework", "sqlite", "git"]
draft: false
---

<p align="center">
<img src="https://legacy.python.org/community/logos/python-logo-master-v3-TM.png">
</p>

## Vous trouverez ici le Projet complet : [GitHub Repository](https://github.com/Mickael-Salmon/OCP13/) 👋

# Mettez à l'échelle une application Django en utilisant une architecture modulaire 🏗️

![Orange County Lettings](https://user.oc-static.com/upload/2023/07/20/1689880374259_Orange%20County%20Lettings%20Ad.png)

## Résumé 📋
Orange County Lettings est une start-up dans le secteur de la location de biens immobiliers. La start-up est en pleine phase d’expansion aux États-Unis.

## Objectif 🎯

- [x] Refonte de l'architecture modulaire dans le repository GitHub
- [x] Réduction de diverses dettes techniques sur le projet
- [x] Ajout d'un pipeline CI/CD ainsi que son déploiement
- [x] Surveillance de l’application et suivi des erreurs via Sentry
- [x] Création de la documentation technique de l’application avec Read The Docs et Sphinx

### Site web d'Orange County Lettings 🌐

[https://oc-letting-site.onrender.com/](https://oc-letting-site.onrender.com/)

## Développement local 💻

### Prérequis 🛠️

- Compte GitHub avec accès en lecture à ce repository 📚
- Git CLI 🖥️
- SQLite3 CLI 💾
- Interpréteur Python, version 3.6 ou supérieure 🐍

Dans le reste de la documentation sur le développement local, il est supposé que la commande `python` de votre OS shell exécute l'interpréteur Python ci-dessus (à moins qu'un environnement virtuel ne soit activé).

### macOS / Linux 🍏

#### Cloner le repository 📥

- `cd /path/to/put/project/in`
- `git clone https://github.com/OpenClassrooms-Student-Center/Python-OC-Lettings-FR.git`

#### Créer l'environnement virtuel 🌐

- `cd /path/to/Python-OC-Lettings-FR`
- `python -m venv venv`
- Activer l'environnement `source venv/bin/activate`
- Confirmer que la commande `python` exécute l'interpréteur Python dans l'environnement virtuel
`which python`
- Confirmer que la version de l'interpréteur Python est la version 3.6 ou supérieure `python --version`
- Confirmer que la commande `pip` exécute l'exécutable pip dans l'environnement virtuel, `which pip`
- Pour désactiver l'environnement, `deactivate`

#### Installer les dépendances 📦

- `pip install --requirement requirements.txt`

#### Exécuter le site 🌍

- `cd /path/to/Python-OC-Lettings-FR`
- `source venv/bin/activate`
- `pip install --requirement requirements.txt`
- `python manage.py runserver`
- Aller sur `http://localhost:8000` dans un navigateur.
- Confirmer que le site fonctionne et qu'il est possible de naviguer (vous devriez voir plusieurs profils et locations).

#### Linting 🔍

- `cd /path/to/Python-OC-Lettings-FR`
- `source venv/bin/activate`
- `flake8`

#### Tests unitaires 🧪

- `cd /path/to/Python-OC-Lettings-FR`
- `source venv/bin/activate`
- `pytest`

#### Base de données 💽

- `cd /path/to/Python-OC-Lettings-FR`
- Ouvrir une session shell `sqlite3`
- Se connecter à la base de données `.open oc-lettings-site.sqlite3`
- Afficher les tables dans la base de données `.tables`
- Afficher les colonnes dans le tableau des profils, `pragma table_info(Python-OC-Lettings-FR_profile);`
- Lancer une requête sur la table des profils, `select user_id, favorite_city from Python-OC-Lettings-FR_profile where favorite_city like 'B%';`
- `.quit` pour quitter

#### Panel d'administration 🛠️

- Aller sur `http://localhost:8000/admin`
- Connectez-vous avec l'utilisateur `admin`, mot de passe `*******`

### Windows 🖥️

Utilisation de PowerShell, comme ci-dessus sauf :

- Pour activer l'environnement virtuel, `.\venv\Scripts\Activate.ps1`
- Remplacer `which <my-command>` par `(Get-Command <my-command>).Path`

## Docker 🐳

Pour exécuter l'environnement en local avec docker, un fichier docker est fourni.

`docker build -t oc_letting_site .`

`docker run -p 8000:8000 oc_letting_site`

## Documentation 📚

### Documentation technique

[Documentation Projet](https://ocp13-oc-lettings-site.readthedocs.io/fr/latest/index.html)

## Références 📖

- [Django](https://www.djangoproject.com/)
- [Django REST Framework](https://www.django-rest-framework.org/)
- [Sphinx](https://www.sphinx-doc.org/en/master/)
- [Read The Docs](https://readthedocs.org/)
- [Sentry](https://sentry.io/)
- [Docker](https://www.docker.com/)
- [CircleCI](https://circleci.com/)
- [Render](https://render.com/)
- [Python](https://www.python.org/)
- [SQLite](https://www.sqlite.org/index.html)
- [Git](https://git-scm.com/)

