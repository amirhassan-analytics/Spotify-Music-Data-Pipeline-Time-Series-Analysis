# 🎵 Data Mining & Pattern Discovery on Spotify Dataset 

## Music Genre Classification, Clustering, and Association Rule Mining 
### A Machine Learning & Data Mining Project by Amir Hassan 

## 📌 Overview
This project explores data mining techniques on a large Spotify dataset to uncover insights about audio features, music genres, and behavioral patterns. We applied clustering, classification, and association rule mining to not only classify genres but also find hidden relationships within musical elements.

## 🚀 Objectives
◉ Classify music genres based on Spotify's audio features

◉ Discover patterns and relationships through clustering and association rules

◉ Predict the genre of a track using classification and rule-based systems

◉ Analyze genre characteristics and the contribution of audio attributes

## 📊 Dataset
➤ Source: [Spotify Tracks Dataset from Kaggle / UCI repository]

➤ Size: ~15,000 tracks with 24 features

➤ Features Include: tempo, danceability, energy, acousticness, instrumentalness, genre, etc.

## 🔧 Techniques & Methodology
### 1. Data Preprocessing
➤ Handled missing values

➤ Applied outlier detection via IQR

➤ Feature normalization and transformation (log/sqrt)

### 2. Clustering Analysis
➤ Algorithms: K-Means, Bisecting K-Means, DBSCAN, Hierarchical Clustering

➤ Evaluated using silhouette scores (Best: 0.452)

➤ Grouped songs into distinct audio-based clusters

### 3. Classification Models
📌 Algorithms: Decision Tree, k-NN, Naïve Bayes

## Accuracy:

➤ Decision Tree: ~51%

➤ k-NN: ~58.5% (Best)

➤ Used feature selection and hyperparameter tuning for optimization

### 4. Pattern Mining with Apriori Algorithm
➤ Discovered frequent itemsets and genre-based rules

➤ Achieved an average lift score of 17+ for genre-based rules

➤ Example Rule: If acousticness is high and energy is low → Genre = Sleep

### 5. Rule-Based Prediction
➤ Built a custom classifier using mined association rules

➤ Achieved 96% accuracy in binary genre prediction (e.g., “Sleep” vs. others)

## 📈 Visualizations
➤ Pie charts for genre distributions

➤ Cluster visualizations (2D PCA plots)

➤ Rule graphs showing item associations

➤ Bar graphs for classification performance

## 🧠 Tools & Technologies
➤ Language: Python

➤ Libraries: scikit-learn, mlxtend, pandas, matplotlib, seaborn

➤ Environment: Jupyter Notebooks / Colab

## 🔍 Key Takeaways
➤ Unsupervised learning reveals meaningful audio-based groupings

➤ Association rules can enhance classification, especially in niche genres

➤ Pattern mining is a valuable tool for understanding genre characteristics and user behavior
