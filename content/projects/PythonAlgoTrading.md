---
title: "Résolvez des problèmes en utilisant des algorithmes en Python"
date: 2023-03-01
tags: ["python", "django", "BD", "backend", "frontend", "HTML", "CSS", "Bootstrap", "JavaScript","Git", "GitHub"]
draft: false
---

<div align="center">
  <a href="" target="_blank" rel="noreferrer">
    <img src="https://www.python.org/static/community_logos/python-logo-master-v3-TM.png">
  </a>
</div>


<h3 align="center">

## Vous trouverez ici le projet complet [GitHub Repository](https://github.com/Mickael-Salmon/OCP7) 👋

</h3>

<h2 align="center">

Résolvez des problèmes en utilisant des algorithmes en Python 💻 !

</h2>

> Scénario
##

Vous venez de rejoindre **AlgoInvest&Trade**, une société financière spécialisée dans l'investissement. La société cherche à optimiser ses stratégies d'investissement à l'aide d'algorithmes, afin de dégager davantage de bénéfices pour ses clients.

<div align="center">
  <a href="" target="_blank" rel="noreferrer">
    <img src="https://user.oc-static.com/upload/2020/09/18/1600429119334_P6.png">
  </a>
</div>


Vous avez passé vos premiers jours à rencontrer votre petite équipe de six personnes. Votre responsable technique, Robin, a expliqué que même si tous les membres de l'équipe connaissent les termes techniques, ils sont en revanche tous issus de l'économie et de la finance, plutôt que de l'informatique. Comme vous êtes un des seuls développeurs, votre rôle sera principalement de traduire leurs besoins commerciaux en solutions techniques.

</br>

- 💬 Objectif : concevoir des algorithmes qui vont maximiser le profit réalisé par nos clients après deux ans d'investissement. L' algorithme doit suggérer une liste des actions les plus rentables à acheter pour maximiser le profit d'un client au bout de deux ans.
-  le programme essaie toutes les différentes combinaisons d'actions qui correspondent à nos contraintes, et choisit le meilleur résultat. 
- Le programme doit donc lire un fichier contenant des informations sur les actions, explorer toutes les combinaisons possibles et afficher le meilleur investissement.

> Contraintes  :
##

-   Chaque action ne peut être achetée qu'une seule fois.

-   Ne pas acheter une fraction d'action.

-   Dépenser au maximum 500 euros par client.

##

Partie 1: Concevoir un premier algorithme
-   développer une solution de force brute ("bruteforce.py").

##

Partie 2: Optimisation d'algorithme
-    Le programme Python optimisé, qui lit un fichier contenant des informations sur les actions, et fournit la meilleure stratégie d'investissement.
-   Un jeu de diapositives contenant les éléments suivants : 
-   une analyse de votre algorithme de force brute ; 
-   un diagramme, un organigramme ou un pseudocode décrivant le processus de réflexion qui sous-tend la solution optimisée ;
-   l'algorithme choisi pour la version optimisée, et les limites de l'algorithme (cas limites) ; 
-   une comparaison de l'efficacité et des performances de l'algorithme de force brute par rapport à l'algorithme optimisé en utilisant la notation Big-O, la complexité temporelle et l'analyse de la mémoire.

##

Partie 3: backtesting et optimisation
-   Préparer un jeu de diapositives contenant une comparaison côte à côte entre les résultats de votre algorithme et les choix de Sienna 
- Créer un rapport d'exploration de l'ensemble des données. Présentation.

##

> Livrables attendus 🔭
##

1.  Un **fichier Python `bruteforce.py`** avec la solution de force brute. 
2.  Un **fichier Python `optimized.py`** avec la version optimisée de l'algorithme.
3.  Un **jeu de diapositives** au format PDF expliquant ce qui suit (20 diapositives maximum) :
    -   la solution optimisée, y compris :
        -   l'analyse de l'algorithme de force brute,
        -   un diagramme/agenda/pseudocode,
        -   l'algorithme choisi et ses limites,
        -   l'analyse des performances et de l'efficacité de vos algorithmes ;
    -   une comparaison côte à côte entre la sortie de votre algorithme et les choix de Sienna, via un rapport d'exploration de l'ensemble des données.

</br>

> Structure de dossiers du projet
##

```
├── Partie 1
│   ├── bruteforce.py
├── Partie 2
│   ├── optimised.py
└── Partie 3
    ├── Optimized2.py
    ├── Rapport et présentation
    ├── Datasets en CSV pour backtesting

```


<h2> Installation et démarrage du projet</h2>
<h3>Windows  </h3>

Depuis un terminal , se déplacer dans le dossier applicatif souhaité :

<h3>Récupération du projet</h3>

```
git clone https://github.com/Mickael-Salmon/OCP7/
```

<h3>Activer l'environnement virtuel </h3>

```
cd OCP7
```
```
python -m venv .env
```
$ ~env\scripts\activate

<h3>Installer les paquets requis </h3>

```
pip install -r requirements.txt
```

<h3>Lancer le programme</h3>

```
python main.py
```

<h2>MacOS et Linux : </h2>

Depuis un terminal, se déplacer dans dossier souhaité.

<h3>Récupération du projet</h3>

```
git clone https://github.com/Mickael-SalmonSa/OCP7/
```

<h3>Activer l'environnement virtuel </h3>

```
cd OCP7
```
```
python3 -m venv venvOCP7
```
```
source env/bin/activate
```

<h3>Installer les paquets requis </h3>

```
pip install -r requirements.txt
```

<h3>Lancer le programme </h3>

```
python3 bruteforce.py
```
```
python3 optimized.py
```
```
python3 optimized2.py
```
  - choisir dataset1 ou dataset2
  - les résultats s'affichent à l'écran
