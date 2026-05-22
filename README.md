Overview
This repository contains the code and analytical pipeline for our study investigating the prediction of medication non-adherence among chronic disease patients (diabetes, hypertension, and dyslipidaemia) in a multi-ethnic Malaysian context.

The study uniquely integrates Complementary and Alternative Medicine (CAM) beliefs alongside clinical and sociodemographic variables to predict adherence risk.

The methodology relies on advanced machine learning techniques, feature selection, and SHAP (SHapley Additive exPlanations) for model interpretability, moving beyond conventional statistical approaches to capture complex behavioural determinants.

Publication: This code supports our manuscript submitted to PLOS ONE. [Insert Link to Published Article Here, once available]

Project Workflow and Methodology
The analytical pipeline within this repository is structured around the following key phases:

Data Preprocessing & Balancing:

Implementation of data cleaning and preprocessing for survey-based data.

Evaluation of class distribution strategies: comparing naturally unbalanced datasets (17:13 ratio) against synthetic balancing techniques (SMOTE-Tomek).

Targeted Feature Selection:

Execution of Sequential Backward Elimination to systematically reduce dimensionality.

Comparison of feature selection algorithms using Logistic Regression (LR), Support Vector Machines (SVM), and Random Forest (RF). LR-selected variables were identified as the most optimal approach.

Model Training and Evaluation:

Training and evaluation of 120 model configurations.

Construction of base learners and advanced stacked ensembles (GLM, RF, GBM).

The Stacked Ensemble GLM utilizing LR-selected variables on the unbalanced dataset was identified as the best-performing model (AUC: 0.816).

Model Interpretability (SHAP):

Application of SHAP analysis to decode the "black-box" nature of the ensemble model.

Extraction of feature importance and directional impacts, specifically highlighting the profound predictive power of psychological factors like Belief in Natural Treatments and Belief in Holistic Health (measured via the CAMBI scale).

Clinical Risk Stratification:

Calculation of the Youden Index and implementation of Decision Curve Analysis (DCA).

Identification of the optimal clinical threshold (0.40) to balance diagnostic accuracy (minimizing false negatives) with real-world clinical utility for patient interventions.

Data Description
Input Features: 19 independent variables encompassing sociodemographics (e.g., ethnicity, education), clinical characteristics (e.g., no. of dodes, treatment duration), and psychosocial constructs (CAMBI scores).

Target Variable: Medication adherence operationalized dichotomously using the Malaysian Medication Adherence Scale (MALMAS), where a score of <6 indicates non-adherence.

Note: Due to patient privacy and ethical restrictions, the raw clinical dataset is not publicly hosted in this repository.
