# Fever Prediction with Infrared Thermography

This project uses machine learning to predict oral temperature based on sensor data collected from infrared thermography. The aim is to explore whether non-invasive thermal data can be used to estimate fever status.

<img src="docs/assets/infra.png" width="800"/>

## Overview

This project explores the application of machine learning techniques to predict oral body temperature and fever status using sensor data from thermal infrared images. Inspired by the work of [Wang et al. (2022)](https://www.mdpi.com/1424-8220/22/1/215), which demonstrated the clinical potential of infrared thermography in fever screening, the task involves developing models that can infer oral temperature, both as a continuous variable and a binary fever indicator (≥ 37.5°C), from more accessible, non-invasive temperature readings.

Using the Infrared Thermography Temperature Dataset, which includes environmental and demographic variables alongside thermal readings from various facial regions, the project addresses two core objectives:

**Regression:** Predict the exact oral temperature in (°C) in both Fast Mode (aveOralF) and Monitor Mode (aveOralM).

**Classification:** Predict whether a person has a fever (≥ 37.5°C) based on Fast and Monitor Mode measurements.

This work is motivated by the broader goal of improving non-contact fever screening tools through accurate, interpretable, and computationally efficient machine learning models.

## Notebook

The full Colab notebook is available here:  
👉 [`Infrared_Thermography_Temperature.ipynb`](./Infrared_Thermography_Temperature.ipynb)


## Some Results
<img src="docs/assets/precrec.png" width="700"/>
<img src="docs/assets/rmse.png" width="700"/>
<img src="docs/assets/nn_xgb.png" width="700"/>
<img src="docs/assets/featimp.png" width="700"/>


# 6. CONCLUSION

This project presented a comprehensive machine learning workflow to model oral temperature and fever classification using the Infrared Thermography Temperature Dataset. The work followed a structured pipeline that included dataset exploration, methodological design, model development, validation strategies, and advanced neural network experimentation.

### Summary of Key Steps

- **Dataset Exploration**  
  - Feature correlation and interaction analyses were performed to identify redundancies and gain insight into thermal measurements.
  - Classification targets were identified as imbalanced, guiding the use of F1-score as a key metric during model selection.

- **Methodology Design**  
  - Multiple models were tested for both classification and regression, including logistic regression, decision trees, ensemble models (random forest and XGBoost), and regularized linear models (elastic net and ridge).
  - Monte Carlo Cross-Validation (MC CV) was implemented to ensure robust model evaluation and stability in performance estimates.
  - Evaluation metrics were selected based on the task: F1-score and AUC for classification, and RMSE, MAE, and R² for regression.
  - A custom PyTorch-based Multilayer Perceptron (MLP) was built and integrated into a **nested cross-validation** pipeline with inner-loop hyperparameter tuning and outer-loop generalisation testing.

- **Model Performance Classification**  
  - In the classification task, both Fast Mode and Monitor Mode settings were tested. Models like Logistic Regression, Random Forest, XGBoost, and Elastic Net all showed strong results.  
  - The MLP classifier consistently achieved strong F1-scores, outperforming XGBoost in many folds, particularly in Monitor Mode.
  - **FAST MODE: MLP achieved best mean F1-Score: 0.788 ± 0.165**
  - **MONITOR MODE: MLP achieved best mean F1-Score: 0.855 ± 0.088**


- **Model Performance Regression**  
  - In the regression task, both Fast Mode and Monitor Mode settings were tested. Models like Linear Regression, Random Forest, XGBoost, and Elastic Net all showed strong results.  
  - **The MLP regressor achieved strongest performance in both Fast and Monitor Modes, with nested CV RMSEs of 0.226 (Fast)** and **0.216 (Monitor)**.


- **Reflections**

  - Monitor Mode thermal data returns higher predictive accuracy due to its lower noise and more stable readings.
  - Neural networks perform better with tree-based models and offer flexibility when paired with careful hyperparameter tuning and early stopping.
  - Elastic net regarlisation returned competetive results across both classification and regression.
  - The most influential predictors are all temperature-derived features from specific facial regions.

  Overall, the results demonstrate the feasibility of using thermal imaging data for non-invasive fever screening. MLPs provide a powerful framework for both continuous temperature prediction and binary fever detection. These findings pave the way for future extensions, such as the deployment of lightweight neural models in mobile.



