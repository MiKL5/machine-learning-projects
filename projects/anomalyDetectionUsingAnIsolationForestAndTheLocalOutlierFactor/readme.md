# **Détection d'anomalies 👉 Isolation Forest & Local Outlier Factor (LOF)**<a href="../../"><img align="right" src="https://github.com/MiKL5/python/blob/main/assets/logo/Jupyter.svg" alt="Jupyter" height="64px"></a>
<div align="center">

![Python](https://img.shields.io/badge/Python-3.13-blue?style=flat&logo=python&logoColor=FFD43B)
![scikit-learn](https://img.shields.io/badge/scikit--learn-AnomalyDetection-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Plotting-11557C?style=flat&logo=matplotlib&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Arr_processing-013243?logo=numpy)
<!-- ![MIT License](https://img.shields.io/badge/License-MIT-blue.svg) -->

</div><hr>

<h3>Ce projet illustre et compare deux méthodes d’<b>apprentissage non supervisé pour la détection d’anomalies</b> :
<ul>
    <li> <b>Isolation Forest</b> (Forêt d’isolement)
    <li> <b>Local Outlier Factor (LOF)</b>
</ul>
Les deux algorithmes sont testés sur des données numériques bidimensionnelles générées aléatoirement, avec visualisation comparative des outliers détectés.<h3><hr>

## **La méthodologie**
### **1️⃣ Générer et visualiser des données**
* Création d’un nuage de points 2D avec NumPy : le jeu de données comporte principalement des inliers (points normaux), avec éventuellement quelques outliers.
* Visualisation initiale par scatter plot Matplotlib.
### **2️⃣ Détecter les anomalies**
#### **Isolation Forest**
* Entraînement du modèle sur les données.
* Prédiction des inliers (1) vs outliers (-1).
* Paramètre : `contamination=0.001` (proportion attendue d’anomalies).
* Affichage des résultats par la couleur : points aberrants en rouge, points normaux en bleu.
#### **Local Outlier Factor (LOF)**
* Utilisation avec 20 voisins (`n_neighbors=20`) et même taux de contamination.
*Prédiction et visualisation des outliers sur un second graphique, pour comparer à l’Isolation Forest.
## Notes
* Les algorithmes non supervisés comme ceux-ci sont essentiels en détection de fraude, nettoyage de données, cybersécurité…
* L’expérience avec différents jeux, dimensions, et taux de `contamination` est recommandée pour bien comprendre leurs subtilités.