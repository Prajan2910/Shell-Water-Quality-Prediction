# Shell-Water-Quality-Prediction

Developed by Prajan Kannan

This project aims to predict multiple water quality parameters using machine learning techniques, specifically `MultiOutputRegressor` wrapped around a `RandomForestRegressor`.

## Introduction

Access to clean water is a critical global concern. Accurate prediction of various water quality metrics can aid in the early detection of pollution and ensure timely intervention.

## Procedure:

- Collected and preprocessed real-world water quality datasets  
- Used supervised machine learning for **multi-target regression**  
- Built a pipeline using **MultiOutputRegressor** with **RandomForestRegressor**  
- Evaluated the model using appropriate regression metrics  

## Tools Used:

- **Python 3.12**
- **Pandas**, **NumPy** – Data handling  
- **Scikit-learn** – Machine learning model and evaluation  
- **Matplotlib**, **Seaborn** – Data visualization  
- **Jupyter Notebook** – Interactive experimentation  

## Quality Parameters

The model predicts multiple water quality parameters, including:

- **NH₄** (Ammonium)  
- **BOD₅** (BSK₅ – Biochemical Oxygen Demand)  
- **Colloids**  
- **O₂** (Dissolved Oxygen)  
- **NO₃**, **NO₂**, **SO₄**, **PO₄** (Nitrate, Nitrite, Sulfate, Phosphate)  
- **CL** (Chloride)  

## Model Performance

The model was evaluated using the following metrics:

- **R² Score**
- **Mean Squared Error (MSE)**

Performance was **efficient and feasible across all parameters**, demonstrating the potential of machine learning in environmental monitoring.
