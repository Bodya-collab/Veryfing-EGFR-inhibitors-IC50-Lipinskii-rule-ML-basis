# Bioactivity Prediction of EGFR Inhibitors using Machine Learning 
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Library](https://img.shields.io/badge/Library-RDKit-green)
![ML](https://img.shields.io/badge/Model-Random%20Forest-orange)
## 📌 Project Overview
This project focuses on **Computational Drug Discovery**. The goal was to build a Machine Learning pipeline to predict whether a molecule can effectively inhibit **EGFR** (Epidermal Growth Factor Receptor), a key target in non-small cell lung cancer therapy.

Using bioactivity data from the **ChEMBL** database, I performed data curation, calculated molecular descriptors (Lipinski's Rule of 5), and trained a **Random Forest Classifier** to distinguish between active and inactive compounds.

## 🚀 Motivation (Self-Initiated Project)
Although my university curriculum covers *In Silico Methods* in future semesters, I initiated this project independently to gain early hands-on experience in **Cheminformatics** and **Python**. I self-studied the necessary libraries (Pandas, RDKit, Scikit-learn) to implement this pipeline from scratch.

## 🛠️ Tech Stack & Methodology
* **Data Mining:** ChEMBL API (Python client).
* **Cheminformatics:** **RDKit** for SMILES processing and descriptor calculation (MW, LogP, H-Donors, H-Acceptors).
* **Data Analysis:** Pandas & NumPy for data cleaning and labeling.
* **Visualization:** Matplotlib & Seaborn (Chemical Space Analysis).
* **Machine Learning:** **Scikit-learn** (Random Forest Classifier).
* ## 📊 Key Results

### 1. Chemical Space Analysis
I visualized the distribution of active (green) vs. inactive (red) molecules based on Molecular Weight and LogP.
* **Observation:** A significant cluster of active EGFR inhibitors falls within the "drug-like" region defined by **Lipinski's Rule of 5** (MW < 500, LogP < 5), suggesting good oral bioavailability potential.

<img width="833" height="701" alt="Activity" src="https://github.com/user-attachments/assets/aa4a7a47-8e1b-4a66-b469-61d79d1cf871" />
















### 2. Model Performance
* **Algorithm:** Random Forest Classifier (n_estimators=100).
* **Accuracy:** ~67% on the test set.

**Confusion Matrix Analysis:**
The model shows reasonable predictive power but struggles with class imbalance (significantly more inactive compounds than active ones in the dataset).

![Confusion Matrix](IMAGES/confusion_matrix.png)
