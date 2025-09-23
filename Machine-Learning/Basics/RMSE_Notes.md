# Root Mean Squared Error (RMSE) in Machine Learning

## 📘 Definition
Root Mean Squared Error (RMSE) is a common metric used to measure the difference between values predicted by a model and the values actually observed.

It is defined as:

\[
\text{RMSE} = \sqrt{\frac{1}{m} \sum_{i=1}^m (\hat{y}^{(i)} - y^{(i)})^2}
\]

Where:
- **m** = number of instances in the dataset
- **\(y^{(i)}\)** = actual (true) value for instance *i*
- **\(\hat{y}^{(i)}\)** = predicted value for instance *i*

---

## 🔹 Vectorized Form
If we use matrix notation:
- **X** = design matrix (features)
- **θ** = parameter vector (weights)
- **y** = target vector (labels)
- **\(\hat{y} = Xθ\)** = predictions

Then RMSE can be written as:

\[
\text{RMSE} = \sqrt{\frac{1}{m} \|Xθ - y\|^2}
\]

---

## 📊 Intuition
- RMSE measures the **average magnitude of the errors**.
- It gives **higher weight to larger errors** (because of squaring).
- Units of RMSE are the same as the target variable.

---

## ✅ Advantages
- Easy to interpret (same units as output variable).
- Penalizes large errors strongly, which is useful in sensitive applications.

## ⚠️ Disadvantages
- Sensitive to outliers (one large error can significantly affect RMSE).

---

## 🔑 When to Use
- Regression problems where large errors are particularly undesirable.
- Model evaluation and comparison (lower RMSE = better fit).

---

## 🏠 Example (House Price Prediction)
Suppose we predict house prices and get:

- Actual values: [5000000, 6500000, 3500000, 7000000]  
- Predicted values: [2570000, 3230000, 2110000, 3820000]  

Errors = [-2430000, -3270000, -1390000, -3180000]  
Squared errors = [5.9e12, 1.07e13, 1.93e12, 1.01e13]  

MSE = (sum of squared errors) / 4  
RMSE = sqrt(MSE) ≈ **2,675,925**  

So, the model’s predictions are off by about 2.68 million on average.

---

## 📌 Summary
- RMSE = square root of average squared error.  
- Lower RMSE means better performance.  
- Always compare RMSE **on the same dataset** for fair evaluation.

