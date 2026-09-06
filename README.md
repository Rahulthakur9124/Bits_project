# Bits_project
# 🌍 Earthquake Impact & Tsunami Analysis

An end-to-end data analysis and machine learning project analyzing **earthquake magnitude, depth, geographic location, tsunami occurrence, alert severity, and earthquake impact** using Python and Scikit-learn.

## 📌 Overview

This project analyzes **782 earthquake events** to identify patterns in earthquake characteristics and build machine learning models for:

* Predicting **tsunami occurrence**
* Estimating **tsunami probability**
* Predicting **CDI (Community Determined Intensity)**
* Predicting **MMI (Modified Mercalli Intensity)**
* Understanding relationships between earthquake characteristics and alert severity
* Visualizing earthquake patterns geographically and statistically

## 🛠️ Technologies Used

* **Python**
* **Pandas & NumPy** — Data cleaning and analysis
* **Scikit-learn** — Machine learning
* **Matplotlib & Seaborn** — Statistical visualization
* **Plotly** — Interactive visualizations
* **Random Forest** — Classification and regression

## 🔍 Data Analysis

The dataset was cleaned and transformed before analysis, including:

* Handling missing categorical values
* Filling missing depth values using the mean
* Converting tsunami indicators into numerical values
* Extracting **year and month** from earthquake dates
* Analyzing earthquake frequency over time
* Comparing magnitude across continents
* Studying earthquake **alert levels** and their associated magnitudes

### Alert-Level Analysis

The dataset contained the following alert categories:

| Alert  | Earthquakes | Average Magnitude |
| ------ | ----------: | ----------------: |
| Green  |         325 |              6.86 |
| None   |         367 |              6.98 |
| Yellow |          56 |              7.06 |
| Orange |          22 |              7.12 |
| Red    |          12 |              7.28 |

The analysis shows that earthquakes with higher alert levels generally had higher average magnitudes.

## 🤖 Tsunami Prediction

A **Random Forest Classifier** was trained to predict whether an earthquake was associated with a tsunami.

### Features

* Magnitude
* Depth
* Latitude
* Longitude
* Significance (`sig`)

### Model Configuration

```python
RandomForestClassifier(
    n_estimators=100,
    random_state=42
)
```

The data was split into **80% training and 20% testing**, with feature scaling applied using `StandardScaler`.

### Results

**Accuracy: 66%**

| Class      | Precision | Recall | F1-Score |
| ---------- | --------: | -----: | -------: |
| No Tsunami |      0.69 |   0.74 |     0.71 |
| Tsunami    |      0.60 |   0.55 |     0.57 |

### Feature Importance

The most important features identified by the Random Forest model were:

| Feature      | Importance |
| ------------ | ---------: |
| Longitude    |  **32.4%** |
| Latitude     |  **25.2%** |
| Depth        |  **17.3%** |
| Significance |  **16.1%** |
| Magnitude    |   **8.9%** |

Longitude and latitude were the strongest predictors in the trained model.

## 📊 Tsunami Probability Visualization

The trained classifier was also used to generate **tsunami probabilities** for earthquake events.

Interactive Plotly visualizations were created to explore:

* Earthquake locations
* Magnitude
* Depth
* Tsunami probability
* Geographic distribution

A magnitude-vs-depth visualization was also created using tsunami probability as an additional dimension.

## 📈 Earthquake Impact Prediction

Random Forest regression models were developed to estimate two earthquake impact measures:

* **CDI**
* **MMI**

### Results

| Target | R² Score |  MSE |
| ------ | -------: | ---: |
| CDI    | **0.74** | 2.84 |
| MMI    | **0.48** | 1.06 |

The CDI model showed stronger predictive performance than the MMI model.

## 📊 Visualizations

The project includes visualizations for:

* Earthquake frequency by year
* Average magnitude by continent
* Alert-level distribution
* Magnitude vs. depth
* Feature importance
* Tsunami probability
* Global earthquake locations
* Predicted CDI vs. MMI

Interactive visualizations were created using **Plotly**.

## 🔄 Project Workflow

```text
Raw Earthquake Data
        ↓
Data Cleaning & Preprocessing
        ↓
Exploratory Data Analysis
        ↓
Feature Engineering
        ↓
 ┌───────────────┬────────────────┐
 │               │                │
 ▼               ▼                ▼
Tsunami       CDI Prediction   MMI Prediction
Classification   Regression      Regression
 │               │                │
 ▼               ▼                ▼
Random Forest  Random Forest    Random Forest
 │
 ▼
Tsunami Probability
        ↓
Interactive Visualizations
```

## 📁 Project Structure

```text
Earthquake-Impact-Tsunami-Analysis/
│
├── Impact_Metrics_IIT(BHU).ipynb
├── earthquake_data.csv
├── cleaned_earthquake_data.csv
└── README.md
```

> Update the filenames above according to the files included in your GitHub repository.

## 🎯 Key Takeaways

* Analyzed **782 earthquake events** through exploratory and statistical analysis.
* Built a Random Forest model achieving **66% accuracy** for tsunami classification.
* Geographic coordinates were the strongest predictors of tsunami occurrence in the trained model.
* CDI prediction achieved **R² = 0.74**, while MMI prediction achieved **R² = 0.48**.
* Used interactive geographic and statistical visualizations to interpret model outputs.

## 👨‍💻 Author

**Rahul Thakur**
B.Tech Mathematics & Computing
Delhi Technological University

