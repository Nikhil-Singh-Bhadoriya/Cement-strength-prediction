# Cement Strength Prediction Project

## Overview
This project focuses on predicting **concrete compressive strength** using machine learning algorithms. The project explores various regression models to determine which performs best for this prediction task.

---

## Dataset

### Source
`cement_data.csv` - Contains 1030 samples with 9 features

### Variables

| Variable | Type | Unit | Description |
|----------|------|------|-------------|
| Cement (Component 1) | Quantitative | kg in a m³ mixture | Input Variable |
| Blast Furnace Slag (Component 2) | Quantitative | kg in a m³ mixture | Input Variable |
| Fly Ash (Component 3) | Quantitative | kg in a m³ mixture | Input Variable |
| Water (Component 4) | Quantitative | kg in a m³ mixture | Input Variable |
| Superplasticizer (Component 5) | Quantitative | kg in a m³ mixture | Input Variable |
| Coarse Aggregate (Component 6) | Quantitative | kg in a m³ mixture | Input Variable |
| Fine Aggregate (Component 7) | Quantitative | kg in a m³ mixture | Input Variable |
| Age | Quantitative | Day (1-365) | Input Variable |
| **Concrete Compressive Strength** | Quantitative | **MPa** | **Output Variable (Target)** |

---

## Project Notebooks

### 1. **EDA.ipynb** - Exploratory Data Analysis & Model Comparison
Main analysis and model evaluation notebook.

**Key Steps:**
- Data loading and preprocessing
- Train-test split (80-20)
- Data preprocessing pipeline (KNNImputer + StandardScaler)
- Model training and evaluation

**Models Evaluated:**

| Model | Mean Squared Error | R² Score |
|-------|-------------------|----------|
| Linear Regression | 113.34 | 0.59 |
| Ridge Regression | 112.92 | 0.60 |
| Lasso Regression | 116.17 | 0.58 |
| Random Forest Regression | 53.09 | 0.81 |
| **Gradient Boosting Regression** | **30.28** | **0.89** |

**Best Model:** Gradient Boosting Regression with the lowest MSE (30.28) and highest R² score (0.89)

---

### 2. **cement_strength_prediction.ipynb** - Basic ML Pipeline
Traditional machine learning workflow with multiple model implementations.

**Features:**
- Data exploration (info, head, shape)
- Data quality checks (missing values, duplicates)
- Individual model training:
  - Linear Regression
  - Ridge Regression
  - Lasso Regression
  - Random Forest Regressor
  - Gradient Boosting Regressor
- Model evaluation using Mean Squared Error and R² Score

---

### 3. **cementStrength.ipynb** - Advanced Data Transformation
Focus on data preprocessing and distribution analysis.

**Features:**
- Statistical analysis (describe, info)
- Distribution plots for all features
- **Log transformation** of features (with +1 adjustment to avoid log(0))
- Outlier detection using box plots
- Visual analysis of data before and after transformation

**Data Observations:**
- No missing values detected
- Log transformation applied to normalize feature distributions
- Outliers identified using box plots for further investigation

---

## Project Structure

```
cement-strength-prediction-project/
├── notebook/
│   ├── EDA.ipynb                           # Main analysis & model comparison
│   ├── cement_strength_prediction.ipynb    # Basic ML pipeline
│   ├── cementStrength.ipynb                # Advanced data transformation
│   ├── cement_data.csv                     # Dataset
│   └── README.md                           # This file
```

---

## Key Findings

### Model Performance Summary
- **Best Overall Model:** Gradient Boosting Regression
  - MSE: 30.28
  - R² Score: 0.89
  - Explains 89% of the variance in concrete compressive strength

### Data Insights
- Dataset is clean with no missing values
- Features follow different distributions
- Log transformation helps normalize non-normal distributions
- Outliers present but minimal impact after scaling

---

## Technologies Used

- **Python 3.x**
- **Libraries:**
  - `pandas` - Data manipulation
  - `scikit-learn` - Machine learning models and preprocessing
  - `matplotlib` - Plotting
  - `seaborn` - Statistical visualization
  - `numpy` - Numerical computing

---

## How to Use

1. **Load the notebooks in Jupyter/JupyterLab:**
   ```bash
   jupyter notebook EDA.ipynb
   ```

2. **Run cells sequentially** to:
   - Load and explore the data
   - Preprocess the features
   - Train and evaluate models
   - Analyze results

3. **Best practices:**
   - Start with `cementStrength.ipynb` for data understanding
   - Use `EDA.ipynb` for model comparison and selection
   - Reference `cement_strength_prediction.ipynb` for basic ML workflow

