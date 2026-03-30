# Détection de spam dans les messages texte avec apprentissage automatique<a href="https://github.com/MiKL5/machine-learning-projects"><img align="right" src="https://github.com/MiKL5/python/blob/main/assets/logo/Jupyter.svg" alt="Jupyter" height="64px"></a>
<div align="center">

![Python](https://img.shields.io/badge/python-3.13-blue?style=flat&logo=python&logoColor=FFD43B)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-Classification-FF9900?style=flat&logo=scikit-learn&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-Data_Visualization-556F9F?style=flat&logo=python&logoColor=white)

</div><hr>

Ce projet vise à détecter automatiquement les messages spam (indésirables) au sein d'un ensemble de messages texte en utilisant des techniques de machine learning.  
Le dataset fourni contient des messages classés en catégories `ham` (non spam) et `spam`, ce qui permet un apprentissage supervisé.
---
## **Le dataset**
* Nombre d'exemples : 5572 messages  
* Colonnes : `Category` (label), `Message` (texte)  
* Répartition : 4825 `ham`, 747 `spam`
## **Prétraitement et équilibrage des données**
* Aucun valeur manquante présente.
* Sous-échantillonnage de la classe majoritaire (`ham`) pour équilibrer avec la classe minoritaire (`spam`), évitant ainsi le déséquilibre des classes.
## **Transformer les données**
* Encodage des catégories `ham` → 0 et `spam` → 1 avec `LabelEncoder`.
* Mélange des données équilibrées aléatoirement.  
* Séparation en features (`Message`) et labels (`Category`).  
* Découpage en données d'entraînement (75%) et de test (25%).
## **Vectoriser le texte**
* Utilisation de `TfidfVectorizer` de scikit-learn pour transformer les messages en représentations numériques pondérées par la fréquence et l'importance des mots.
* Paramètres utilisés : suppression des mots courants en anglais (`stop_words='english'`), gestion de la casse (`lowercase=True`).
## **Modéliser**
* Modèle utilisé : **Régression Logistique**.
* Entraînement sur les données vectorisées d'entraînement.  
* Prédiction sur données test.
## **Les résultats**
- Précision atteinte : environ **94.9 %** pour la détection correcte des messages spam/ham sur le jeu de test.  
- Ce modèle simple offre une performance robuste pour un problème classique de classification binaire sur données textuelles.
## **Conclusion**
Ce workflow montre comment un modèle de machine learning classique, couplé à une bonne préparation et vectorisation des données textuelles, peut efficacement résoudre un problème de classification textuelle sensible comme la détection de spam.  
Le sous-échantillonnage permet de limiter les biais liés aux classes déséquilibrées et la représentation TF-IDF facilite la prise en compte de la pertinence des mots.
<!-- ## Suggestions d'amélioration
* Tester d'autres modèles comme SVM, Random Forest ou XGBoost.  
* Explorer des techniques avancées de traitement du langage naturel comme les embeddings ou réseaux de neurones.  
* Évaluer sur d'autres métriques (précision, rappel, F1-score) et sur cross-validation. -->