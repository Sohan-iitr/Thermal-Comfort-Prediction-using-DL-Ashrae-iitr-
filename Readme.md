# 🌡️ Deep Learning-Based Thermal Comfort Prediction

This project predicts thermal comfort levels in indoor environments using deep learning techniques. By analyzing environmental features such as temperature, humidity, airspeed, and radiant temperature, our model estimates the PMV (Predicted Mean Vote) index—a standard measure of human thermal comfort.

## 📌 Objective

To build an intelligent system that predicts occupants’ thermal comfort levels in real time. The goal is to enhance energy-efficient HVAC control in buildings while maintaining occupant satisfaction.

## 📊 Dataset

We used the **ASHRAE Global Thermal Comfort Database II**, which contains over 100,000 samples collected from field studies worldwide. Each record includes:
- Air temperature (°C)
- Relative humidity (%)
- Air velocity (m/s)
- Mean radiant temperature (°C)
- Subjective thermal comfort vote (PMV)

🗂️ Links:
- [ASHRAE Global Thermal Comfort Database II](https://www.kaggle.com/datasets/claytonmiller/ashrae-global-thermal-comfort-database-ii)

## 🧠 Methodology

1. **Data Preprocessing**
   - Dropped columns with >50% missing values
   - Label encoding for categorical variables
   - Z-score normalization for numerical variables
   - 80-20 train-test split with 5-fold cross-validation

2. **Modeling**
   - Baseline: 1) AdaBoost Regressor (R² ~0.96), 2) DecisionTree (R² ~0.94), 3) ElasticNet (R² ~0.48)
   - Main Model: Dense Feedforward Neural Network (PyTorch)
   - Optimized using **Optuna** (Tree-structured Parzen Estimator)

3. **Hyperparameters Tuned**
   - Number of layers and units
   - Learning rate
   - Dropout rate
   - Batch size

## 📈 Results

- **Final R² Score**: **0.9887** (cross-validated)
- **RMSE**: ~0.3
- **MAE**: ~0.2
- Outperformed recent academic benchmarks (IEEE & SSRN)

## 📦 Requirements

- Python ≥ 3.8
- PyTorch
- Pandas, NumPy
- Scikit-learn
- Optuna
- Matplotlib / Seaborn

Install requirements using:
```bash
pip install -r requirements.txt
