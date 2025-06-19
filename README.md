# Shell-Water-Quality-Prediction

**Developed by Prajan Kannan**

This project focuses on predicting and classifying water quality using machine learning techniques. It integrates environmental data analysis with a fully-fledged machine learning pipeline to compute and classify Water Quality Index (WQI) and its associated parameters.

## Introduction

Access to clean water is a vital global need. Predicting water quality metrics allows for early detection of contaminants and aids policymakers and researchers in proactive environmental management.

## Project Workflow

- Uploaded real-world water quality datasets  
- Performed a complete preprocessing and feature engineering pipeline  
- Calculated WQI from raw parameters using standard limits and weightings  
- Classified WQI into qualitative categories (WQC)  
- Trained an XGBoost classifier with hyperparameter tuning  
- Visualized predictions and interpreted feature impact using SHAP  

## Features and Updates

### Data Handling and Upload

- Upload the file "Water Quality Prediction Dataset.csv"

### Full Preprocessing Pipeline

- Parsed dates and extracted `month` and `year`
- Imputed missing values using `SimpleImputer`
- Corrected skewed features using `np.log1p`
- Scaled all features using `StandardScaler`

### WQI Calculation and Classification

- Computed Water Quality Index (WQI) using weighted parameter scores
- Used parameter-specific standard (`S_i`) and ideal (`V_i`) limits
- Classified WQI into five categories: Excellent, Good, Poor, Very Poor, Unsuitable

### Label Encoding and Data Splitting

- Encoded WQC string labels into integers using `LabelEncoder`
- Applied stratified train-test split to preserve class proportions

### Model Training

- Used `XGBClassifier` with objective `'multi:softprob'`
- Tuned hyperparameters using `GridSearchCV` with cross-validation

### Evaluation and Visualization

- Reported `accuracy score` and `classification report`
- Visualized class-level performance using a `confusion matrix` (Seaborn heatmap)
- Interpreted feature impact using SHAP with beeswarm plots for individual classes

## Quality Parameters Predicted

The model processes and predicts the following water quality indicators:

- **NH₄** (Ammonium)  
- **BOD₅** (BSK₅ – Biochemical Oxygen Demand)  
- **Suspended Solids (Colloids)**  
- **O₂** (Dissolved Oxygen)  
- **NO₃**, **NO₂**, **SO₄**, **PO₄** (Nitrate, Nitrite, Sulfate, Phosphate)  
- **CL** (Chloride)  

## Tools and Libraries Used

- **Python 3.12**  
- **Pandas**, **NumPy** – Data manipulation  
- **Scikit-learn** – Machine learning models and preprocessing  
- **XGBoost** – Gradient boosting model  
- **Matplotlib**, **Seaborn** – Visualization  
- **SHAP** – Model explainability  
- **Jupyter Notebook / Google Colab** – Execution environment

## Model Performance

The model achieved strong classification accuracy across categories and demonstrated interpretability using SHAP. It is deployable for practical monitoring systems and scientific reporting.
