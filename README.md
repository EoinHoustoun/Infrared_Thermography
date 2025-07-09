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
