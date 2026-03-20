# Machine Learning avec <a href="#"><img align="center" src="../../../assets/netflix.png" alt="netflix" height="36px"></a>etflix<a href="../../../"><img align="right" src="https://github.com/MiKL5/python/blob/main/assets/logo/Jupyter.svg" alt="Jupyter" height="64px"></a>
## 📌 Contexte
> Ce projet illustre la mise en place d’un **système de recommandation basé sur le contenu** en utilisant la similarité cosinus et la vectorisation **TF-IDF (Term Frequency – Inverse Document Frequency)**.  
Il exploite un dataset de films/séries (titres, genres, pays) afin de proposer aux utilisateurs des recommandations personnalisées.
## **🎯 objectif**
> Démontrer la maîtrise des techniques fondamentales de **NLP (Natural Language Processing)** et de **Machine Learning** appliquées à un cas concret.
---
## ⚙️ Fonctionnalités principales
- **Nettoyage et prétraitement** des données textuelles (genres, catégories).
- **Vectorisation TF-IDF** pour représenter les genres sous forme de vecteurs pondérés.
- **Calcul de la similarité cosinus** pour identifier la proximité entre films/séries.
- **Fonction de recommandation** retournant les 5 films les plus similaires à un titre donné.
- **Visualisation** sous forme de tableau interactif avec `matplotlib`.
---
## 🛠️ Stack technique
- **Langage** : Python 3.x  
- **Bibliothèques principales** :
  - `pandas` → manipulation des données  
  - `scikit-learn` → TF-IDF, calcul de similarité  
  - `matplotlib` → visualisation des recommandations  
## 🚀 Exemple d’utilisation
```python
# Exemple de recommandations
plot_recommendations("Dick Johnson Is Dead")

# Test rapide
get_recommendations("The Dark Knight")
```
🔎 Résultat attendu : un tableau affichant les **5 films les plus proches** du titre donné, avec **titre**, **genres** et **pays**.
## 📊 Résultats
- Génération d’un **système de recommandation simple, efficace et extensible**.
- Capacité à être intégré dans une application web (Flask, FastAPI) ou un moteur de recherche interne.
- Possibilité d’améliorer avec des approches hybrides (collaboratif + contenu) ou deep learning.
<!-- ## 🌍 Perspectives d’évolution
- Ajout de **pondération par popularité** (scores IMDB, vues Netflix, etc.).
- Intégration d’un **système de filtrage collaboratif** (collaborative filtering).
- Déploiement sous forme d’API (FastAPI, Flask).
- Création d’une interface interactive avec **Streamlit** ou **Dash**. -->