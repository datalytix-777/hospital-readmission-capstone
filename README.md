# Hospital Readmission Prediction

This project predicts hospital readmission risk using the UCI "Diabetes 130-US Hospitals" dataset.

It uses diagnostic, demographic, and other key comorbidities associated with readmission and evaluates a Random Forest model against a Majority Class and Logistic Regression model.

## Files
- **notebook/** - Contains the Jupyter notebook used for EDA and modeling
- **model/** - Trained Random Forest Model as '.pkl' file
- **results/** — Visuals of charts and summary metrics
- **requirements.txt** — List of Python dependencies

## Model Performance
**Legend:**  
RF - Random Forest  
LogReg - Logistic Regression  
MajClass - Majority Classifier

- ROC-AUC - (RF): 0.618 / (LogReg): 0.57 / (MajClass):: 0.5
- F1-score - (RF): 0.58 / (LogReg): 0.49 / (MajClass): 0.00
- Recall - (RF): 0.63 / (LogReg): 0.45 / (MajClass): 0.00 
 
 ## Usage
To load the model:
```python
import joblib
model = joblib.load('models/random_forest_readmission_model.pkl')
predictions = model.predict(X_test)
```
 ### Required Features
The model requires these features in this exact order

 - age
 - time_in_hospital 
 - num_lab_procedures
 - num_procedures
 - num_medications
 - number_diagnoses
 - change
 - diabetesMed
 - readmitted
 - race
 - gender
 - diag_1_cat
 - diag_2_cat
 - diag_3_cat

 All features have to be numerically encoded  
 A full list of encoded features is provided in `models/feature_list.pkl`