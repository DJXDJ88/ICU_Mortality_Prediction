# ICU_Mortality_Prediction
Predicting In-Hospital Mortality using Structured Clinical Data

# Project Overview
This project focuses on predicting in-hospital mortality of ICU patients using structured clinical data from the PhysioNet / Computing in Cardiology Challenge 2012 dataset.
Instead of time-series modeling, this work formulates the task as a binary classification problem based on fixed, aggregated patient features, with particular attention to class imbalance and clinically relevant evaluation metrics.

# Problem Statement
Objective: Predict whether an ICU patient will die during hospitalization
Label: In-hospital death (0 = Alive, 1 = Death)
Challenge:
Strong class imbalance
Accuracy alone is misleading
Clinical priority: identify high-risk (death) patients

# Methodology
1. Data Preprocessing
Missing value handling
Feature selection and normalization
Train / test split with class distribution preserved
2. Class Imbalance Handling
SMOTE (Synthetic Minority Oversampling Technique) applied on training data
Class-weighted models to penalize false negatives (death misclassification)
3. Models Used
Logistic Regression (baseline)
Random Forest Classifier
Gradient-based classifiers with adjustable class weights

# Evaluation Metrics
Given the imbalanced nature of the data, multiple metrics were used:
AUC (ROC-AUC) – overall risk discrimination ability
Recall (Death class) – ability to correctly identify high-risk patients
F1-score (Death class) – balance between precision and recall
Accuracy (reported but not the primary metric)
### The project prioritizes risk ranking and recall, rather than raw accuracy.

# Key Results
Achieved good ranking performance (AUC) despite moderate accuracy
Demonstrated the trade-off between recall and precision in clinical risk prediction
Highlighted the importance of threshold and cost-sensitive learning

# Key Insights
High AUC with low recall at default threshold indicates good risk ranking but conservative decision boundary
Adjusting class weights increases recall at the cost of precision
No single metric is optimal — metric choice depends on clinical priorities
Accuracy alone is not appropriate for imbalanced medical datasets
