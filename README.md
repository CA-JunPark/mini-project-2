# Mini Project II – Heart Disease Prediction

## Problem Description & Motivation
The goal of this project is to build and analyze a machine learning pipeline that predicts whether a patient has heart disease based on clinical and diagnostic features. 

---

## Dataset Description

This data set dates from 1988 and consists of four databases: Cleveland, Hungary, Switzerland, and Long Beach V. It contains 76 attributes, including the predicted attribute, but all published experiments refer to using a subset of 14 of them. The "target" field refers to the presence of heart disease in the patient. It is integer valued 0 = no disease and 1 = disease.

**Source:** Heart Disease Dataset  
**Samples:** 303 patients  
**Task:** Binary classification  

### Original Features (14)
- `age`: Age of the patient  
- `sex`: Sex (0 = female, 1 = male)  
- `cp`: Chest pain type  
- `trestbps`: Resting blood pressure  
- `chol`: Serum cholesterol  
- `fbs`: Fasting blood sugar  
- `restecg`: Resting ECG results  
- `thalach`: Maximum heart rate achieved  
- `exang`: Exercise-induced angina  
- `oldpeak`: ST depression  
- `slope`: Slope of peak exercise ST segment  
- `ca`: Number of major vessels  
- `thal`: Thalassemia  

### Renamed Features
For clarity and interpretability, several features were renamed during preprocessing:

| Original Name | Renamed Feature |
|--------------|----------------|
| `age` | `age` |
| `sex` | `sex` |
| `cp` | `chest_pain_type` |
| `trestbps` | `resting_blood_pressure` |
| `chol` | `cholesterol` |
| `fbs` | `fasting_blood_sugar` |
| `restecg` | `resting_ecg` |
| `thalach` | `max_heart_rate` |
| `exang` | `exercise_induced_angina` |
| `oldpeak` | `st_depression` |
| `slope` | `st_slope` |
| `ca` | `num_major_vessels` |
| `thal` | `thalassemia` |
| `target` | `heart_disease` |

After one-hot encoding categorical variables, the final dataset expanded from **14 to 23 features**, improving model expressiveness.

### Target Variable
- `heart_disease`  
  - `0` = No heart disease  
  - `1` = Heart disease  

The dataset is roughly balanced, with approximately **54% diseased** and **46% healthy** patients, reducing the need for aggressive resampling techniques.

Based on exploratory data analysis, the features were grouped by their observed predictive strength.

### Strong Predictive Features
These features show clear separation between patients with and without heart disease:
- `max_heart_rate`  
- `st_depression`  
- `chest_pain_type`  
- `num_major_vessels`  
- `exercise_induced_angina`

### Moderate Predictive Features
These features show noticeable trends but with overlap between classes:
- `st_slope`
- `thalassemia`

### Weak Predictive Features
These features show similar distributions across classes and limited standalone predictive power:
- `cholesterol`
- `resting_blood_pressure`
- `fasting_blood_sugar`
- `resting_ecg`
- `sex`
- `age`

These findings informed feature importance analysis and model interpretation rather than aggressive feature removal.

### Setup instructions

    git clone <this repo>
    cd mini-project-2
    python -m venv .venv
    source .venv/Scripts/activate or .venv/bin/activate
    pip install -r requirements.txt

run .ipynb files with a created python environment.

### Result summary with Key Metrics

### Team Member Contributions
Bryan Rachmat: 01_data_exploration.ipynb

Jun Park: 02_modeling.ipynb

Together: Learning Hub Report
    



