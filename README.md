# TP Comptage de Mots — Python & Hadoop MapReduce

Comparaison de différentes approches pour le comptage de mots dans un fichier texte, réalisée dans le cadre d'un travail pratique sur le traitement de données (M2, Bases de Données).

## Objectif

Implémenter et étudier trois méthodes de comptage de mots :

- **Python séquentiel** : comptage des occurrences à l'aide d'un dictionnaire.
- **Pseudo-MapReduce** : simulation des étapes Map, Shuffle et Reduce en Python.
- **Hadoop MapReduce** : utilisation d'Apache Hadoop pour effectuer le traitement des données.

Le projet permet de découvrir le paradigme MapReduce et d'étudier les différences entre un traitement classique et une approche conçue pour le traitement distribué.

## Technologies

- Python 3.10
- Jupyter Notebook
- Pandas
- Matplotlib
- Apache Hadoop
- Java
- Ubuntu Linux

## Structure du projet

```text
TP_Comptage_Mots/
├── README.md
├── .gitignore
├── mots.txt
└── TP_Comptage_Mots.ipynb
```

- `mots.txt` : fichier texte utilisé comme jeu de données initial (un mot par ligne, avec répétitions).
- `TP_Comptage_Mots.ipynb` : notebook contenant les explications, les implémentations, les tests et les expériences.
- `.gitignore` : fichiers et dossiers exclus du suivi Git (environnement virtuel, fichiers de test générés, checkpoints Jupyter).

Le dossier `fichiers_test/`, utilisé pour les mesures de performance, est généré automatiquement par le notebook et n'est pas versionné.

## Installation

### Prérequis

- Python 3
- pip
- Git
- Jupyter Notebook

Java et Apache Hadoop sont nécessaires pour exécuter la partie Hadoop.

### 1. Cloner le dépôt

```bash
git clone https://github.com/salahsahnoun/TP_Comptage_Mots.git
cd TP_Comptage_Mots
```

### 2. Créer un environnement virtuel

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Installer les dépendances

```bash
python -m pip install --upgrade pip
python -m pip install jupyter pandas matplotlib
```

### 4. Lancer le notebook

```bash
jupyter notebook
```

Ouvrir ensuite le fichier `TP_Comptage_Mots.ipynb` et exécuter les cellules dans l'ordre pour générer les données, lancer les implémentations et effectuer les expériences.

## Méthodes étudiées

### Python séquentiel

Comptage des occurrences de chaque mot à l'aide d'un dictionnaire Python.

### Pseudo-MapReduce

Simulation des trois étapes principales :

1. **Map** : transformation des mots en paires `(mot, 1)`.
2. **Shuffle** : regroupement des valeurs par mot.
3. **Reduce** : addition des occurrences.

### Hadoop MapReduce

Exécution du comptage de mots avec le modèle MapReduce sur Apache Hadoop.

## Expérimentation

Le notebook génère plusieurs fichiers de tailles différentes (de 20 à 100 000 lignes) par duplication du jeu de données initial, mesure les temps d'exécution des méthodes et compare leurs résultats.

Le protocole expérimental, les mesures et leur interprétation sont présentés dans le notebook.

## Auteur

Projet académique consacré au comptage de mots et à l'étude du paradigme MapReduce.
