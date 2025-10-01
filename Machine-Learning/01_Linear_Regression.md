# 📘 Linear Regression

## 🔍 What is Linear Regression?
Short explanation...

## 🧠 Assumptions
- Linearity
- Homoscedasticity
- No multicollinearity

## 📈 Dataset Used
- Dataset: Kaggle [link here]
- Description: Predict housing prices...

## 📊 Exploratory Data Analysis (EDA)
Use plots and `seaborn`, `matplotlib`.

## 🧮 Model Training
```python
from sklearn.linear_model import LinearRegression
model = LinearRegression()
model.fit(X_train, y_train)

# Relationship Between Correlation and Slope in Regression

## 1. Slope of Regression Line
In **simple linear regression** (one predictor \(X\), one outcome \(Y\)):

\[
\hat{Y} = \beta_0 + \beta_1 X
\]

where:
- \(\beta_1\) = slope  
- \(\beta_0\) = intercept  

The slope formula is:

\[
\beta_1 = r \cdot \frac{s_Y}{s_X}
\]

where:
- \(r\) = correlation coefficient between \(X\) and \(Y\)  
- \(s_Y\) = standard deviation of \(Y\)  
- \(s_X\) = standard deviation of \(X\)  

---

## 2. Relationship Between Correlation and Slope
- **Directly proportional**: If correlation increases (positive or negative), slope also increases in magnitude.  
- **Sign is the same**:
  - If \(r > 0\): slope is positive → upward line  
  - If \(r < 0\): slope is negative → downward line  
- **If \(r = 0\):** slope = 0 → flat line (no linear relationship)  
- **If \(|r| = 1\):** slope perfectly predicts \(Y\) from \(X\) (all points lie exactly on a straight line).  

---

## 3. Intuition
- **Correlation** tells you about the *strength & direction* of the linear relationship.  
- **Slope** tells you about the *rate of change* in \(Y\) per unit of \(X\).  

👉 Correlation **normalizes slope** (by dividing out the scales of \(X\) and \(Y\)).  
- That’s why correlation is **unitless**, while slope depends on the measurement units.  

