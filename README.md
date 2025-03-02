# Electricity Demand Prediction  

This project predicts electricity demand using **weather data and historical electricity consumption patterns**. A **regression model** was trained and evaluated, achieving an **R² score of 94%**, indicating high accuracy in predictions.  

---

## Table of Contents  
- [1. Requirements](#1-requirements)  
- [2. Installation](#2-installation)  
- [3. Data Loading and Integration](#3-data-loading-and-integration)  
- [4. Data Preprocessing](#4-data-preprocessing)  
- [5. Exploratory Data Analysis (EDA)](#5-exploratory-data-analysis-eda)  
- [6. Outlier Detection and Handling](#6-outlier-detection-and-handling)  
- [7. Regression Modeling](#7-regression-modeling)  
- [8. Model Evaluation](#8-model-evaluation)  
- [9. Usage](#9-usage)  
- [10. Next Steps](#10-next-steps)  
- [11. Author](#11-author)  

---

## 1. Requirements  
Ensure you have the following dependencies installed:  

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```


---

## 2. Installation  
Clone this repository and navigate to the project directory:  

```bash
git clone https://github.com/yourusername/electricity-demand-prediction.git
cd electricity-demand-prediction
```

---

## 3. Data Loading and Integration  
The project uses two datasets:  
✅ **Electricity Demand Data** (`JSON` format)  
✅ **Weather Data** (`CSV` format)  

Both datasets were **merged** based on a common `Timestamp`. The relevant features were extracted and transformed for further analysis.  

---

## 4. Data Preprocessing  
To ensure data consistency and accuracy, the following steps were applied:  

✅ Converted `Timestamp` to **datetime format**  
✅ Standardized column names for uniformity  
✅ Handled **missing values**:  
   - Columns with **>20% missing data** were dropped  
   - Forward-fill (`ffill`) was used for minor missing values  
✅ Created **time-based features**:  
   - `hour`, `day_of_week`, `month`, `year`, `is_weekend`  
✅ One-hot encoding for **categorical variables** (e.g., Province)  

---

## 5. Exploratory Data Analysis (EDA)  
EDA was conducted to understand patterns in electricity consumption:  

✅ **Trend Analysis**:  
   - Electricity demand over time  
   - Demand variations by **province**, **weekdays vs. weekends**, and **seasons**  
✅ **Correlation Analysis**:  
   - Checked relationships between **temperature, time features, and demand**  
✅ **Visualizations**:  
   - **Heatmaps** to identify correlations  
   - **Boxplots** to detect anomalies  
   - **Time series plots** for demand trends  

---

## 6. Outlier Detection and Handling  
Outliers can distort model accuracy, so the following techniques were applied:  

✅ **Interquartile Range (IQR) method** to detect outliers  
✅ **Capping at the 1st and 99th percentiles** to limit extreme values  

---

## 7. Regression Modeling  
The goal was to build a regression model that predicts electricity demand.  

✅ **Selected Features**:  
   - `Temperature`, `hour`, `day_of_week`, `month`, `is_weekend`, `Province` (one-hot encoded)  
✅ **Train-Test Split**:  
   - **80% training**  
   - **20% testing**  
✅ **Models Trained**:  
   - **Linear Regression**  
   - **Random Forest Regressor**  
   - **Gradient Boosting Regressor**  
✅ **Hyperparameter Tuning** using GridSearchCV  

---

## 8. Model Evaluation  
The best-performing model was evaluated using the following metrics:  

| Metric          | Score  |
|----------------|--------|
| **R² Score**   | **0.94 (94%)** |
| **MAE**        | Low    |
| **MSE**        | Low    |
| **RMSE**       | Low    |

✅ **Final Model Accuracy: 94% (R² Score = 0.94)**  
✅ **Predictions closely match actual electricity demand**  

---

## 9. Usage  
To use the model for predictions, run the following script:  

```bash
python predict.py --input data/sample_input.csv
```

Example usage in Python:  

```python
from model import load_model, predict_demand

model = load_model("best_model.pkl")
predictions = predict_demand(model, "data/sample_input.csv")
print(predictions)
```

---

## 10. Next Steps  
🔹 **Deploy the model** (API or dashboard for real-time predictions)  
🔹 **Improve predictions** using advanced techniques (LSTM, Prophet for time series forecasting)  
🔹 **Incorporate real-time weather forecasts** to enhance accuracy  

---

## 11. Author  
📌 **Saif Ullah**  
📌 **su3561116@gmail.com**  
📌 **https://github.com/saif55045**  

