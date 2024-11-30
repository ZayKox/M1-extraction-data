
# Détection de Fraudes sur les Cartes Bancaires

## Objectif du Projet
Le projet vise à développer un modèle capable de détecter les transactions frauduleuses à partir d'un dataset contenant des informations de transactions par carte bancaire. L'objectif principal est d'identifier les transactions frauduleuses tout en minimisant les faux positifs.

---

## Étapes du Projet

### 1. Chargement et Exploration des Données
- **Données utilisées** : Le dataset contient des caractéristiques anonymisées (`V1` à `V28`), ainsi que les colonnes `Time` (temps écoulé) et `Amount` (montant de la transaction).
- **Tâches réalisées** :
  - Chargement des données avec `pandas`.
  - Exploration des caractéristiques principales (`head()`, `info()`, et `describe()`).
  - Vérification des valeurs manquantes et analyse de la répartition des classes (`Class`).

---

### 2. Préparation des Données
- **Nettoyage des données** :
  - Normalisation des colonnes avec `StandardScaler` pour rendre les caractéristiques comparables.
- **Gestion du déséquilibre des classes** :
  - Utilisation de SMOTE (Synthetic Minority Oversampling Technique) pour équilibrer le dataset.
- **Division des données** :
  - Séparation des données en ensembles d'entraînement (80%) et de test (20%) avec `train_test_split`.

---

### 3. Construction du Modèle
- Modèle choisi : **Random Forest Classifier**.
- Justification :
  - Performant pour les tâches de classification binaire.
  - Résistant au sur-apprentissage pour les caractéristiques bruyantes.
- Entraînement réalisé sur l'ensemble d'entraînement.

---

### 4. Évaluation du Modèle
- Métriques utilisées :
  - Rapport de classification : précision, rappel, F1-score.
  - Matrice de confusion pour visualiser les vrais positifs, vrais négatifs, faux positifs, et faux négatifs.
  - Courbe ROC et AUC pour évaluer les performances globales sur les données déséquilibrées.

---

### 5. Optimisation des Hyperparamètres
- **Technique utilisée** : `GridSearchCV` avec validation croisée (k=3).
- **Hyperparamètres optimisés** :
  - `n_estimators` : Nombre d'arbres dans la forêt.
  - `max_depth` : Profondeur maximale des arbres.
  - `min_samples_split` : Nombre minimal d'échantillons requis pour diviser un nœud.
- **Résultat** : Meilleure combinaison d'hyperparamètres identifiée et réutilisée pour évaluer les performances finales.

---

## Résultats
- **Performances obtenues** :
  - Scores parfaits pour la précision, le rappel, et le F1-score.
  - AUC élevé (> 0.99), indiquant une excellente séparation des classes.
- **Précautions** :
  - Validation sur des données réelles recommandée pour confirmer les résultats.
  - Le modèle peut être sujet au sur-apprentissage en raison de l'utilisation de SMOTE et des hyperparamètres ajustés.

---

## Instructions pour Exécuter le Projet
1. Installer les dépendances nécessaires :
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn
   ```
2. Lancer le notebook : `Credit_Card_Fraud_Detection_FR.ipynb`.
3. Suivre les étapes décrites pour entraîner le modèle et évaluer les performances.

---

## Améliorations Futures
- Tester sur un jeu de données complètement indépendant.
- Intégrer d'autres modèles (XGBoost, LightGBM) pour comparer les performances.
- Envisager une analyse approfondie des caractéristiques les plus importantes dans les prédictions.

---

## Auteurs
Ce projet a été réalisé dans le cadre d'une présentation académique. Il démontre une implémentation pratique des techniques de Machine Learning pour résoudre un problème réel de détection de fraudes.
