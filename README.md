# Obesity Risk Behaviour Clustering

An unsupervised machine learning project applying K-Means and Agglomerative 
Hierarchical Clustering to identify early obesity-risk behavioural patterns 
from lifestyle and dietary data.

## Overview

This project investigates whether unsupervised clustering can uncover early 
obesity-risk behavioural patterns that are useful for preventive healthcare 
and personalised wellness interventions.

**Research Question:** Can unsupervised clustering uncover early obesity-risk 
behavioural patterns that are useful for preventive healthcare and personalised 
wellness interventions?

## Dataset

- **Source:** UCI Machine Learning Repository — Estimation of Obesity Levels 
  Based on Eating Habits and Physical Condition
- **Size:** 2,111 records, 17 features
- **Features:** Age, Height, Weight, physical activity frequency (FAF), 
  water intake (CH2O), eating frequency, transport habits, family history, 
  and more
- **No labels used** — purely unsupervised analysis

## Methodology

1. **EDA** — descriptive statistics, pairplots, missing value checks, 
   variable type identification
2. **Preprocessing:**
   - One-hot encoding of 9 categorical variables 
     (OneHotEncoder, drop='first')
   - Feature joining to produce complete feature matrix
   - StandardScaler normalisation for Euclidean distance compatibility
3. **Optimal k selection** — Elbow Method and Silhouette Score 
   evaluated for k = 2 to 19, optimal k = 5
4. **Model 1: K-Means Clustering** — k=5, random_state=0, 
   PCA visualisation (2D)
5. **Model 2: Agglomerative Hierarchical Clustering** — Ward linkage, 
   Euclidean distance, dendrogram visualisation, PCA 2D projection
6. **Cluster comparison** — cross-tabulation of K-Means vs 
   Hierarchical assignments to confirm stability

## Results

Five interpretable lifestyle clusters identified:

| Cluster | Profile | Risk Level |
|---------|---------|------------|
| 0 | Young, healthy BMI, moderate activity | Low |
| 1 | Low hydration, sedentary, ~92kg | High |
| 2 | Average weight, mixed habits, emerging risk | Moderate |
| 3 | Highest weight ~120kg, high eating frequency, low activity | Critical |
| 4 | Older, sedentary, transport-dependent | Chronic |

Both algorithms produced consistent cluster assignments, confirming 
structural stability in the data.

## Key Findings

- Obesity risk emerges from interacting behavioural patterns, not 
  single isolated variables
- Cluster 3 showed a paradox: high vegetable consumption alongside 
  critical obesity risk — highlighting the complexity of dietary behaviour
- Silhouette scores confirmed moderate but meaningful cluster separation 
  appropriate for behavioural data with natural overlap

## Healthcare and Business Value

- **Preventive healthcare providers** — identify high-risk patients earlier 
  for targeted intervention
- **Digital wellness apps** — personalise recommendations by cluster membership
- **Public health campaigns** — design hydration and activity messaging 
  targeted at specific risk segments

## Tools and Libraries

- Python 3
- scikit-learn (KMeans, AgglomerativeClustering, PCA, 
  StandardScaler, OneHotEncoder, silhouette_score)
- scipy (dendrogram, linkage)
- pandas, numpy
- matplotlib, seaborn

## Files

- `obesity_risk_clustering.ipynb` — full analysis notebook
- `requirements.txt` — Python dependencies

## How to Run

1. Clone this repository
2. Install dependencies: `pip install -r requirements.txt`
3. Download the dataset from the 
   [UCI Repository](https://archive.ics.uci.edu/dataset/544/estimation+of+obesity+levels+based+on+eating+habits+and+physical+condition)
4. Open the notebook in Jupyter or Google Colab
5. Run all cells sequentially

## Author

Amarachukwu Iku 
