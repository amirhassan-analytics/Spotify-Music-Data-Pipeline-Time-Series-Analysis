# 🎧 Advanced Data Mining & Time-Series Analysis on Spotify Dataset

## Genre Classification | Pattern Mining | Time-Series Forecasting | Deep Learning

## 📌 Overview
This project extends traditional data mining by combining machine learning, pattern discovery, clustering, and time-series analysis to uncover complex structures within Spotify's vast music dataset. The goal was to classify music genres, detect hidden audio trends over time, and implement AI-driven models for predictive modeling and feature importance.

This was part of our Advanced Data Mining coursework and showcases a full-fledged ML pipeline, including deep learning models and explainable AI tools.

🎯 Project Objectives

📊 Classify music genres using both traditional and ensemble ML models

📈 Extract patterns and motifs from time-series audio features

🧠 Apply deep learning (CNN, RNN) for genre recognition

📉 Forecast music popularity and genre distribution

🧩 Use SHAP and LIME for model interpretability

🔍 Analyze temporal behaviors in audio trends

## 📁 Dataset
◉ Source: Spotify API / Public repositories

◉ Tracks: 109,547

◉ Artists: 30,141

◉ Features: tempo, danceability, energy, valence, acousticness, instrumentalness, loudness, etc.

◉ Format: Tabular, temporal, and categorical

## ⚙️ Tools & Technologies
◉ Languages: Python

◉ Libraries: scikit-learn, xgboost, keras, tensorflow, shap, lime, tslearn, matplotlib, pandas, seaborn

◉ Platforms: Jupyter, Colab

◉ Models: SVM, k-NN, Decision Tree, Random Forest, Gradient Boosting, AdaBoost, CNN, LSTM

## 🧪 Methodology & Implementation
### 1. Data Preprocessing
➤ Merged track and artist datasets

➤ Handled missing values with mean imputation

➤ Feature normalization and encoding for ML

➤ Final dataset: 938,597 records, 17 engineered features

### 2. Clustering Analysis
➤ Algorithms: K-Means, DBSCAN, Hierarchical Clustering

➤ Optimized K using Elbow Method & Silhouette Score (Best = 0.452)

➤ Discovered 6 latent clusters beyond predefined genre tags

### 3. Genre Classification
➤ Algorithms: Decision Tree, k-NN, Naïve Bayes, XGBoost, Gradient Boosting, AdaBoost

➤ Achieved 58.5% accuracy (k-NN) for multi-class genre classification

➤ Ensemble methods improved stability and generalization

### 4. Time-Series Pattern Discovery
➤ Reduced dimensionality with PAA (Piecewise Aggregate Approximation)

➤ Extracted motifs and anomalies using Dynamic Time Warping (DTW) and Shapelets

➤ Analyzed how audio features evolved over time per genre

### 5. Deep Learning for Genre Prediction
➤ Implemented:

➜ CNN for feature abstraction → 24.1% accuracy

➜ LSTM for sequential feature prediction

➜ MLP for baseline comparison

➜ Input: Time-series extracted from audio feature windows

### 6. Explainable AI (XAI)
➜ Applied SHAP & LIME for interpreting black-box models

➜ Identified danceability, energy, and artist popularity as top predictors

➜ Generated per-sample and global explanations for insights

### 7. Binary Classification - Track Popularity
➜ Target: Popular vs. Non-popular (based on play counts/ratings)

➜ Achieved 97.1% accuracy using XGBoost

## 📊 Key Results
➜ Task	Best Model	Accuracy / Score
➜ Multi-class Genre Classification	k-NN	58.5%
➜ Popularity Binary Classification	XGBoost	97.1%
➜ Time-Series Motif Extraction	DTW + Shapelets	Visual Insights Only
➜ Deep Learning Genre Classifier	CNN	24.1%
➜ Best Clustering Score	Hierarchical	0.452 (silhouette)

## 📌 Visualizations
🎯 Confusion matrices for genre classification

🔍 SHAP summary plots for global feature impact

📉 Line plots of time-series features by genre

📊 Bar and pie charts for genre distribution

📈 Cluster visualizations using PCA-reduced data

## 🧠 Learnings & Takeaways
➤ Clustering reveals genre-independent groupings—some genres share audio characteristics

➤ Time-series features help in understanding evolution of music preferences

➤ Explainable AI is essential for model trust, especially in creative domains like music

➤ Deep learning works best when large datasets and rich time-context are available

