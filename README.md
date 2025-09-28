# Explainable Techniques II — Sleep and Lifestyle Analysis

## Project Overview
This project explores explainable machine learning techniques using the **Lifestyle and Sleep dataset**.  
The dataset includes demographic, lifestyle, and health-related features, with **Quality of Sleep** as the primary outcome variable.  

The goal of this project is to apply **Partial Dependence Plots (PDP)**, **Individual Conditional Expectation (ICE)**, and **Accumulated Local Effects (ALE)** to better understand how different features influence sleep quality, while also examining correlations between features.

---

## Dataset
The dataset contains 374 rows and 13 columns.  
Key features include:
- Demographics: Gender, Age, Occupation  
- Lifestyle: Sleep Duration, Physical Activity Level, Daily Steps  
- Health: Stress Level, BMI Category, Heart Rate, Blood Pressure  
- Outcomes: Quality of Sleep, Sleep Disorder  

Preprocessing steps:
- Dropped the `Person ID` column.  
- Split `Blood Pressure` into `Systolic_BP` and `Diastolic_BP`.  
- Encoded categorical variables (`Gender`, `Occupation`, `BMI Category`, `Sleep Disorder`) using `LabelEncoder`.  

---

## Methods
1. **Exploratory Analysis**
   - Summary statistics of key features  
   - Distribution plots  
   - Correlation heatmap  
   - Pairwise scatterplots  

2. **Model Training**
   - Random Forest Regressor trained on Quality of Sleep  
   - Evaluation with RMSE and R²  

3. **Explainable Techniques**
   - Partial Dependence Plots (PDP)  
   - Individual Conditional Expectation (ICE)  
   - Accumulated Local Effects (ALE)  

---

## Key Findings
- Sleep Duration and Stress Level are the strongest predictors of Quality of Sleep.  
- Higher sleep duration improves sleep quality, while higher stress decreases it.  
- Physical Activity Level has a smaller but generally positive effect.  
- Correlation analysis revealed strong relationships (e.g., Sleep Duration ↔ Quality of Sleep, Stress Level ↔ Sleep Duration), highlighting the importance of ALE over PDP when features are correlated.  

---

## Requirements
- Python 3.8+  
- Libraries: pandas, numpy, seaborn, matplotlib, scikit-learn, PyALE  

