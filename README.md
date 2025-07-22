# Analyse des ventes de votre entreprise

## Table des matières

- [Description du projet](#description-du-projet)  
- [Structure du projet](#structure-du-projet)  
- [Jeu de données](#jeu-de-données)  
- [Outils et bibliothèques](#outils-et-bibliothèques)  
- [Nettoyage et préparation des données](#nettoyage-et-préparation-des-données)  
- [Méthodologie d’analyse](#méthodologie-danalyse)  
- [Analyse univariée](#analyse-univariée)  
- [Analyse bivariée et multivariée](#analyse-bivariée-et-multivariée)  
- [Corrélations](#corrélations)  
- [Résultats clés](#résultats-clés)  
- [Recommandations](#recommandations)

## Description du projet

Ce projet a été réalisé dans le cadre du parcours **Data Analyst** chez OpenClassrooms.  
L’objectif est de mener une **analyse exploratoire** des ventes de la librairie fictive *Rester Livres*, afin de mieux comprendre les comportements d’achat des clients, la performance des produits et d’éventuelles corrélations entre variables.

## Structure du projet
**data/**  Fichiers CSV d’entrée
- `transactions.csv`
- `clients.csv`
- `produits.csv`
  
**notebooks/** 
- `P4_01_scriptdonnees.py` # Script de nettoyage des données
- `P4_02_scriptanalyse.py` # Script d’analyse et de visualisation
  
**visualizations/**

Graphiques issus de l’analyse (histogrammes, boxplots, etc.)

**présentation/**  
- `presentation.pptx` : Fichier PowerPoint utilisé lors de la soutenance pour présenter les objectifs, la méthodologie et les résultats.

## Jeu de données

- **transactions.csv** : Détail des ventes (date, identifiant client, produit, prix)
- **clients.csv** : Informations sur les clients (sexe, date de naissance, etc.)
- **produits.csv** : Informations sur les produits (catégorie, prix)

## Outils et bibliothèques

- Python 3
- Pandas
- NumPy
- Matplotlib / Seaborn
- Jupyter Notebook 
- SciPy (pour les statistiques)
- Scikit-learn 

## Nettoyage et préparation des données

- **Valeurs manquantes** :
  - Produits ou clients présents dans certaines tables mais absents d’autres
  - 21 clients n’ont réalisé aucun achat
  - 22 produits n’ont jamais été vendus

- **Valeurs aberrantes** :
  - Prix négatifs
  - Présence de clients tests (`ct_0`, `ct_1`) et produit test (`T_0`) supprimés
  - Vérification de la cohérence des dates

- **Formatage** :
  - Conversion des dates
  - Fusion des bases pour croiser les informations

## Méthodologie d’analyse

1. Analyse univariée : comprendre les distributions de variables
2. Analyse bivariée : croisement entre 2 variables
3. Corrélations : rechercher des relations significatives entre variables
4. Visualisations : histogrammes, boxplots, séries temporelles, courbe de Lorenz, etc.

## Analyse univariée

- Âge des clients : majorité nés entre 1975 et 1982
- Répartition des sexes : équilibre hommes/femmes
- Produits les plus vendus : appartiennent à la catégorie 0
- Panier moyen : prix moyen réparti de manière relativement homogène
- Ventes dans le temps : chute en octobre, reprise en décembre

## Analyse bivariée et multivariée

- Les hommes achètent davantage de produits de la catégorie 0
- Les clients entre 40 et 50 ans achètent plus de livres que les autres groupes d’âge
- Les clients de plus de 30 ans n’achètent pas les produits de la catégorie 2
- Plus le panier est grand, plus l’âge diminue (corrélation négative)

## Corrélations

- **Sexe vs catégorie de produits** : pas de corrélation significative
- **Âge vs montant total des achats** : corrélation négative modérée
- **Âge vs fréquence d’achat** : corrélation négative modérée
- **Âge vs panier moyen** : forte corrélation négative
- **Catégorie vs âge (quantitatif / qualitatif)** : faible corrélation détectée

## Résultats clés

- Les produits les moins chers sont les plus vendus
- Les produits les plus vendus sont ceux de la catégorie 0
- Le chiffre d’affaires chute en octobre, notamment pour la catégorie 1
- Le prix moyen du panier est stable selon les profils clients
- Pas de différence notable entre hommes et femmes en matière de catégories achetées
  
## Recommandations

- Promouvoir davantage les produits de la catégorie 2, peu vendus
- Surveiller le chiffre d’affaires des produits de la catégorie 1, notamment en automne
- Cibler les clients de 40 à 50 ans, population la plus active
- Maintenir des prix attractifs pour maximiser les ventes

