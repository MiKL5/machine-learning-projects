# 🏠 KNN — Prédiction de prix de logements Airbnb Parisiens<a href="https://github.com/MiKL5/machine-learning-projects"><img align="right" src="https://github.com/MiKL5/python/blob/main/assets/logo/Jupyter.svg" alt="Jupyter" height="64px"></a>
<div align="cetner">

![Python](https://img.shields.io/badge/Python-3.13-3776AB?style=plastic&logo=python&logoColor=white) ![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=plastic&logo=jupyter&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-1.x-013243?style=plastic&logo=numpy&logoColor=white) ![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?style=plastic&logo=pandas&logoColor=white) ![Machine Learning](https://img.shields.io/badge/ML-K--Nearest%20Neighbors-brightgreen?style=plastic&logo=scikit-learn&logoColor=white) ![Dataset](https://img.shields.io/badge/Dataset-Airbnb%20Paris-FF5A5F?style=plastic&logo=airbnb&logoColor=white)

</div>

> Implémentation pédagogique de l'algorithme **K-Nearest Neighbors (KNN)** appliqué à la prédiction de prix de logements Airbnb à Paris, en utilisant la distance euclidienne comme métrique de similarité.
---

## 📁 Structure du projet
```sh
├── knn_paris.ipynb                 # Notebook 1 — Introduction au KNN & distance euclidienne
├── knn_function.ipynb              # Notebook 2 — Fonction predict_price() & prédictions
├── airbnbParisPricing.ipynb        # Notebook principal
├── random_forest_airbnb.pkl        # Modèle Random Forest sauvegardé
├── random_forest_airbnb_meta.pkl   # Métadonnées du modèle
└── README.md
```

## 📊 Dataset

Le dataset `paris_airbnb.csv` contient des annonces de logements Airbnb situés à **Paris, Île-de-France**.

<details>
<summary>📋 Colonnes disponibles (19 features)</summary>

Colonne | Type | Description
---|---|---
`host_response_rate` | string | Taux de réponse de l'hôte
`host_acceptance_rate` | float | Taux d'acceptation
`host_listings_count` | float | Nombre de logements gérés par l'hôte
`latitude` | float | Latitude géographique
`longitude` | float | Longitude géographique
`city` | string | Ville (Paris)
`zipcode` | string | Code postal
`state` | string | Région (Île-de-France)
`accommodates` | int | Nombre de personnes pouvant être accueillies ⭐
`room_type` | string | Type de logement
`bedrooms` | float | Nombre de chambres
`bathrooms` | float | Nombre de salles de bain
`beds` | float | Nombre de lits
`price` | float | **Prix par nuit (cible)** 🎯
`cleaning_fee` | float | Frais de ménage
`security_deposit` | float | Dépôt de garantie
`minimum_nights` | int | Nombre de nuits minimum
`maximum_nights` | int | Nombre de nuits maximum
`number_of_reviews` | int | Nombre d'avis

</details>


## 🧠 Algorithme KNN

### Principe

L'algorithme des **K Plus Proches Voisins** (K-Nearest Neighbors) est une méthode d'apprentissage supervisé **non-paramétrique** basée sur la similarité locale. Pour prédire le prix d'un nouveau logement, on :

1. Calcule la **distance euclidienne** entre ce logement et tous les logements du dataset
2. Sélectionne les **k voisins les plus proches**
3. Retourne la **moyenne des prix** de ces voisins

### Distance euclidienne (univariée)

$$d = |x_{new} - x_i|$$

### Fonction de prédiction

```python
def predict_price(new_listing):
    temp_df = listings.copy()
    temp_df['distance'] = temp_df['accommodates'].apply(
        lambda x: np.abs(x - new_listing)
    )
    temp_df = temp_df.sort_values('distance')
    nearest_neighbors = temp_df.iloc[0:5]['price']
    predicted_price = nearest_neighbors.mean()
    return predicted_price
```


## 📈 Résultats

Capacité d'accueil | Prix prédit
:--:|:--:
1 personne  | **52,40 $**
2 personnes | **67,20 $**
4 personnes | **136,00 $**

## 🚀 Installation & Utilisation

### Prérequis

* Python ≥ 3.12
* Jupyter Notebook ou JupyterLab

### Installation des dépendances

```bash
pip install -r requirements.txt
```

### Lancer les notebooks

```bash
jupyter notebook knn_paris.ipynb
jupyter notebook knn_function.ipynb
jupyter notebook aribnbParisPricing.ipynb
```

## 📚 Concepts abordés

* 📐 Distance euclidienne comme métrique de similarité
* 🔍 Principe de la fenêtre de voisinage (k=5)
* 🐼 Manipulation de DataFrames avec `pandas` (`.copy()`, `.sort_values()`, `.iloc[]`)
* 🔢 Calcul vectorisé avec `numpy` (`np.abs`)
* 💰 Nettoyage de données monétaires (suppression de `$` et `,`)
* 🎲 Permutation aléatoire du dataset (`np.random.permutation`)
* ✂️ Séparation train/test pour éviter le surapprentissage
* ⚖️ Normalisation Min-Max des features
* 🔍 Optimisation d'hyperparamètre (k, n_estimators) par courbe du coude
* 📊 Métriques d'évaluation : MAE et RMSE
* 🔁 Validation croisée à 5 plis (CV-5)
* 🏆 Benchmarking multi-algorithmes
* 🌲 Random Forest et importance des features
* 💾 Sauvegarde de modèle avec `joblib`