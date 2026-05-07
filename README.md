# Heart Attack Prediction

A machine learning classification project that predicts the likelihood of a heart attack based on clinical patient data. Seven algorithms are benchmarked against each other, with Support Vector Machine achieving the highest accuracy of **91.8%**.

---

## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Methodology](#methodology)
- [Results](#results)
- [Installation](#installation)
- [Usage](#usage)
- [Dependencies](#dependencies)
- [License](#license)

---

## Overview

Cardiovascular disease is one of the leading causes of death worldwide. Early and accurate prediction of heart attack risk can be life-saving. This project applies supervised machine learning techniques to clinical data in order to classify patients as at-risk or not at-risk, and evaluates multiple classifiers to identify the best-performing model.

---

## Dataset

**Source:** [Heart Attack Analysis & Prediction Dataset — Kaggle](https://www.kaggle.com/datasets/rashikrahmanpritom/heart-attack-analysis-prediction-dataset)  
**File:** `heart.csv`  
**Samples:** 303 patients (1 duplicate removed)  
**Features:** 13 input features, 1 binary target

| Feature | Description |
|---|---|
| `age` | Age of the patient |
| `sex` | Sex (1 = Male, 0 = Female) |
| `cp` | Chest pain type (0 = Typical Angina, 1 = Atypical Angina, 2 = Non-anginal, 3 = Asymptomatic) |
| `trestbps` | Resting blood pressure (mm Hg) |
| `chol` | Serum cholesterol (mg/dl) |
| `fbs` | Fasting blood sugar > 120 mg/dl (1 = True, 0 = False) |
| `restecg` | Resting ECG results (0 = Normal, 1 = ST-T wave abnormality, 2 = Left ventricular hypertrophy) |
| `thalach` | Maximum heart rate achieved |
| `exang` | Exercise-induced angina (1 = Yes, 0 = No) |
| `oldpeak` | ST depression induced by exercise relative to rest |
| `slope` | Slope of the peak exercise ST segment |
| `ca` | Number of major vessels colored by fluoroscopy (0–3) |
| `thal` | Thalium stress test result |
| `target` | **Output** — Heart attack risk (1 = Higher risk, 0 = Lower risk) |

---

## Project Structure

```
heart-attack-prediction/
│
├── heart.csv                                          # Dataset
├── heartattack-prediction-with-91-8-accuracy.ipynb   # Main notebook
└── README.md
```

---

## Methodology

### 1. Exploratory Data Analysis
- Distribution analysis for all features (age, cholesterol, blood pressure, heart rate)
- Class balance check for the target variable
- Correlation matrix and pairplot visualization
- Countplots and violin plots for categorical features

### 2. Data Preprocessing
- Verified zero null values across all columns
- Removed one duplicate row
- Applied `StandardScaler` for feature normalization
- Split data: **80% training / 20% testing** (`random_state=0`)

### 3. Model Training
Seven classifiers were trained and evaluated:

| # | Model | Notes |
|---|---|---|
| 1 | Logistic Regression | Linear baseline classifier |
| 2 | Gaussian Naive Bayes | Probabilistic model assuming normal distribution |
| 3 | Bernoulli Naive Bayes | Probabilistic model for binary/boolean features |
| 4 | Support Vector Machine | RBF kernel; best overall performer |
| 5 | Random Forest | 100 estimators, `random_state=0` |
| 6 | K-Nearest Neighbors | Optimized via error-rate curve; k=7 selected |
| 7 | XGBoost | Gradient-boosted tree ensemble |

---

## Results

| Model | Accuracy |
|---|---|
| **Support Vector Machine** | **91.8%** |
| Logistic Regression | ~85% |
| Gaussian Naive Bayes | ~85% |
| Bernoulli Naive Bayes | ~83% |
| Random Forest | ~85% |
| K-Nearest Neighbors (k=7) | ~87% |
| XGBoost | ~88% |

> **SVM achieved the best accuracy at 91.8%**, correctly classifying 54 of 61 test samples.

---

## Installation

```bash
git clone https://github.com/jayabharath-p/heart-attack-prediction.git
cd heart-attack-prediction
pip install -r requirements.txt
```

**Or install dependencies manually:**

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost jupyter
```

---

## Usage

Launch Jupyter Notebook and open the project file:

```bash
jupyter notebook heartattack-prediction-with-91-8-accuracy.ipynb
```

Run all cells sequentially. The notebook is self-contained — EDA, preprocessing, model training, and evaluation are all included in order.

---

## Dependencies

| Library | Purpose |
|---|---|
| `pandas` | Data loading and manipulation |
| `numpy` | Numerical computation |
| `matplotlib` | Plotting |
| `seaborn` | Statistical data visualization |
| `scikit-learn` | Machine learning models and utilities |
| `xgboost` | Gradient boosting classifier |

Python 3.7+ required.

---

## License

This project is open source and available under the [MIT License](LICENSE).
