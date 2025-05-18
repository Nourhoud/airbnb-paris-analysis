# Analyse Airbnb Paris 🏙️

Ce projet analyse les annonces Airbnb à Paris pour comprendre la distribution des prix, la disponibilité et les types de logements.

## 📂 Données
Données issues du site [Inside Airbnb](http://insideairbnb.com/get-the-data.html)

- Dataset : `listings.csv.gz` (Paris)

## 🧼 Prétraitement
- Suppression des colonnes inutiles
- Nettoyage de la colonne `price` (format string → float)
- Suppression des lignes sans prix ou sans reviews

## 📊 Analyses réalisées
- Distribution des prix (logements < 500€)
- Moyenne des prix par type de logement
- Quartiers les plus représentés
- Boxplot des prix par quartier (top 10)

## 📎 Outils
- Python
- Pandas, Seaborn, Matplotlib
- VS Code + Jupyter

## 📈 Résultat principal
La majorité des logements coûtent entre 60€ et 150€, avec des pics de prix très élevés dans certains quartiers rares.

## 🔗 Auteur
Réalisé par [Ton prénom Nom], étudiante à Polytech Lille
