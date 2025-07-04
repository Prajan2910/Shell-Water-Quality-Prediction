# Shell-Water-Quality-Prediction

**Developed by Prajan Kannan**

## Project Overview

This project implements a machine learning pipeline to predict the concentrations of major water pollutants (O₂, NO₃, NO₂, SO₄, PO₄, CL), compute the Water Quality Index (WQI), classify the water quality into categories, and evaluate the model’s prediction performance.

---

## Workflow Steps

### 1. Data Loading and Preprocessing

- Parse dates, extract year and month
- Sort by `id` and `date`
- Missing values of the rows are replaced with the mean of their respective columns

### 2. Water Quality Index (WQI)

- Compute WQI using a weighted quality index formula
- Classify WQI into qualitative classes:
  - Excellent (≤25)
  - Good (26–50)
  - Poor (51–75)
  - Not Suitable (>75)

### 3. Feature and Target Preparation

- One-hot encode station IDs
- Train-test split
- Apply `StandardScaler` to input features

### 4. Model Training

- Train a multi-output random forest regressor (`RandomForestRegressor` inside `MultiOutputRegressor`)

### 5. Regression Evaluation

- Print Mean Squared Error (MSE) and R² Score for each pollutant

### 6. WQI Classification Evaluation

- Predict WQI from the predicted pollutant concentrations
- Compare actual vs predicted WQI classes
- Display confusion matrix and compute classification accuracy

### 7. Random Sample Evaluation

- Randomly select `n` samples from the dataset
- Compare actual vs predicted pollutant levels and WQI classifications

### 8. Save Model and Preprocessors

- Save trained model
- Save `StandardScaler`
- Save ordered list of training feature columns

---

## Output Files

- `multi_rf_pollutant_model.pkl`: Trained multi-output model
- `feature_scaler.pkl`: `StandardScaler` used for input preprocessing
- `model_features.pkl`: Ordered list of feature columns used in training

---

## How to Use

1. Clone this repository.
2. Place the dataset file `Water Quality Prediction Dataset.csv` in the working directory.
3. Run the script `main.py` or open the notebook `Water_Quality_Predictor.ipynb`.
4. The output will include:
   - Pollutant-wise regression metrics (MSE, R²)
   - Confusion matrix for WQI classification
   - Accuracy of WQI prediction
   - Random sample evaluation output
5. Load the saved models using `joblib.load(...)` for predictions on new input data.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
