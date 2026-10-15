# Breast Cancer Prediction: Classification Methods Evaluation

This repository contains a Data Mining and Machine Learning project focused on predicting breast cancer malignancy using the **Breast Cancer Wisconsin (Diagnostic)** dataset. The project evaluates multiple classification algorithms, placing a strong emphasis on maximizing **Recall (Sensitivity)** to minimize false-negative results, which is a critical safety requirement in medical diagnostics.

## Project Overview
The analysis was fully implemented using **RapidMiner** and involves a complete machine learning pipeline:
1.  **Data Preprocessing:** Feature scaling using Z-transformation to ensure distance-based algorithms function correctly.
2.  **Class Imbalance Handling:** Application of **SMOTE** (Synthetic Minority Over-sampling Technique) within the cross-validation loop to prevent data leakage and bias towards the majority class (Benign).
3.  **Hyperparameter Tuning:** Utilizing Grid Search to find the optimal parameters for each model (e.g., *k* in k-NN, *C* in SVM, and *number of trees/depth* in Random Forest).
4.  **Model Evaluation:** Robust evaluation using 10-fold Cross-Validation comparing Accuracy, Precision, Recall, and AUC.

## Models Evaluated & Key Results
*   **Support Vector Machine (SVM):** Achieved the highest overall Accuracy (97.37%) and Precision (98.05%), proving highly reliable for general classification.
*   **Random Forest (RF):** Achieved an Accuracy of 96.49% but delivered the **highest Recall (95.28%)** for the malignant class, making it the safest and most appropriate model for clinical application.
*   **k-Nearest Neighbors (k-NN):** Reached 96.49% Accuracy and the highest AUC (0.994), though it slightly lagged in Recall compared to RF.

## Feature Importance
Using Information Gain, the analysis revealed that the "Worst" geometric features—specifically **Perimeter Worst, Radius Worst, and Area Worst**—are the most critical indicators for predicting malignancy.

## Technologies & Tools
*   **RapidMiner Studio:** Used for building the data pipelines, training the models, and extracting visualizations.

## AI Assistance & Tooling
During the documentation and structuring phase of this repository in October 2026, **Google Gemini 3** was utilized as an AI assistant. The AI helped structure this README, format the project for GitHub, and translate core Greek project insights into a professional English summary.

## Repository Structure
*   `data/`: Directory for the dataset (ignored via `.gitignore`). The project uses the UCI Breast Cancer Wisconsin dataset.
*   `processes/`: Contains the RapidMiner process files (`.rmp`):
    *   `01_wdbc_cross_validation.rmp`: The main pipeline applying SMOTE, Normalization, and 10-fold CV on the models.
    *   `02_wdbc_hyperparameter_tuning.rmp`: The Grid Search processes for optimizing each algorithm.
*   `reports/`: Contains the comprehensive project report in Greek PDF format (`project_report.pdf`). (to be updated)
