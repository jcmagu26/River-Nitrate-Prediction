# 🌊 River Nitrate Prediction Project  

This project investigates factors influencing **nitrate (NO₃) concentration in rivers** using regression modeling, regression trees, and model selection techniques in R.  

We explore how watershed characteristics such as **density, discharge, runoff, precipitation, and area** affect nitrate concentration, and ultimately propose a polynomial regression model that best satisfies statistical assumptions.  

## 📂 Dataset  
- **File used**: `RiverN.csv`  
- **Variables include**:  
  - `NO3` – nitrate concentration (response variable)  
  - `Density` – watershed density  
  - `Discharge` – river discharge  
  - `Runoff` – watershed runoff  
  - `Area` – watershed area  
  - `NPrec` – nitrogen precipitation  
  - `Prec` – precipitation  

## 🛠️ Tools & Libraries  
Implemented in **R** with the following packages:  
- `rpart` – regression trees  
- `car` – multicollinearity diagnostics (VIF)  
- `boot` – cross-validation (`cv.glm`)  

## 📊 Methods  

1. **Exploratory Data Analysis**  
   - Summary statistics, variance, and correlations between predictors.  

2. **Main Effects Model**  
   - Fit a multiple linear regression:  
     NO3 ~ Density + Discharge + Runoff + Area + NPrec + Prec  
   - Found **Density** to be the only significant predictor.  

3. **Regression Tree for Interactions**  
   - Identified potential interaction terms and higher-order effects.  

4. **Model Comparisons**  
   - Considered interaction terms and polynomial terms.  
   - Performed **10-fold cross-validation** to avoid overfitting.  
   - Checked **VIF** for multicollinearity.  
   - Used **ANOVA** to compare nested models.  

5. **Transformations & Model Refinement**  
   - Applied log transformation: ln(NO3).  
   - Compared quadratic and cubic polynomial models.  
   - Final model chosen:  
     ln(NO3) ~ Density + Density^2 + Density^3  

## ✅ Results  

- **Best model**: cubic polynomial of Density predicting log-transformed nitrate.  
- **R²**: high explanatory power with statistically significant terms.  
- **Assumptions**: linearity, equal variance, and normality satisfied after transformation.  
- **Conclusion**: Nitrate concentration is **non-linearly dependent** on watershed density.  

## 📷 Visualizations  

- Regression tree structure  
- Residual vs. fitted plots for diagnostics  
- Histograms of log-transformed NO₃  
- Polynomial regression plots  

## 👥 Contributors  
- Harsha Somaya  
- Jane Maguire  
