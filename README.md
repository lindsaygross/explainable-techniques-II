# Explainable Techniques II (PDP, ICE, and ALE) — Sleep and Lifestyle Analysis

## Project Overview
This project applies explainable machine learning techniques to the **Lifestyle and Sleep Health dataset**.  
The dataset includes demographic, lifestyle, and health-related features, with **Quality of Sleep** as the target variable.  

The aim is to use **Partial Dependence Plots (PDP)**, **Individual Conditional Expectation (ICE)**, and **Accumulated Local Effects (ALE)** to understand how lifestyle and health features influence sleep quality, and to examine how correlations between features affect these results.

---

## Dataset

- **Source**: Lifestyle and Sleep Health dataset (374 rows, 13 columns)  
- **Target variable**: *Quality of Sleep*  

**Key features include**:  
- **Demographics**: Gender, Age, Occupation  
- **Lifestyle**: Sleep Duration, Physical Activity Level, Daily Steps  
- **Health**: Stress Level, BMI Category, Heart Rate, Blood Pressure  
- **Outcomes**: Quality of Sleep, Sleep Disorder  

**Preprocessing steps**:  
- Dropped the `Person ID` column (non-informative).  
- Split `Blood Pressure` into `Systolic_BP` and `Diastolic_BP`.  
- Encoded categorical variables (`Gender`, `Occupation`, `BMI Category`, `Sleep Disorder`) with `LabelEncoder`.  

---

## Methods

### Exploratory Data Analysis
- Summary statistics and feature distributions.  
- Correlation heatmap to check for feature dependencies.  
- Pairplots to visualize relationships between key features and the target.  

### Model Training
- **Model**: Random Forest Regressor predicting *Quality of Sleep*  
- **Evaluation metrics**: RMSE and R²  

### Explainable Techniques
- **PDP**: Shows the average marginal effect of a feature on predictions.  
- **ICE**: Reveals how predictions change for individual instances.  
- **ALE**: Accounts for feature correlations and shows local effects.  

---

## Findings
- **Sleep Duration**: Strong positive effect on predicted sleep quality, especially beyond ~7.5 hours.  
- **Stress Level**: Clear negative effect on predictions, particularly above level 5.  
- **Physical Activity Level**: Very limited effect; model predictions remain mostly flat.  
- **Correlation impact**: Sleep Duration and Quality of Sleep are highly correlated (~0.88). This means PDP may exaggerate the effect of sleep, while ALE adjusts for this correlation.  
- **PDP vs ALE**: PDP showed sharper trends, while ALE smoothed effects into more realistic patterns.  
- **ICE insights**: Individuals differ in how much sleep or stress influences their outcomes, highlighting heterogeneity not visible in PDP or ALE.  

---

## Conclusion
By combining PDP, ICE, and ALE, we build a fuller understanding of model behavior:  
- **PDP** highlights global patterns.  
- **ICE** shows variation across individuals.  
- **ALE** reduces bias from correlated features, making it more reliable when dependencies exist.  

Together, these tools provide complementary perspectives that lead to more trustworthy and interpretable insights into feature importance.

---

## Requirements
- Python 3.8+  
- Libraries: pandas, numpy, seaborn, matplotlib, scikit-learn, PyALE
