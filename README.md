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

<img width="781" height="660" alt="image" src="https://github.com/user-attachments/assets/a288142c-4b72-4d4c-a071-232363c25848" />
















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






## 5. Advanced Validation: Generative AI & Cross-Scoring
To rigorously validate the lead candidate beyond traditional docking, I implemented a **State-of-the-Art Deep Learning pipeline** using **DiffDock** (Diffusion Generative Model) and cross-validated the results with **GNINA** (CNN-based Scoring).

### Method 1: Generative Inference (DiffDock)
I deployed the DiffDock inference pipeline on Google Colab (T4 GPU) to blindly predict the binding conformation of `CHEMBL52765` within the EGFR pocket (PDB: 1M17).

* **Visual Result:** The model successfully positioned the ligand deep within the ATP-binding pocket. The predicted pose (red/grey sticks) shows excellent steric fit within the protein ribbons.

<img width="1517" height="648" alt="image" src="https://github.com/user-attachments/assets/eba5b435-fa01-4ab3-b3f9-9b9f13858e0b" />









### Method 2: Confidence Correlation Analysis (Validation)
To ensure the reliability of the AI predictions, I correlated **DiffDock's Confidence Score** with **GNINA's Binding Affinity** (physics-based scoring).

* **Statistical Finding:** There is a **strong correlation (r = -0.734)** between the model's confidence and the calculated binding energy.
* **Interpretation:** As the AI becomes more confident in a pose (X-axis increases), the physical binding energy becomes more favorable (Y-axis decreases). This convergence of **Generative AI** and **Biophysics** strongly supports the validity of the identified lead candidate.

 <img width="752" height="577" alt="image" src="https://github.com/user-attachments/assets/99b070dd-fb47-4a19-9485-3312e3cdc0be" />






## 6.Conclusion 
This project successfully demonstrates a comprehensive computational drug discovery workflow, bridging the gap between raw biological data and actionable chemical insights. By integrating Machine Learning (Random Forest) with structural analysis, I achieved the following:
* Effective screening
* Lead compound optimization
* Structual Validation
The next step is using AI tool in order to compare AI prediction with SWISSDOC prediction and prove that this compound fits as good as Elotinib. We can see strong corelation in both methods which proves theory.
This self-initiated study allowed me to master key Cheminformatics tools (RDKit), Molecular docking tools including as standard SWISSDOC and PYMOL as an AI prediction systems.  and Data Science libraries independently, proving that in silico methods can significantly accelerate the early stages of pharmaceutical research.

## 👤 Author
**Bohdan Lazepnikov **
* Student at Jagiellonian University (Faculty of Chemistry).
* Interests: Bioanalysis, Computational Chemistry, Drug Design.

