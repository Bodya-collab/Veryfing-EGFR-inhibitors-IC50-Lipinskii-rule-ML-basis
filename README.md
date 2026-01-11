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

<img width="505" height="470" alt="загружено" src="https://github.com/user-attachments/assets/13a1491f-258d-4b84-a546-4024730351c9" />















### 3.Optimalization process 
* **Figure 3**: Multi-Parameter Optimization (MPO) Strategy To prioritize candidates with the highest clinical potential, I plotted Potency (IC50) against Drug-likeness (QED Score).

* **Y-Axis (Potency)**: IC50 values on a logarithmic scale (inverted). Points higher up represent more potent compounds.
* **X-Axis (Quality)**: QED score (0 to 1). Points further to the right represent molecules with better physicochemical properties (solubility, permeability).

* **Key Finding**: The plot reveals Top-Right Quadrant, containing compounds that are both highly potent (IC50 < 1000 nM) and highly drug-like (QED > 0.6). While some compounds showed extreme potency at Top-Left, their low QED scores suggest potential toxicity or poor absorption, making them unsuitable for drug development. The analysis successfully filtered the dataset down to high-quality lead candidates (e.g., CHEMBL52765) can be synthesized for in vitro studies. 


<img width="1125" height="547" alt="Optimalization QED score" src="https://github.com/user-attachments/assets/ef8bb7d5-a6d5-45eb-bb12-afeb4576c684" />









                                                                   



## 4.Comparing potencial with true drug 
* To validate the potential mechanism of action for the identified lead candidate (CHEMBL52765), I analyzed the co-crystallized structure of EGFR with the reference inhibitor Erlotinib (PDB ID: 1M17). SWISSDOC simulation had showed only physics state, where 3 molekules of CHEMBL52765 are connected to different places in 1M17 including target place. It shows that CHEMBL52765 also complete inhibition in the same place as Erlotinib.

* **Figure 4.** Binding Mode Analysis (Validation Step)
* <img width="820" height="456" alt="image" src="https://github.com/user-attachments/assets/20f7664b-de84-43b6-99cd-815cf75044df" />












## 5.Conclusion 
This project successfully demonstrates a comprehensive computational drug discovery workflow, bridging the gap between raw biological data and actionable chemical insights. By integrating Machine Learning (Random Forest) with structural analysis, I achieved the following:
* Effective screening
* Lead compound optimization
* Structual Validation
This self-initiated study allowed me to master key Cheminformatics tools (RDKit) and Data Science libraries independently, proving that in silico methods can significantly accelerate the early stages of pharmaceutical research.

## 👤 Author
**Bohdan Lazepnikov **
* Student at Jagiellonian University (Faculty of Chemistry).
* Interests: Bioanalysis, Computational Chemistry, Drug Design.

