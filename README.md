# Fraud Detection System

Ce projet implémente un système de **détection de fraude financière** en utilisant des modèles de Machine Learning.  
Il permet de prédire si une transaction est **frauduleuse** ou **normale**, à partir de caractéristiques financières extraites d’un dataset de transactions.

## Fonctionnalités principales

- 🔹 **Exploration et manipulation des données** : analyse des distributions, statistiques descriptives  
- 🔹 **Encodage des variables catégorielles** (type de transaction)  
- 🔹 **Partitionnement des données** : train/test split  
- 🔹 **Feature Scaling** pour normaliser les variables continues  
- 🔹 **Oversampling** pour traiter le déséquilibre de classes (fraud/non-fraud)  
- 🔹 **Modèles entraînés** :
  - Random Forest  
  - XGBoost  
  - Autoencoder pour détection d’anomalies
- 🔹 **Évaluation des modèles** avec :
  - Précision  
  - Rappel  
  - F1-score  
  - Accuracy
- 🔹 **Interface web interactive** avec **Flask** pour tester en temps réel les transactions

## Méthodologie

### 1️⃣ Prétraitement des données 
- Encodage du type de transaction (`TRANSFER`, `CASH_OUT`, `DEBIT`, `CASH_IN`)  
- Normalisation / Scaling des features continues  
- Oversampling pour équilibrer le dataset

### 2️⃣ Modélisation
- **Random Forest**, **XGBoost**, **Autoencoder**  
- Sélection des features clés :
  - `step`  
  - `amount`  
  - `oldbalanceOrg`  
  - `newbalanceOrig`  
  - `oldbalanceDest`  
  - `newbalanceDest`

### 3️⃣ Évaluation
- **Précision, Rappel, F1-score, Accuracy** pour mesurer la performance du modèle sur les transactions frauduleuses et normales

### 4️⃣ Déploiement Web
- Flask pour créer une API `/predict`  
- Génération des features manquantes (`oldbalanceDest` et `newbalanceDest`) selon le type de transaction  
- Retour de la prédiction en JSON :
  - `🚨 Fraude détectée ! 🚨`  
  - `✅ Transaction normale.`



