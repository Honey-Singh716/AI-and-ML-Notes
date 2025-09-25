Great question 👍 You want to **exclude categorical columns** from your dataset (keep only numerical ones).

In **Pandas**, categorical columns usually have `dtype = object` (strings) or sometimes `category`.

---

### ✅ Ways to exclude categorical columns:

#### 1. Using `select_dtypes` (most common)

```python
X_numeric = X_full.select_dtypes(exclude=['object'])
```

* Drops all `object` type columns (strings).
* Keeps integers and floats only.

👉 If some columns are explicitly marked as `category` type:

```python
X_numeric = X_full.select_dtypes(exclude=['object', 'category'])
```

---

#### 2. Keep only numerical dtypes directly

```python
X_numeric = X_full.select_dtypes(include=['int64', 'float64'])
```

* Keeps only integer and float columns.
* Explicitly tells Pandas what you want.

---

#### 3. Drop categorical columns by `df.dtypes`

```python
X_numeric = X_full.drop(columns=X_full.select_dtypes(include=['object']).columns)
```

* First selects object columns,
* Then drops them from the dataset.

---

### ✅ Example

Suppose:

```python
import pandas as pd

data = {
    'LotArea': [8450, 9600, 11250],
    'Street': ['Pave', 'Pave', 'Grvl'],  # categorical
    'OverallQual': [7, 6, 7],
    'Neighborhood': ['CollgCr', 'Veenker', 'CollgCr']  # categorical
}
df = pd.DataFrame(data)
```

* Original:

```python
print(df.dtypes)
```

```
LotArea          int64
Street          object
OverallQual      int64
Neighborhood    object
```

* Keep only numeric:

```python
df_numeric = df.select_dtypes(exclude=['object'])
print(df_numeric)
```

```
   LotArea  OverallQual
0     8450            7
1     9600            6
2    11250            7
```

---

⚖️ **In summary:**

* Use `select_dtypes(exclude=['object', 'category'])` → safest way.
* Or use `include=['int64','float64']` if you only want numerical.

---

👉 Do you want me to also show **how to handle those categorical columns** (instead of dropping), e.g., with **One-Hot Encoding** for ML models?
