# SmartSensor_SKL_ML

## Projet Scikit-learn: Prédiction de l'état de capteurs IoT

Ce projet consiste à construire, avec **Scikit-learn**, un modèle de Machine Learning capable de prédire automatiquement l'état d'un capteur IoT (**OK**, **ALERTE**, **ERREUR**) à partir de ses mesures : température, humidité, pression et consommation énergétique.

Les données proviennent de capteurs installés dans plusieurs bâtiments d'une entreprise, avec pour chaque mesure le bâtiment, la date, l'heure et l'état associé.

Le projet suit le workflow classique du Machine Learning :

```
Dataset → Chargement → Exploration → Nettoyage → X / y → Train / Test →
Prétraitement → Modèle → fit() → predict() → Évaluation → Sauvegarde →
Chargement → Réutilisation
```

## Démarche

- **Exploration & nettoyage** : chargement du dataset, détection et suppression des doublons
- **Sélection des données** : `etat` comme cible (y) ; `temperature`, `humidite`, `pression`, `consommation` comme caractéristiques (X)
- **Découpage train/test** : split stratifié (80/20) garantissant la reproductibilité et la conservation des proportions de classes
- **Prétraitement** : imputation des valeurs manquantes (`SimpleImputer`, stratégie médiane) et mise à l'échelle (`StandardScaler`)
- **Modélisation** : classification par **K plus proches voisins (KNN, k=5)**
- **Évaluation** : accuracy, matrice de confusion (visualisée avec Seaborn), rapport de classification (precision, recall, F1-score)
- **Sauvegarde & réutilisation** : export du modèle via **Joblib** et **Pickle**, rechargement et prédiction sur de nouvelles mesures

## Technologies

- Python
- Pandas / NumPy
- Scikit-learn
- Seaborn / Matplotlib
- Joblib / Pickle
- Jupyter Notebook

## 📁 Structure

```text
SmartSensor_SKL_ML/
├── data/
│   └── mesures_capteurs.csv
├── notebooks/
│   └── atelier_scikit-learn_iot.ipynb
├── models/
│   ├── modele_capteurs.joblib
│   └── modele_capteurs.pkl
└── README.md
```

## Auteur

**Harouna MBAYE**
Intelligence Artificielle, SONATEL ACADEMY
