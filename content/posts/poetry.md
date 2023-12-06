---
title: "Utilisation de Poetry pour la gestion des dépendances en Python"
date: 2023-04-01
draft: false
---

# Utilisation de Poetry pour la gestion des dépendances en Python 🐍

## Introduction 📚

Poetry, un outil de gestion de dépendances et de packaging pour Python. Il permet de déclarer les bibliothèques dont dépend un logiciel et de les installer dans un environnement virtuel.

## Installation 💻

### macOS & Linux 🍎🐧

```bash
curl -sSL https://install.python-poetry.org | python3 -
```

### Windows 💻

```powershell
(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicP) | python3 -
```

## Initialisation d'un nouveau projet 🌱

```bash
poetry new mon_projet
```

Ou, si vous avez déjà un projet existant :

```bash
cd mon_projet_existant/
poetry init
```

## Ajout de dépendances ➕

Pour ajouter une dépendance à votre projet :

```bash
poetry add nom_du_paquet
```

Pour les dépendances de développement :

```bash
poetry add --dev nom_du_paquet_dev
```

## Installation des dépendances ⬇️

```bash
poetry install
```

## Mise à jour des dépendances ⬆️

```bash
poetry update
```

## Gestion des environnements virtuels 🌐

Poetry crée automatiquement un environnement virtuel pour votre projet. Pour activer cet environnement :

### macOS & Linux 🍎🐧

```bash
source $(poetry env info --path)/bin/activate
```

### Windows 💻

```powershell
. $(poetry env info --path)/Scripts/Activate
```

## Conclusion 🎉

Poetry est un outil puissant et flexible pour gérer vos projets Python. Il simplifie la gestion des dépendances et le packaging, ce qui vous permet de vous concentrer sur le développement.
