# Heart-Disease-Prediction-with-Interactive-ML-Dashboard
An interactive machine learning dashboard built with Dash and Plotly for end-to-end ML workflow visualization. Covers EDA, data preprocessing, classification (Random Forest), clustering (KMeans), and model interpretability (SHAP, LIME, PDP) — applied to heart disease prediction using the Kaggle Heart Disease dataset.
# 🫀 Heart Disease Prediction — Interactive ML Dashboard

> An end-to-end machine learning workflow dashboard for heart disease prediction, built with Dash and Plotly. Covers EDA, preprocessing, classification, clustering, and model interpretability — all in one interactive web application.

---

## 📌 Project Overview

This project was developed as a Capstone for **INFO-6151 — Data Visualization** at **Fanshawe College (2026)**.

The goal was to build a comprehensive, interactive dashboard that assists machine learning practitioners and non-technical stakeholders in visualizing and interpreting every stage of an ML workflow — from raw data exploration through model explainability.

**Dataset:** [Heart Disease Prediction Dataset — Fedesoriano (Kaggle)](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction)  
**Task:** Binary Classification — predict presence of heart disease (0 = No Disease, 1 = Heart Disease)  
**Model:** Random Forest Classifier  
**Dashboard:** Dash by Plotly

---

## 🎯 Key Results

| Metric | Score |
|---|---|
| Accuracy | 87.0% |
| Precision | 88.2% |
| Recall | 88.2% |
| F1-Score | 0.882 |
| ROC-AUC | 0.93 |

---

## 🗂️ Project Structure

```
├── Capston_Project_Group_11.ipynb   # Main Jupyter Notebook (full workflow)
├── requirements.txt                 # Python dependencies
└── README.md                        # Project documentation
```

---

## 📊 Dashboard Modules

The interactive dashboard is organized into **6 tabs:**

### 📊 1. EDA (Exploratory Data Analysis)
- Interactive histograms and box plots — switchable per feature
- Scatter plots with selectable X/Y axes
- Correlation matrix heatmap

### ⚙️ 2. Preprocessing
- Side-by-side before/after StandardScaler visualization
- Select any feature to inspect its scaling transformation

### 🎯 3. Model Evaluation
- Confusion Matrix
- ROC Curve (AUC = 0.93)
- Precision-Recall Curve
- Feature Importance bar chart

### 🔵 4. Clustering
- KMeans elbow plot (optimal K selection)
- 3D PCA cluster scatter plot

### 🔍 5. Interpretability
- SHAP global feature importance (interactive slider)
- SHAP dependence plot (feature dropdown)
- Decision boundary visualization (top 2 SHAP features)

### 📁 6. Upload Dataset
- Drag-and-drop CSV upload
- Instant preview of uploaded data (first 10 rows)

---

## 🔬 Full Notebook Workflow

The Jupyter notebook covers the complete ML pipeline:

| Step | Description |
|---|---|
| Data Quality Audit | Detect hidden zero values and invalid clinical readings |
| Median Imputation | Replace physiologically impossible zeros in Cholesterol and RestingBP |
| Label Encoding | Convert categorical features to numerical codes |
| Feature Scaling | StandardScaler normalization |
| EDA | Histograms, box plots, scatter plots, pair plots, correlation matrix, outlier detection |
| Model Training | Random Forest (n_estimators=100, random_state=42) |
| Model Evaluation | Confusion matrix, ROC curve, PR curve, Q-Q plot, residual plot, prediction vs actual |
| Feature Importance | Random Forest importances + SHAP summary, dependence, and beeswarm plots |
| Clustering | KMeans (K=4), PCA 2D/3D, t-SNE, cumulative variance analysis |
| Interpretability | SHAP (global), LIME (local), Partial Dependence Plots, Feature Interaction plots |
| Dashboard | Full Dash app with 6 interactive tabs |

---

## 🗃️ Dataset

**Source:** [Kaggle — Heart Failure Prediction Dataset by Fedesoriano](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction)

| Property | Details |
|---|---|
| Rows | 918 patients |
| Features | 11 clinical + 1 target |
| Target | HeartDisease (0 / 1) |
| Source | 5 hospitals across US, Hungary, Switzerland |

**Features:**

| Feature | Description |
|---|---|
| Age | Age of the patient (years) |
| Sex | M / F |
| ChestPainType | TA, ATA, NAP, ASY |
| RestingBP | Resting blood pressure (mm Hg) |
| Cholesterol | Serum cholesterol (mm/dl) |
| FastingBS | Fasting blood sugar > 120 mg/dl (1/0) |
| RestingECG | Normal / ST / LVH |
| MaxHR | Maximum heart rate achieved |
| ExerciseAngina | Exercise-induced angina (Y/N) |
| Oldpeak | ST depression induced by exercise |
| ST_Slope | Slope of peak exercise ST segment (Up/Flat/Down) |
| **HeartDisease** | **Target — 0: No Disease, 1: Heart Disease** |

---

## ⚙️ Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/heart-disease-ml-dashboard.git
cd heart-disease-ml-dashboard
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Download the dataset

```bash
pip install kagglehub
```

The notebook handles the download automatically using `kagglehub`. You will need a Kaggle account.

Alternatively, download the CSV manually from [Kaggle](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction) and place it in the project root.

### 4. Run the notebook

```bash
jupyter notebook Capston_Project_Group_11.ipynb
```

Run all cells in order. The Dash app launches automatically at the last cell.

### 5. Open the dashboard

```
http://127.0.0.1:8050/
```

---

## 📦 Requirements

```
numpy
pandas
matplotlib
seaborn
scikit-learn
shap
lime
plotly
dash
scipy
kagglehub
jupyter
```

Install all at once:

```bash
pip install -r requirements.txt
```

---

## 🧠 Key Findings

- **ST_Slope** is the single most important predictor of heart disease — confirmed by both Random Forest feature importance and SHAP values
- **ChestPainType (Asymptomatic)** and **MaxHR** are the strongest secondary predictors
- **172 patients** had physiologically impossible zero cholesterol values — a critical hidden data quality issue discovered during EDA
- **KMeans with K=4** revealed 4 distinct patient risk profiles
- **t-SNE** provided significantly clearer cluster separation than PCA (2D PCA only captured 24.8% variance)
- **LIME** enabled patient-level explanations — ST_Slope was the dominant factor for the highest-risk individuals

---

## 📈 Visualizations Included

| Category | Visualizations |
|---|---|
| EDA | Histograms, Box Plots, Scatter Plots, Pair Plots, Correlation Matrix, Outlier Detection |
| Preprocessing | Before/After scaling, Encoding comparison |
| Model Evaluation | Confusion Matrix, ROC Curve, PR Curve, Q-Q Plot, Residual Plot, Prediction vs Actual |
| Feature Importance | RF Importance, SHAP Bar, SHAP Beeswarm, SHAP Dependence |
| Clustering | Elbow Plot, KMeans, PCA 2D, PCA 3D, t-SNE, Cumulative Variance |
| Interpretability | LIME explanation, Partial Dependence Plots, Feature Interaction, Decision Boundary |

## 🙏 Acknowledgements

- Dataset: [Fedesoriano — Heart Failure Prediction Dataset (Kaggle)](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction)
