---
title: "Gestion de ses dotfiles avec Chezmoi"
date: 2023-01-01
tags: ["dotfiles", "chezmoi", "git", "github", "linux"]
draft: false
---

# Gestion des Dotfiles avec Chezmoi 🏠

## Prérequis 📋

-   Avoir `git` installé sur votre machine. 🖥️
-   Avoir un compte GitHub. 🐙

## Installation de chezmoi 📥

### Sur Linux 🐧

Ouvrez un terminal et exécutez la commande suivante :

``` bash
sh -c "$(curl -fsLS git.io/chezmoi)"

```

### Sur macOS 🍏

Si vous utilisez Homebrew, vous pouvez simplement faire :

``` bash
brew install chezmoi

```

## Initialisation de chezmoi 🛠️

Après l'installation, initialisez chezmoi avec la commande suivante :

``` bash
chezmoi init

```

Cette commande créera un répertoire `~/.local/share/chezmoi` où tous vos dotfiles seront stockés.

## Script pour ajouter des dotfiles à chezmoi 📜

Le script suivant ajoute une liste prédéfinie de dotfiles à chezmoi :

``` bash
#!/bin/bash

# Function to safely add a file to chezmoi
add_to_chezmoi() {
  if [ -f "$1" ] || [ -d "$1" ]; then
    chezmoi add "$1"
  else
    echo "Skipping $1 as it does not exist."
  fi
}

# Fish shell
add_to_chezmoi "$HOME/.config/fish/config.fish"
add_to_chezmoi "$HOME/.config/fish/fish_variables"
add_to_chezmoi "$HOME/.config/fish/starship.fish"

# Visual Studio Code
add_to_chezmoi "$HOME/.config/Code/User/settings.json"
add_to_chezmoi "$HOME/.config/Code/User/keybindings.json"
add_to_chezmoi "$HOME/.config/Code/User/snippets/"

# Starship
add_to_chezmoi "$HOME/.config/starship.toml"

# Neovim
add_to_chezmoi "$HOME/.config/nvim/init.vim"

# GitHub CLI
add_to_chezmoi "$HOME/.config/gh/config.yml"

# Neofetch
add_to_chezmoi "$HOME/.config/neofetch/config.conf"

# Ranger
add_to_chezmoi "$HOME/.config/ranger/rc.conf"

# Other commonly used dotfiles
add_to_chezmoi "$HOME/.bashrc"
add_to_chezmoi "$HOME/.zshrc"
add_to_chezmoi "$HOME/.gitconfig"
add_to_chezmoi "$HOME/.vimrc"
add_to_chezmoi "$HOME/.tmux.conf"
add_to_chezmoi "$HOME/.ssh/config"
add_to_chezmoi "$HOME/.wgetrc"
add_to_chezmoi "$HOME/.curlrc"

# Python-specific files
add_to_chezmoi "$HOME/.pylintrc"
add_to_chezmoi "$HOME/.flake8"

echo "Done adding files to chezmoi."

```

## Création d'un dépôt GitHub 🌐

1.  Allez sur GitHub et créez un nouveau dépôt. Nommez-le comme vous le souhaitez, par exemple `dotfiles`.
2.  Gardez ce dépôt vide pour l'instant.

## Pousser les dotfiles sur GitHub 🚀

Maintenant que vous avez un dépôt, vous pouvez configurer chezmoi pour pousser vos dotfiles sur ce dépôt.

1.  **Aller dans le répertoire de chezmoi** :

    ``` bash
    cd ~/.local/share/chezmoi

    ```

2.  **Initialiser un dépôt git** :

    ``` bash
    git init

    ```

3.  **Ajouter le dépôt GitHub comme `origin`** :

    ``` bash
    git remote add origin [URL de votre dépôt]

    ```

4.  **Faire un commit initial** :

    ``` bash
    git add .
    git commit -m "Initial commit"

    ```

5.  **Pousser sur GitHub** :

    ``` bash
    git push -u origin master

    ```


## Restaurer les dotfiles sur une nouvelle machine 🔄

Si vous souhaitez récupérer vos dotfiles sur une nouvelle machine, c'est simple. Installez `chezmoi` et exécutez :

``` bash
chezmoi init --apply [Votre nom d'utilisateur GitHub]

```