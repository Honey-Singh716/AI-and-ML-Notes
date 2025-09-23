1) Definition / derivation (scalar and vector forms)

For a dataset with 
𝑚
m examples, true labels 
𝑦
(
𝑖
)
y
(i)
 and predictions 
𝑦
^
(
𝑖
)
y
^
	​

(i)
:

Mean Squared Error (MSE):

MSE
  
=
  
1
𝑚
∑
𝑖
=
1
𝑚
(
𝑦
^
(
𝑖
)
−
𝑦
(
𝑖
)
)
2
MSE=
m
1
	​

i=1
∑
m
	​

(
y
^
	​

(i)
−y
(i)
)
2

Root Mean Squared Error (RMSE):

RMSE
  
=
  
MSE
  
=
  
1
𝑚
∑
𝑖
=
1
𝑚
(
𝑦
^
(
𝑖
)
−
𝑦
(
𝑖
)
)
2
RMSE=
MSE
	​

=
m
1
	​

i=1
∑
m
	​

(
y
^
	​

(i)
−y
(i)
)
2
	​


If your model is linear with parameters 
𝜃
θ and design matrix 
𝑋
X, predictions are 
𝑦
^
=
𝑋
𝜃
y
^
	​

=Xθ. The vectorized RMSE is:

RMSE
  
=
  
1
𝑚
 
∥
𝑋
𝜃
−
𝑦
∥
2
2
RMSE=
m
1
	​

∥Xθ−y∥
2
2
	​

	​


(where 
∥
𝑣
∥
2
2
=
𝑣
⊤
𝑣
∥v∥
2
2
	​

=v
⊤
v is the sum of squared components of vector 
𝑣
v).

2) Intuition / interpretation

RMSE is the square root of the average squared prediction error.

Units: same as the target 
𝑦
y (e.g., rupees if price is in rupees).

Sensitive to large errors (squares amplify big mistakes).

Lower RMSE = better average predictive accuracy (on the same scale as 
𝑦
y).

3) Quick numeric example (using your house features)

Dataset (4 houses):

Area	Bedrooms	ACs	Price (actual 
𝑦
y)
1200	3	2	5,000,000
1500	4	3	6,500,000
1000	2	1	3,500,000
1800	4	2	7,000,000

Suppose we pick parameter vector (weights):

  
𝜃
=
[
2000
,
  
50000
,
  
10000
]
⊤
θ=[2000,50000,10000]
⊤

(that is: ₹2000 per sq.ft, ₹50,000 per bedroom, ₹10,000 per AC).

Predictions 
𝑦
^
=
𝑋
𝜃
y
^
	​

=Xθ are:

House 1: 
1,200
⋅
2000
+
3
⋅
50000
+
2
⋅
10000
=
2,570,000
1,200⋅2000+3⋅50000+2⋅10000=2,570,000

House 2: 
1,500
⋅
2000
+
4
⋅
50000
+
3
⋅
10000
=
3,230,000
1,500⋅2000+4⋅50000+3⋅10000=3,230,000

House 3: 
1,000
⋅
2000
+
2
⋅
50000
+
1
⋅
10000
=
2,110,000
1,000⋅2000+2⋅50000+1⋅10000=2,110,000

House 4: 
1,800
⋅
2000
+
4
⋅
50000
+
2
⋅
10000
=
3,820,000
1,800⋅2000+4⋅50000+2⋅10000=3,820,000

Errors (prediction − actual):

[
−
2,430,000
,
  
−
3,270,000
,
  
−
1,390,000
,
  
−
3,180,000
]
[−2,430,000,−3,270,000,−1,390,000,−3,180,000]

Square them, take mean, then square-root:

RMSE
≈
2,675,925.07
RMSE≈2,675,925.07

So on average (in RMS sense) predictions are off by about ₹2.68 lakh × 10 (i.e., ~₹26.76 lakh) — or more plainly, ~₹2.68 million — in the units of the price. That shows this 
𝜃
θ is quite poor (just an arbitrary example).

4) Use in training

During training you typically minimize MSE (equivalently RMSE) with respect to 
𝜃
θ.

MSE is convenient because it’s differentiable; gradient-based optimizers use 
∇
𝜃
MSE
∇
θ
	​

MSE to update weights.

RMSE is just the square root of that; minimizing MSE also minimizes RMSE (monotonic relationship), so many algorithms optimize MSE directly.
