---
title: "Développez une application Web en utilisant Django"
date: 2023-09-01
tags: ["python", "django", "BD", "backend", "frontend", "HTML", "CSS", "Bootstrap", "JavaScript","Git", "GitHub"]
draft: false
---

<div align="center">

![Python Logo](https://www.python.org/static/community_logos/python-logo-master-v3-TM.png)

## Vous trouverez ici le Projet complet : [GitHub Repository](https://github.com/Mickael-Salmon/OCP9/) 👋

## Développez une application Web en utilisant Django 💻 !

![Project Image](https://user.oc-static.com/upload/2020/09/18/16004297044411_P7.png)

</div>

---

### Scénario

LITREVIEW a pour objectif de commercialiser un produit permettant à une communauté d'utilisateurs de consulter ou de solliciter une critique de livres à la demande.

---

### Objectif

- Mettre en place une application web pour un MVP (Minimum Viable Product).

---

### Cahier des charges

#### Summary

Signup and login functionality are a must in terms of what you need for this MVP. When a user logs into the system, their feed is the first page they will see. There they can see the tickets and reviews of all users they follow. They should also see their own tickets and reviews, as well as any reviews in response to their own tickets - even if they do not follow the reviewer. (The logic around combining querysets of different model types can be complicated. Check the appendix at the end of this specification for some guidance on how to do this.)
##
You can think of a ticket as a request for a review from a user. They post their ticket requesting a review for a book or literature article. Users who follow them can then submit their reviews in response to the ticket. Users should also be able to post reviews for books and articles that do not have a ticket yet.
##
Users will be able to follow other users and should also have the option to unfollow them. As this is just an MVP, keep this functionality fairly simple. You won’t need a search functionality or a Discover feed for new users. Keep it to a simple box where you enter the username of the user you wish to follow. You should also have a page that lists all the users the logged-in user follows with the option to unfollow.
##
You will also need another page from which users can review their own submissions. They should be able to see their posts and edit and delete them from this page.
##
Remember, this is an MVP, so try not to get too caught up on styling. Focus more on a clean and minimal UI. However, you  should ensure things like date formats, styling, etc. are consistent across the site. Follow the layout of the wireframes provided, but don’t be afraid to add some personal touches if you wish, remember, clean and minimal.

#### A User Will Need To Do :

- [x] Log in and sign up
- [x] The site should not be accessible to a non-logged-in user
- [x] View a feed containing the latest tickets and reviews from users that they follow, ordered by time with the latest first
- [x] Create new tickets requesting a review on a book/article
- [x] Create reviews as a response to tickets
- [x] Create reviews not in response to a ticket. As part of a one-step process, the user will create a ticket and then a review responding to their own ticket
- [x] Be able to view, edit, and delete their own tickets and reviews
- [x] Follow other users by entering their username
- [x] View who they follow and unfollow whoever they want

#### A Developer Will Need To Do :

- [x] Create a local environment using venv
- [x] Have a UI matching those of the wireframes
- [x] Use server-side rendering to display information
- [x] Use the Django framework
- [x] Use SQLite as a local development DB
- [x] Have a database design that matches the database schema
- [x] Have syntax that meets PEP8 guidelines

---

### Livrables

- Un ensemble d'instructions détaillant la configuration de l’environnement et le fonctionnement de l'application.
- L'application, qui répond aux exigences énoncées dans le cahier des charges.
- Une interface utilisateur correspondant aux wireframes.

---

### Installation et démarrage du projet

#### Récupération du projet

```bash
$ git clone https://github.com/Mickael-Salmon/OCP9/
```
#### Lancer le server
```bash
$ python manage.py runserver
```

#### Accéder à l'application

Depuis un navigateur : `127.0.0.1:8000`

#### Utilisateurs de test

**Admin**

-   Admin : ocadmin1
-   Password : PasswordAdmin123

**Utilisateurs**

Le mot de passe est toujours `Test.123!`

-   John
-   Jane
-   Joshua
-   Alfred
-   Emilia
-   Rebecca
-   Tiffa
