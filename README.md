# Synthetic data
# Overview

This repository contains the Python-based analytical framework for evaluating synthetic healthcare data in neonatal clinical research, with a focus on necrotizing enterocolitis (NEC) prediction.

Neonatal clinical datasets are often limited by small sample sizes, severe class imbalance, and restrictions on patient-level data sharing. This project investigates the potential of synthetic data to address these challenges while evaluating its impact on downstream predictive performance and patient privacy.

# Research Objectives

- Assess the distributional similarity between real and synthetic healthcare data.

- Evaluate synthetic data augmentation for NEC prediction.

- Compare traditional oversampling and generative modeling approaches.

- Assess potential patient-level and attribute-level disclosure risks.

- Investigate the trade-off between synthetic data utility and privacy.

# Methodology

## 1. Synthetic Data Generation

- Synthetic Minority Oversampling Technique (SMOTE)
- Tabular Variational Autoencoder (TVAE)
- Class-stratified synthetic data generation

## 2. Distributional Similarity

- Principal Component Analysis (PCA)

## 3. Machine Learning and Predictive Utility

Two machine learning models were evaluated:

- Logistic Regression
- XGBoost

Four training strategies were compared:

- Real data only
- SMOTE-augmented data
- Synthetic data only
- Combined SMOTE and synthetic data

All models were evaluated using a held-out real test dataset.

Performance metrics included:

- Area Under the Receiver Operating Characteristic Curve (AUROC)
- Area Under the Precision-Recall Curve (AUPRC)
- Sensitivity and specificity
- Precision
- F1 score
- Matthews Correlation Coefficient (MCC)
- Brier score and calibration
- Calibration Analysis
- Decision Curve Analysis (DCA)

## 4. Privacy and Disclosure Risk Evaluation

Three complementary approaches were used to assess potential privacy risks associated with synthetic data:

- **Membership Inference Analysis (MIA):** Assesses whether an individual's participation in the original training dataset can be inferred.
- **Attribute Inference Analysis (AIA):** Evaluates the potential disclosure of sensitive clinical attributes.
- **Distance-to-Closest-Record (DCR):** Nearest-neighbor analysis was additionally performed to identify exact record matches and assess the proximity of synthetic records to real patient records.

# Repository Structure
## Notebook Description

**Principal_Component_Analysis.ipynb:** Comparison of real and synthetic data distributions using PCA
**Logistic_Regression.ipynb:** Logistic regression model development and evaluation
**XGBoost.ipynb:** Gradient-boosted model development and evaluation
**Model_results.ipynb:** Comparative analysis of model performance
**Distance_to_Closest_Record_Analysis.ipynb:** Record-level similarity and nearest-neighbor analysis
**Membership_Inference_Analysis.ipynb:** Patient-level membership disclosure risk evaluation
**Attribute_Inference_Analysis.ipynb:** Attribute-level disclosure risk evaluation

# Key Findings

- Synthetic data augmentation improved NEC sensitivity without consistent improvements in discrimination or precision.
- Models trained exclusively on synthetic data tended to overestimate NEC risk.
- Combined SMOTE and synthetic data training achieved the highest observed F1 and MCC scores among the evaluated training strategies.
- Membership inference analysis demonstrated limited distinguishability between training and non-training records, with an AUROC of 0.546.
- Nearest-neighbor analysis identified exact matches for 0.08% of real training records across the evaluated features.

These findings highlight the potential of synthetic data as a complementary approach to real clinical data, rather than a replacement, and emphasize the importance of evaluating both predictive utility and privacy risks.

# Technologies and Tools

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Imbalanced-learn
- Synthetic Data Vault (SDV)
- Matplotlib
- Seaborn

# Applications

- Healthcare artificial intelligence
- Clinical machine learning
- Synthetic healthcare data generation and evaluation
- Rare disease and imbalanced clinical outcome prediction
- Patient privacy and disclosure risk assessment
- Neonatal and pediatric research

# License

This repository is distributed under the MIT License. See the LICENSE file for details.

# Author

Shilpa Muralidhar, PhD
Research interests: Healthcare Artificial Intelligence, Clinical Machine Learning, Synthetic Data, and Neonatal Research.
