---
title: "Développez une architecture back-end sécurisée avec Python et SQL"
date: 2023-04-01
tags: ["python", "crm", "backend", "frontend", "postgresql", "sqlalchemy", "jwt", "sentry", "rich", "pytest", "faker", "factoryboy", "bcrypt", "cryptography", "datetime"]
draft: false
---

<p align="center">
<img src="https://legacy.python.org/community/logos/python-logo-master-v3-TM.png">
</p>

# Bienvenue !
## Vous trouverez ici le Projet 12 du parcours Développeur d'application - Python 👋

# Développez une architecture back-end sécurisée avec Python et SQL

![Epic Events](https://user.oc-static.com/upload/2023/07/26/16903799358611_P12-02.png)

[GitHub Repository](https://github.com/Mickael-Salmon/OCP12/)

# Contexte

Epic Events est une entreprise qui organise des événements (fêtes,
réunions professionnelles, manifestations hors les murs) pour ses clients. Ils souhaitent développer un logiciel CRM (Customer Relationship
Management) pour améliorer leur travail.
Le logiciel CRM permet de collecter et de traiter les données des clients
et de leurs événements, tout en facilitant la communication entre les
différents pôles de l'entreprise.

# Comment Epic Events fonctionne

Nos équipes opérationnelles sont divisées en trois départements :
● le département commercial
● le département support
● le département gestion

Les commerciaux démarchent les clients. Ils créent et mettent à jour
leurs profils sur la plateforme. Lorsqu’un client souhaite organiser un
événement, un collaborateur du département gestion crée un contrat et
l’associe au client.

# Exigences techniques et de sécurité

Vous devrez utiliser Python 3 (la version 3.9 ou une version plus
récente).
● L’application sera faite en ligne de commande.
● Vous devrez empêcher les injections SQL.
● Vous devrez mettre en œuvre et faire appliquer le principe du
moindre privilège lors de l'attribution de l'accès aux données.

Veillez à ce que les utilisateurs n'aient accès qu'aux données dont
ils ont besoin.

● Une journalisation utile et efficace sera mise en place avec Sentry :
les applications doivent consigner les exceptions et les erreurs
produites

Une fois le contrat signé, le commercial crée l’événement dans la
plateforme et le département gestion désigne un membre du
département support qui sera responsable de l’organisation et du
déroulé de l’événement.

# Sécurité et top 10 OWASP

-   **Authentification Robuste**: L'application implémente une authentification des utilisateurs pour protéger contre les risques tels que l'**A01:2021 - Broken Access Control**.

-   **Gestion de Session Sécurisée**: Les tokens JWT sont utilisés pour maintenir l'état de connexion pour aide à prévenir les problèmes liés à l'**A02:2021 - Cryptographic Failures**.

-   **Stockage Sécurisé des Mots de Passe**: Les mots de passe sont hachés et salés avec `bcrypt` pour contrer l'**A02:2021 - Cryptographic Failures**.

-   **Contrôle d'Accès Basé sur les Rôles**: Des décorateurs tels que `@admin_required` et `@authenticated` sont utilisés pour restreindre l'accès à certaines fonctionnalités, relevant de l'**A01:2021 - Broken Access Control**.

-   **Validation des Entrées Utilisateur**: Le code utilise des validations pour les champs tels que les emails, les numéros de téléphone et force une complexité de mots de passe ce qui peut contribuer à atténuer les risques d'**A03:2021 - Injection**.

-   **Gestion des Erreurs**: Les erreurs sont gérées correctement pour ne pas exposer des détails sensibles, ce qui correspond à l'**A04:2021 - Insecure Design**.

-   **HTTPS/SSL**: Bien que non mentionné explicitement dans le code, l'utilisation de protocoles sécurisés pour la communication est essentielle pour l'**A02:2021 - Cryptographic Failures**. L'application s'exécutant uniquement depuis le terminal, il est envisageable d'effectuer une connexion SSH depuis un ordinateur distant pour accéder à l'application, profitant ainsi d'une connexion sécurisée via les paires de clés privées/publiques associées au fonctionnement de SSH.

-   **Journalisation et Surveillance**: L'application implémente une  journalisation des erreurs avec `Sentry`qui pourrait être étendue pour surveiller les activités suspectes, pertinent pour l'**A08:2021 - Software and Data Integrity Failures**.

-   **Protection contre les injesctions SQL**: L'application utilise des requêtes paramétrées pour prévenir les injections SQL, ce qui est une bonne pratique pour lutter contre l'**A01:2021 - Broken Access Control** et le code utilise l'ORM SQLAlchemy, qui, par défaut, aide à prévenir les injections SQL en utilisant des requêtes paramétrées plutôt que de construire des requêtes SQL à partir de chaînes concaténées. C'est une mesure de protection supplémentaire contre l'**A03:2021-Injection** du Top 10 OWASP.
-   **Le système de gestion des droits d'accès** (`accesscontrol`) dans l'application respecte le principe du moindre privilège, qui est une pratique de sécurité fondamentale, correspondant à l'**A05:2021-Security Misconfiguration** du Top 10 OWASP. Voici ce qui a été implémenté :
-   **Authentification et gestion des sessions** : Les utilisateurs doivent se connecter pour accéder à l'application, garantissant que seules les personnes authentifiées peuvent interagir avec le système.
-   **Contrôles d'accès basés sur les rôles** (`@admin_required`, `@authenticated`): Les décorateurs vérifient les rôles et les permissions avant d'accéder à certaines fonctions, s'assurant que les utilisateurs ne peuvent exécuter que les actions autorisées.
- **Permissions restreintes** : Les actions sont limitées en fonction des rôles de l'utilisateur, par exemple, seuls les administrateurs peuvent accéder aux fonctions d'administration des employés.
- **Gestion des tokens JWT** : L'application utilise des tokens JWT pour gérer les sessions, limitant l'accès aux utilisateurs avec un token valide.
- **Gestion des mots de passe** : Les mots de passe sont hachés avec `bcrypt`, une bonne pratique pour contrer l'**A02:2021 - Cryptographic Failures**.
- **Le CRUD a été implémenté** via les models : CRUD est un acronyme pour Create, Read, Update, Delete, qui sont les quatre opérations de base pour la persistance des données.

    | Operation | Description                                      |
    |-----------|--------------------------------------------------|
    | Create    | Créer de nouvelles entrées dans la base de données.     |
    | Read      | Lire ou récupérer des données existantes.               |
    | Update    | Mettre à jour ou modifier des données existantes.       |
    | Delete    | Supprimer des données existantes.                      |

- **Modèles SQLAlchemy** : Les models définissent les droits d'accès aux données pour les utilisateurs afin d'aider à lutter contre l'**A01:2021 - Broken Access Control**.
- **Utiliser une table `user_sessions`** sur la BD pour gérer les tokens de session pour adresser les points suivants :
- **Contrôle de session centralisé** : Les sessions peuvent être gérées de manière centralisée, ce qui permet aux administrateurs de révoquer l'accès immédiatement si nécessaire.
- **Minimisation des risques de vol de tokens** : Stocker les tokens côté serveur au lieu de les laisser sur le disque dur de l'utilisateur réduit le risque que ces tokens soient volés par des malwares ou fuités à travers des attaques XSS.
- **Gestion fine des accès** : Permet d'implémenter des stratégies de sécurité telles que l'expiration de session ou des vérifications de sécurité supplémentaires pour des actions sensibles.Nous avons implémenté le login, logout et expiration de session.
- **Conformité aux bonnes pratiques de sécurité** : Respecte le principe de moindre privilège et s'aligne avec les recommandations OWASP pour la gestion des sessions et des authentifications.


# Estimation de livraison

L’application CRM doit être livrée dans deux mois.

# Les clients

| Information                        | Exemple               |
|------------------------------------|-----------------------|
| Nom complet                        | Kevin Casey           |
| Email                              | kevin@startup.io      |
| Téléphone                          | +678 123 456 78       |
| Nom de l’entreprise                | Cool Startup LLC      |
| Date de création (premier contact) | 18 avril 2021         |
| Dernière mise à jour/contact       | 29 mars 2023          |
| Contact commercial chez Epic Events| Bill Boquet           |

# Les contrats

Un contrat contient :
● un identifiant unique ;
● les informations sur le client ;
● le contact commercial pour le contrat (= le commercial associé au
client) ;
● le montant total du contrat ;
● le montant restant à payer ;
● la date de création du contrat ;
● le statut du contrat (= si le contrat a été signé).

# Les événements

À l’heure actuelle, le département support utilise une feuille Excel pour
suivre les événements. Voici deux exemples d’événements :

## Exemple 1

| A                 | B                                                  |
|-------------------|----------------------------------------------------|
| 1                 | John Ouick Wedding                                 |
| 2                 | Event ID 109                                       |
| 3                 | Contract ID 652                                    |
| 4                 | Client name John Ouick                             |
| 5                 | Client contact john.ouick@gmail.com <br>+1 234 567 8901 |
| 6                 | Event date start 4 Jun 2023 @ 1PM                  |
| 7                 | Event date end 5 Jun 2023 @ 2AM                    |
| 8                 | Support contact Kate Hastroff                      |
| 9                 | Location 53 Rue du Château, 41120 Candé-sur-Beuvron, France |
| 10                | Attendees 75                                       |
| 11                | Notes Wedding starts at 3PM, by the river. <br> Catering is organized, reception starts at 5PM. |

## Exemple 2

| A                 | B                                                               |
|-------------------|-----------------------------------------------------------------|
| 1                 | Lou Bouzin General Assembly                                     |
| 2                 | Event ID 1023                                                    |
| 3                 | Contract ID 412                                                  |
| 4                 | Client name Lou Bouzin                                           |
| 5                 | Client contact Jacky Blangier <br>jacky@loubouzin.grd <br>+ 666 12345 |
| 6                 | Event date start 5 May 2023 @ 3PM                                |
| 7                 | Event date end 5 May 2023 @ 5PM                                  |
| 8                 | Support contact Aliénor Vichum                                   |
| 9                 | Location Salle des fêtes de Mufflins                             |
| 10                | Attendees 200                                                    |
| 11                | Notes Assemblée générale des actionnaires (~200 personnes).      |

# Besoins et fonctionnalités

## Besoins généraux

| Exigence                                                        | Description                                                                                                                                                   |
|-----------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Identifiants pour chaque collaborateur                          | Chaque collaborateur doit avoir ses propres identifiants pour utiliser la plateforme.                                                                          |
| Association des collaborateurs à un rôle                        | Chaque collaborateur est associé à un rôle, dépendant de son département.                                                                                     |
| Stockage et mise à jour des informations                        | La plateforme doit permettre de stocker et de mettre à jour les informations concernant les clients, les contrats et les événements.                          |
| Accès en lecture seule pour tous les collaborateurs             | Tous les collaborateurs doivent avoir la capacité d'accéder à toutes les informations concernant les clients, les contrats et les événements en mode lecture seule. |

## Besoins individuels : équipe de gestion

| Fonctionnalité                                 | Description                                                                                                        |
|------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|
| Créer, mettre à jour et supprimer des collaborateurs | Permet de créer, mettre à jour et supprimer des collaborateurs dans le système CRM.                                 |
| Créer et modifier tous les contrats            | Autorise la création et la modification de tous les contrats dans le système.                                       |
| Filtrer l’affichage des événements             | Permet de filtrer l'affichage des événements, par exemple, afficher tous les événements sans « support » associé.   |
| Modifier des événements                        | Autorise la modification d'événements, y compris l'association d'un collaborateur support à l'événement.           |

## Besoins individuels : équipe commerciale

| Fonctionnalité                                     | Description                                                                                                                                                         |
|----------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Créer des clients                                  | Permet aux utilisateurs de créer des clients, qui seront automatiquement associés à eux.                                                                              |
| Mettre à jour les clients responsables             | Autorise les utilisateurs à mettre à jour les informations des clients dont ils sont responsables.                                                                   |
| Modifier/mettre à jour les contrats des clients    | Permet de modifier ou de mettre à jour les contrats des clients dont les utilisateurs sont responsables.                                                             |
| Filtrer l’affichage des contrats                   | Autorise le filtrage des contrats selon certains critères, comme ceux qui ne sont pas encore signés ou pas encore entièrement payés.                                 |
| Créer un événement pour un client avec contrat     | Permet de créer un événement pour un client qui a signé un contrat, offrant une gestion événementielle intégrée pour les clients sous contrat.                       |

## Besoins individuels : équipe support

| Fonctionnalité                              | Description                                                                                      |
|---------------------------------------------|--------------------------------------------------------------------------------------------------|
| Filtrer l'affichage des événements          | Permet de filtrer l'affichage des événements pour n'afficher que ceux attribués à l'utilisateur. |
| Mettre à jour les événements responsables   | Autorise les utilisateurs à mettre à jour les événements dont ils sont responsables.             |

## Représentation des parcours utilisateur dans l'application

```mermaid
graph TD
    A[Département Commercial] -->|Démarche et crée/mise à jour des profils clients| B[Plateforme]
    C[Département Gestion] -->|Crée un contrat et l'associe au client| B
    B -->|Contrat signé| D[Commercial crée l'événement dans la plateforme]
    E[Département Gestion] -->|Désigne un membre du Support| F[Département Support]
    F -->|Responsable de l'organisation et du déroulé de l'événement| G[Événement]
```



## Résumé du cahier des charges

- **Entreprise**: Epic Events, organisateur d'événements
- **Objectif**: Développer un logiciel CRM en Python 3.9+ pour la gestion des clients, contrats et événements.
- **Départements concernés**: Commercial, Support, Gestion
- **Sécurité et contraintes techniques**: Pas d'injections SQL, principe du moindre privilège, journalisation avec Sentry.
- **Livraison**: Dans un mois, en ligne de commande, avec une documentation d'implémentation.

### Données à gérer

- **Clients**: Nom, Email, Téléphone, etc.
- **Contrats**: ID unique, infos sur le client, montant, etc.
- **Événements**: ID, ID du contrat, nom du client, etc.

### Fonctionnalités

- **Tous les collaborateurs**: Accès en lecture seule à toutes les données
- **Équipe de gestion**: CRUD sur les collaborateurs, contrats et événements
- **Équipe commerciale**: Gestion des clients et contrats
- **Équipe support**: Filtrage et mise à jour des événements
- **Administration**: Gestion des employés

---

# Guide d'implémentation

## Architecture générale

- Modèle MVC (Modèle-Vue-Contrôleur) pour séparer les responsabilités
- Base de données POSTGRES SQL pour un prototype rapide (en gardant à l'esprit les contraintes de sécurité)

### Authentification

- Utilisation de jetons JWT pour authentifier les collaborateurs

### Département Commercial / SALES

- Interface en ligne de commande pour ajouter/mettre à jour les clients et contrats
- Filtres de recherche pour les contrats non signés, etc.

### Département Support / SUPPORT

- Interface pour filtrer et mettre à jour les événements qui leur sont attribués
- Notifications pour les changements d'état des événements

### Département Gestion / ACCOUNTING

- Interface admin pour la gestion des collaborateurs, contrats et événements
- Filtres pour afficher les événements sans support, etc.

### Département Administration / ADMIN

- Utilisé comme un rôle pour filtrer une permission spéciale d'accès au menu d'administration pour la gestion des employés.

### Sécurité

- Utilisation de requêtes paramétrées pour prévenir les injections SQL
- Implémentation du principe du moindre privilège via des rôles et permissions

### Journalisation

- Intégration de Sentry pour capturer les erreurs et exceptions

# Diagram ERD
```mermaid
erDiagram
    Client ||--o{ Contract : has
    Employee ||--o{ Contract : manages
    Employee ||--o{ Event : organizes
    Contract ||--o{ Event : results_in
    Client {
        int id
        string full_name
        string email
        string phone
        string company_name
        date first_contact
        date last_update
        int commercial_contact_id
    }
    Contract {
        int id
        int client_id
        int commercial_id
        float total_amount
        float amount_to_be_paid
        date creation_date
        string status
    }
    Employee {
        int id
        string full_name
        string email
        date creation_date
        string department
    }
    Event {
        int id
        int contract_id
        int support_contact_id
        date start_date
        date end_date
        string location
        int attendees
        string notes
    }

```
# La base de donnée

## 1. Installation de PostgreSQL et PgAdmin:

Les étapes d'installation impliquent la disponiiblité d'un server linux Fedora/RedHat/CentOS.

### Installation du server PSQL
- PostgreSQL:

``` Shell
sudo dnf update sudo dnf install postgresql-server postgresql-contrib
```

### Après l'installation, initialiser la base de données:

``` Shell
sudo postgresql-setup --initdb
```

### Puis démarrer et activer le service:

```shell
sudo systemctl start postgresql sudo systemctl enable postgresql
```

### PgAdmin:

```Shell
sudo dnf install pgadmin4
```

## 2. Créer une nouvelle base de données:

### SHELL : Se connecter à la base de données par défaut (postgres) avec l'utilisateur par défaut (postgres) :

``` Shell
 psql -U postgres -h localhost -d epic_events

```

### Créer une nouvelle base de données avec le nom : `epic_events`.

## 3. Créer un utilisateur pour l'application:

- Créer un nouvel utilisateur (ou "Role" dans le jargon PostgreSQL).
- Attribuer un nom et un mot de passe et assurer les droits suffisants sur la base de données epic_events.


## 4. Configurer les variables d'environnement:

- Les informations de connexion à la base de données dans des variables d'environnement pour des raisons de sécurité. Nous utilisons la librairie  `dot_env`

## 5. Créer un environnement virtuel Python:

### Dans le répertoire du projet, crée un environnement virtuel:


``` Python
python3 -m venv .venv
```
ou
``` Python
virtualenv .venv
```

### Activer l'environnement:

   ``` Shell
   source .venv/bin/activate
   ```

### Installer les dépendances comme `SQLAlchemy` et `Dot_env`:

#### Créer un fichier pour les variables d'environnement

1. **Crée un fichier `.env` dans le répertoire de ton projet**. Ce fichier contiendra tes variables d'environnement.


``` Shell
touch .env
```


### Ouvrir ce fichier avec un éditeur de texte** et ajouter les variables.

- Par exemple :

``` Shell
DATABASE_URL=postgresql://username:password@localhost/dbname SECRET_KEY=mysecretkey

DATABASE_URL=postgresql://user:Password@localhost/epic_events
EPICEVENTS_USER=user
EPICEVENTS_PW=Password
EPICEVENTS_SK=mySecretKey
```

Ici, `username` et `password` sont ceux définis lors de la création de l'utilisateur PostgreSQL, et `dbname` est le nom de la base de données créée précédememnt.

### Pour simplifier l'installation des dépendances nécessaires au projet

``` Shell
pip install -r requirements.txt
```

### Charger les variables d'environnement dans l'application

1. **Installer la librairie `python-dotenv`**: Cette librairie permet de charger les variables d'environnement depuis un fichier `.env` dans le projet.
```Shell
pip install python-dotenv
```

2. **Charger les variables dans le code Python**:

``` Python
from dotenv import load_dotenv import os  load_dotenv()  database_url = os.getenv("DATABASE_URL") secret_key = os.getenv("SECRET_KEY")
```

Ici, `load_dotenv()` lit le fichier `.env` et charge les variables pour les utiliser avec `os.getenv().

# Démonstration

Dans le cadre de ce projet, certains composants sont volontairement exclus de synchronisation avec GitHub comme le fichier .env pour illustrer une bonne pratique consistant à ne pas partager les informations sensibles sur un dépôt public.
La base de donnée est également exclue de la synchronisation avec GitHub pour des raisons de sécurité. Un backup est disponible sur demande généré avec la commande suivante: `pg_dump -U postgres -W -F c -d epic_events > backup_epicevents.backup
`


# FRONTEND

Conformément au cahier de charges, la partie cliente est entièrement réalisée en ligne de commande en utilisant la librairie RICH.

# BACKEND

Le backend est réalisé en Python 3.12 et utilise les librairies suivantes:

| Dépendance       | Version     |
|------------------|-------------|
| bcrypt           | 4.0.1       |
| certifi          | 2023.7.22   |
| cffi             | 1.16.0      |
| cryptography     | 41.0.5      |
| DateTime         | 5.2         |
| factory-boy      | 3.3.0       |
| Faker            | 19.13.0     |
| greenlet         | 3.0.1       |
| iniconfig        | 2.0.0       |
| Jinja2           | 3.1.2       |
| markdown-it-py   | 3.0.0       |
| MarkupSafe       | 2.1.3       |
| mdurl            | 0.1.2       |
| packaging        | 23.2        |
| pluggy           | 1.3.0       |
| psycopg2-binary  | 2.9.9       |
| pwinput          | 1.0.3       |
| pycparser        | 2.21        |
| Pygments         | 2.16.1      |
| PyJWT            | 2.8.0       |
| PyMySQL          | 1.1.0       |
| pytest           | 7.4.3       |
| pytest-html      | 4.1.1       |
| pytest-metadata  | 3.0.0       |
| python-dateutil  | 2.8.2       |
| python-dotenv    | 1.0.0       |
| pytz             | 2023.3.post1|
| rich             | 13.6.0      |
| sentry-sdk       | 1.34.0      |
| setuptools       | 68.2.2      |
| six              | 1.16.0      |
| SQLAlchemy       | 2.0.23      |
| typing_extensions| 4.8.0       |
| urllib3          | 2.0.7       |
| Werkzeug         | 3.0.1       |
| zope.interface   | 6.1         |


# Structure de dossiers

| Dossier/Fichier                   | Sous-Dossiers/Fichiers                                                                                     |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|
| `accesscontrol/`                  | `auth_decorators.py`, `database_session.py`, `env_variables.py`, `functionnalities.py`, `__init__.py`, `jwt_token.py`, `load_current_user.py`, `sec_sessions.py`, `test_jwt_token.py` |
| `conftest.py`                     |                                                                                                            |
| `controllers/`                    | `authentication_controller.py`, `clients.py`, `contracts.py`, `employees.py`, `events.py`, `__init__.py`, `main_controller.py`, `reports.py` |
| `factories/`                      | `clientFactory.py`, `contractFactory.py`, `employeeFactory.py`, `__init__.py`                              |
| `main.py`                         |                                                                                                            |
| `managers/`                       | `clients.py`, `contracts.py`, `employees.py`, `events.py`, `__init__.py`, `manager.py`                                                                  |
| `models/`                         | `clients.py`, `contracts.py`, `employees.py`, `events.py`, `__init__.py`, `user.py`                        |
| `README.md`                       |                                                                                                            |
| `requirements.txt`                |                                                            |
| `tests/`                          | `db/test_clients.py`, `db_create_tables.py`, `db_delete_tables.py`, `db_init.py`, `db_test_check_tables.py`, `db_test_connection.py`, `factories/`, `test_accounting_contract_Create.py`, `test_createEmployee.py`, `unit/settings_pytest.py`, `unit/test_create_customer.py`, `unit/test_createEmployee.py` |
| `utils/`                          | `database/clients_data.json`, `database/contracts_data.json`, `database/database.py`, `database/db_create_secret_key.py`, `database/db_init.py`, `database/employees_data.json`, `database/events_data_contact_id.json`, `database/events_data.json`, `database/login.py`, `database/logout.py`, `database/register.py`, `Fernet_cryptokey_gen.py`, `__init__.py`, `reset_password_user.py`, `token_storage.py` |
| `views/`                          | `client_view.py`, `contract_view.py`, `employee_view.py`, `event_view.py`, `__init__.py`, `login_view.py`, `logout_view.py`, `menu.py`, `report_view.py` |

# Références :
- [OpenClassrooms](https://openclassrooms.com/fr/paths/68-developpeur-dapplication-python)
- [PSQL](https://www.postgresql.org/docs/current/app-psql.html)
- [PgAdmin](https://www.pgadmin.org/docs/pgadmin4/latest/index.html)
- [VScode-postgresql](https://github.com/microsoft/vscode-postgresql)
- [Rich](https://rich.readthedocs.io/en/latest/)
- [SQLAlchemy](https://docs.sqlalchemy.org/en/14/)
- [Python-dotenv](https://pypi.org/project/python-dotenv/)
- [PyJWT](https://pyjwt.readthedocs.io/en/stable/)
- [Pytest](https://docs.pytest.org/en/6.2.x/)
- [Sentry](https://docs.sentry.io/platforms/python/)
- [Faker](https://faker.readthedocs.io/en/master/)
- [FactoryBoy](https://factoryboy.readthedocs.io/en/stable/)
- [DateTime](https://docs.python.org/3/library/datetime.html)
- [Bcrypt](https://pypi.org/project/bcrypt/)
- [Cryptography](https://cryptography.io/en/latest/)
- [Fedora - Installation et configuration PostgreSQL Server](https://doc.fedora-fr.org/wiki/Installation_et_configuration_de_PostgreSQL)