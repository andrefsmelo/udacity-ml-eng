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

`from sklearn.linear_model import LinearRegression

model = LinearRegression()

model.fit(x_values, y_values)

print(model.predict(x_value))`

## Multiple linear Regression

y' = w1*x1 + w2*x2 + ... + wn*xn + b

wi = wi - ∂/∂wi(Error) * α , i = {1, 2}

α: learning rate
