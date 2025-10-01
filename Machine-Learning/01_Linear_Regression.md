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




1. Slope of Regression Line

In simple linear regression (one predictor 
𝑋
X, one outcome 
𝑌
Y):

𝑌
^
=
𝛽
0
+
𝛽
1
𝑋
Y
^
=β
0
	​

+β
1
	​

X

where

𝛽
1
β
1
	​

 = slope

𝛽
0
β
0
	​

 = intercept

The slope formula is:

𝛽
1
=
𝑟
⋅
𝑠
𝑌
𝑠
𝑋
β
1
	​

=r⋅
s
X
	​

s
Y
	​

	​


where

𝑟
r = correlation coefficient between 
𝑋
X and 
𝑌
Y

𝑠
𝑌
s
Y
	​

 = standard deviation of 
𝑌
Y

𝑠
𝑋
s
X
	​

 = standard deviation of 
𝑋
X

2. Relationship Between Correlation and Slope

Directly proportional: If correlation increases (positive or negative), slope also increases in magnitude.

Sign is the same:

If 
𝑟
>
0
r>0, slope is positive → upward line.

If 
𝑟
<
0
r<0, slope is negative → downward line.

If 
𝑟
=
0
r=0: slope = 0 → flat line (no linear relationship).

If 
∣
𝑟
∣
=
1
∣r∣=1: slope perfectly predicts 
𝑌
Y from 
𝑋
X (all points on a straight line).

3. Intuition

Correlation tells you about the strength & direction of the linear relationship.

Slope tells you about the rate of change in 
𝑌
Y per unit of 
𝑋
X.

Correlation normalizes slope (by dividing out the scales of 
𝑋
X and 
𝑌
Y).
That’s why correlation is unitless, while slope depends on the measurement units.
