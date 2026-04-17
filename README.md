#Prédiction de la qualité du vin🍷  
 
📌 Description du projet
Ce projet vise à prédire la qualité du vin à partir de ses caractéristiques physico‑chimiques (acidité, pH, taux d’alcool, etc.).
L’objectif principal est de comparer plusieurs modèles de classification pour estimer la qualité du vin, d’abord sur 7 classes puis sur 3 classes de qualité, à partir de jeux de données issus du Wine Quality Dataset (UCI / Kaggle)

📂 Jeux de données
Deux jeux de données principaux ont été utilisés :

Jeu de données initial

Données classiques de qualité du vin rouge (winequality-red.csv) avec une échelle de qualité de 3 à 8 (7 classes).

Les classes sont fortement déséquilibrées (beaucoup de vins “moyens”, très peu de très mauvais / excellents).

Jeu de données équilibré Kaggle

Dataset : 
Wine Quality dataset – Balanced Classification (taweilo)
.

3 catégories de qualité déjà équilibrées, ce qui facilite l’apprentissage des modèles de classification.
🎯 Problématique et démarche
Étape 1 – 7 classes de qualité
Utilisation de la qualité brute (7 niveaux) comme variable cible.

Modèles testés :

Random Forest

AdaBoost

Gradient Boosting

KNN

XGBoost

Constat :

Forte confusion entre classes voisines (par exemple 5 vs 6, 6 vs 7).

Performances très faibles sur la majorité des classes, même après recherche d’hyperparamètres.

Le modèle Random Forest illustre bien cette confusion : la matrice de confusion montre des prédictions très concentrées sur quelques classes centrales.

Étape 2 – Regroupement en 3 classes
Pour obtenir un problème plus robuste et exploitable, la qualité a été regroupée en 3 catégories :

0 – Mauvais vin

1 – Médiocre

2 – Bon vin

Les modèles de classification suivants ont été entraînés sur ce nouveau problème à 3 classes :

Random Forest

Gradient Boosting

KNN

XGBoost
📈 Évolution des performances
Premier essai : jeu de données non équilibré
Premier notebook : Wine_quality_ML_Final.ipynb

Jeu de données initial (non équilibré) avec 3 classes créées à partir de la qualité brute.

Résultats globalement faibles (scores autour de < 40% selon les métriques), ce qui montre que le volume et l’équilibre des données n’étaient pas suffisants.

Deuxième essai : ajout du dataset équilibré Kaggle
Deuxième notebook : Wine_quality_ML_moredata.ipynb

Fusion / utilisation du dataset équilibré Kaggle à 3 classes.

Les performances des modèles de classification montent autour de ~60% (selon la métrique choisie : accuracy, F1_macro, precision_macro), ce qui est nettement plus cohérent compte tenu de la difficulté du problème et du bruit dans les labels.
