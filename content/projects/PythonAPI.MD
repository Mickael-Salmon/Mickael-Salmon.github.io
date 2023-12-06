---
title: " Créez une API sécurisée RESTful en utilisant Django REST"
date: 2023-04-01
tags: ["python", "API Restful", "Django", "backend", "Postman", "OWASP", "Green Code", "Poetry", "JWT", "authentification", "sécurité"]
draft: false
---
<p align="center">
<img src="https://legacy.python.org/community/logos/python-logo-master-v3-TM.png">
</p>

# Bienvenue !
## Vous trouverez ici le projet complet [GitHub Repository](https://github.com/Mickael-Salmon/OCP10) 👋

# Créez une API sécurisée RESTful en utilisant Django REST 💻 !

# Scénario SoftDesk Support API 🚀

Bienvenue sur le dépôt du projet **SoftDesk Support API** ! Notre mission est de fournir une solution de suivi des problèmes techniques pour les entreprises en B2B.

![SoftDesk Logo](https://user.oc-static.com/upload/2023/06/28/16879473703315_P10-02.png)

___

## 📌 Fonctionnalités

-   **Modèles d'objets** : Gérez efficacement vos objets dans notre application.
-   **Fonctionnalités principales** : Une suite complète d'outils pour le suivi des problèmes techniques.
-   **Points de terminaison d'API** : Une interface robuste pour servir des applications front-end sur différentes plateformes.

___

## 🛡️ Sécurité & Optimisation

-   **OWASP** : Respect des mesures de sécurité OWASP, authentification via JWT et permissions d'accès granulaires.
-   **RGPD** : Garantit la protection des données et la confidentialité des utilisateurs.
-   **Green Code** : Nous visons à optimiser et simplifier le code pour la sobriété énergétique.

___

## 📂 Documentation

1.  **Conception de la mise en œuvre** : Diagramme et description des modèles d'objets, fonctionnalités principales, et points de terminaison d'API.
2.  **Exigences de sécurité et d’optimisation** : Détails sur les spécifications OWASP, RGPD et Green Code.

___

## 📚 Rappel des tâches pour le Projet API SoftDesk

## Todo List pour le Projet SoftDesk

### OWASP et Sécurité
- [x] Authentification via JWT.
- [x] Autorisation et accès contrôlé pour les utilisateurs et contributeurs.
- [x] Gestion des dépendances avec Poetry pour minimiser les vulnérabilités.

### Green Code
- [x] Pagination des ressources pour réduire la charge serveur.
- [x] Optimisation des requêtes web.
- [x] Revue et optimisation du code source.
- [x] Gestion intelligente de l'hébergeur et des ressources.

### Exigences du Projet
- [x] Modèle `User` avec gestion du consentement.
- [x] Modèle `Contributor` pour lier utilisateurs et projets.
- [x] Modèle `Project` pour la gestion des projets.
- [x] Modèle `Issue` pour gérer les problèmes des projets.
- [x] Modèle `Comment` pour les commentaires sur les issues.
- [x] Implémentation de la confidentialité et des choix des utilisateurs.
- [x] Vérification de l'âge des utilisateurs lors de l'inscription.
- [x] Horodatage pour toutes les ressources.
- [x] Mise en place des permissions et des rôles d'accès.
- [x] Test des points de terminaison d'API avec Postman ou `curl`.



## 🖥️ Comment commencer ?

## 🛠️ Instructions d'installation

### Prérequis :

-   Avoir Python d'installé. Si ce n'est pas le cas, vous pouvez le télécharger [ici](https://www.python.org/downloads/).
-   [Poetry](https://python-poetry.org/), un outil pour la gestion des dépendances en Python.

### Étapes :

1.  **Clonage du dépôt :**

    ``` bash
    git clone https://github.com/Mickael-Salmon/OCP10.git
    cd OCP10
    ```

2.  **Installation de Poetry :**

    -   **Sur Linux/macOS :**

        ``` bash
        curl -sSL https://install.python-poetry.org | python3 -

        ```

    -   **Sur Windows (PowerShell) :**

        ``` powershell
        (Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python -

        ```

3.  **Installation des dépendances :**
    Utilisez Poetry pour installer les dépendances du projet.

    ``` bash
    cd softdeskAPI
    poetry install

    ```

4.  **Activation de l'environnement virtuel créé par Poetry :**

    -   **Sur Linux/macOS :**

        ``` bash
        poetry shell

        ```

    -   **Sur Windows :** Ouvrez une nouvelle fenêtre de terminal et naviguez vers le dossier du projet, puis exécutez :

        ``` powershell
        poetry shell

        ```

5.  **Effectuez les migrations initiales :**

    ``` bash
    cd softdeskAPI
    python manage.py migrate

    ```

6.  **Lancez le serveur de développement :**

    ``` bash
    cd softdeskAPI
    python manage.py runserver

    ```


Le serveur devrait démarrer, et l'API devrait être accessible à `http://localhost:8000/`.
