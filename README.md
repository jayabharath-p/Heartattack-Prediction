🫀 Heart Attack Prediction — 91.8% Accuracy
Can we predict a heart attack before it happens? This project tries to answer that using real patient data and a bunch of machine learning models. The short answer: yes, and pretty accurately too.
---
📌 What This Project Does
It takes basic health measurements from a patient — things like age, cholesterol level, blood pressure, and chest pain type — and predicts whether they are at risk of a heart attack or not.
We tested 7 different machine learning models and found that Support Vector Machine (SVM) performs best, hitting 91.8% accuracy.
---
📁 Dataset
File: `heart.csv`  
Rows: 303 patients  
Columns: 14 features
Column	What It Means
`age`	Age of the patient
`sex`	Gender (1 = Male, 0 = Female)
`cp`	Chest pain type (0–3)
`trestbps`	Resting blood pressure (mm Hg)
`chol`	Cholesterol level (mg/dl)
`fbs`	Fasting blood sugar > 120 mg/dl (1 = Yes, 0 = No)
`restecg`	Resting ECG results (0–2)
`thalach`	Maximum heart rate achieved
`exang`	Exercise-induced angina (1 = Yes, 0 = No)
`oldpeak`	ST depression caused by exercise
`slope`	Slope of the peak exercise ST segment
`ca`	Number of major blood vessels (0–3)
`thal`	Thalium stress test result
`target`	Heart attack risk (1 = Yes, 0 = No)
No missing values. One duplicate row was removed during cleaning.
---
🔍 What's Inside the Notebook
Loading & Exploring the Data — checking shape, nulls, duplicates, and data types
Data Visualization — charts for gender breakdown, chest pain types, age distribution, correlation heatmap, violin plots, and more
Data Preprocessing — feature scaling with `StandardScaler`, 80/20 train-test split
Model Training & Comparison — 7 models tested side by side
---
🤖 Models Compared
Model	Notes
Logistic Regression	Simple and solid baseline
Gaussian Naive Bayes	Fast probabilistic approach
Bernoulli Naive Bayes	Works well on binary features
Support Vector Machine (SVM)	⭐ Best performer — 91.8% accuracy
Random Forest	Ensemble of decision trees
K-Nearest Neighbors (KNN)	Optimized at k=7
XGBoost	Gradient boosting powerhouse
---
🛠️ Tech Stack
Python 3
pandas, numpy
matplotlib, seaborn
scikit-learn
xgboost
---
🚀 How to Run
Clone this repo
```bash
   git clone https://github.com/your-username/heart-attack-prediction.git
   cd heart-attack-prediction
   ```
Install dependencies
```bash
   pip install pandas numpy matplotlib seaborn scikit-learn xgboost
   ```
Open the notebook
```bash
   jupyter notebook heartattack-prediction-with-91-8-accuracy.ipynb
   ```
Run all cells top to bottom — that's it!
---
📊 Key Findings
Patients aged 55–60 had the highest density of heart attack risk
SVM was the most accurate model at 91.8%
Most models performed above 80%, showing the dataset is well-suited for classification
Chest pain type and maximum heart rate were strong indicators of risk
---
📬 Contact
Feel free to open an issue or reach out if you have questions or suggestions!
