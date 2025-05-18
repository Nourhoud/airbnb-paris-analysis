# Analyse des données Airbnb à Paris

## Présentation du projet

Ce projet a été réalisé dans le but de développer une analyse complète des annonces Airbnb de la ville de Paris à partir de données publiques.
L’objectif est de simuler un cas réel d’analyse exploratoire permettant d’aider une entreprise à :
- comprendre les dynamiques du marché locatif courte durée
- identifier les segments les plus rentables
- explorer les tendances par quartier

Le projet suit les étapes clés d’un pipeline d’analyse de données et du nettoyage à la visualisation

---

## Objectifs de l’analyse

- Étudier la répartition des prix des logements par type et par quartier
- Identifier les quartiers avec la plus forte densité d'annonces
- Repérer les types de logements les plus courants
- Comprendre la relation entre disponibilité, activité (nombre d'avis) et prix
- Fournir des visualisations claires et actionnables

---

## Données utilisées

- **Source** : Inside Airbnb ([http://insideairbnb.com/get-the-data.html](http://insideairbnb.com/get-the-data.html))
- **Fichier** : `listings.csv.gz`
- **Taille initiale** : ~80 000 lignes, 79 colonnes

Les données comprennent des informations sur chaque logement : identifiant, type, quartier, prix, nombre d’avis, disponibilité annuelle, etc...

---

## Méthodologie

### 1. Chargement et compréhension initiale

- Lecture du fichier compressé avec Pandas
- Inspection des types de données, dimensions, premières lignes

### 2. Sélection des variables pertinentes

Conservation uniquement des colonnes essentielles à l’analyse métier :
- `price`, `room_type`, `neighbourhood_cleansed`, `minimum_nights`, `number_of_reviews`, `reviews_per_month`, `availability_365`, `last_review`, etc.

### 3. Nettoyage des données

- Suppression des symboles monétaires et conversion du champ `price` en float
- Suppression des lignes avec valeurs manquantes sur `price` et `reviews_per_month`
- Réindexation du dataset
- Contrôle qualité du jeu final : plus de 48 000 lignes nettes

### 4. Analyse exploratoire

Analyse statistique et visuelle :
- Répartition des types de logements
- Distribution des prix (avec filtrage < 500 € pour éviter les outliers extrêmes)
- Prix moyen par type de logement (barplot)
- Boxplot par quartier (top 10 quartiers en nombre d'annonces)
- Corrélations possibles entre activité (`number_of_reviews`) et prix

---

## Résultats clés

- Les **appartements entiers** dominent largement (plus de 90 % des annonces)
- Le **prix médian** est d’environ 100 € par nuit
- La majorité des logements sont dans une fourchette de **60 € à 150 €**
- Certains logements de luxe montent à plus de **10 000 €**
- Les quartiers comme **Popincourt**, **Buttes-Montmartre** et **Vaugirard** concentrent le plus d’annonces
- Les hôtels sont très peu présents mais nettement plus chers

---

## Visualisations fournies

- Histogramme de la distribution des prix (< 500 €)
- Barplot : prix moyen par type de logement
- Boxplot : distribution des prix dans les 10 quartiers les plus actifs

Les visualisations sont commentées et intégrées dans le notebook `airbnb_paris_analysis.ipynb`.
