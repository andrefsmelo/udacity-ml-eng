# Linear Regression

## Error types
Graphically is based on the distance between the points and the regression line.

**Mean Absolute Error** = 1/m * Σ |y - ŷ|

**Mean Squared Error** = 1/m * Σ (y - ŷ)²

## Gradient descent
Iterative optimization algorithm to minimize the error on a linear regression.

y' = w1*x + w2

wi = wi - ∂/∂wi(Error) * α , i = {1, 2}

α: learning rate

**Mean Squared Error**

w1 = w1 + (y - ŷ) \* x \* α

w2 = w2 + (y - ŷ) \* α

_remember the chain rule: ( f( g(X) )' = f'( g(x) ) \* g'(x)_

**Mean Absolute Error**

w1 = w1 + x * α

w2 = w2 + α

## Sklearn linear regression

```
from sklearn.linear_model import LinearRegression

model = LinearRegression()

model.fit(x_values, y_values)

print(model.predict(x_value))
```

## Multiple linear Regression

y' = w0 + w1*x1 + w2*x2 + ... + wn*xn

wi = wi - ∂/∂wi(Error) * α , i = {0, 1, ... , n}

α: learning rate

## Other forms to minimize the error

> First order condition

> Matrix solution

## Model characteristics

- Work better with linear data

- Sensitive to outliers

## Polynomial regression
The relationship between the independent variable x and the dependent variable y is modelled as an n degree polynomial in x (nonlinear).

## Regularization
Avoid overfitting in polynomial regression increasing the error with the number of estimators.

### L1

y = 2\*x1³ - 2\*x1²\*x2 - 4\*x2³ + 3\*x1² + 6\*x1\*x2 + 4\*x² + 5 = 0

Error = |2| + |-2| + |-4| + |3| + |6| + |4| = 21

### L2

y = 2\*x1³ - 2\*x1²\*x2 - 4\*x2³ + 3\*x1² + 6\*x1\*x2 + 4\*x² + 5 = 0

Error = (2)² + (-2)² + (-4)² + (3)² + (6)² + (4)² = 85

- parameter λ : mutiples the error (weight)
- L1 is computationally inefficient (unless data is sparse)
- L1 helps in features selection
