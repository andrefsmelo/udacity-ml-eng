# Support Vector Machine

Maximizing the margin: include the margin error to the total error

> Error = Classification error + Margin error

_Classification error punishes the points inside the margin_

**Perceptron Algorithm:** Minimizes misclassified points error weighted by the absolute distance of the boundary line

## Classification error

On Support Vector Machine (SVM) we add a extra area on the perceptron algorithm for extra punish values next the boundary line

![margin](http://www.saedsayad.com/images/SVM_2.png)

## Margin error

Margin = 2 / |W|

Error = |W|² (that grows inversely proportional to the margin) - equal L2

|W|² = (w1²+w2²)

Large margin -> Small error

Small margin -> Large error

![margin1](https://d17h27t6h515a5.cloudfront.net/topher/2018/January/5a52bf15_margin-geometry-images.001/margin-geometry-images.001.jpeg)
![margin2](https://d17h27t6h515a5.cloudfront.net/topher/2018/January/5a52bf1e_margin-geometry-images.002/margin-geometry-images.002.jpeg)
![margin3](https://d17h27t6h515a5.cloudfront.net/topher/2018/January/5a52bf2b_margin-geometry-images.003/margin-geometry-images.003.jpeg)
![margin4](https://d17h27t6h515a5.cloudfront.net/topher/2018/January/5a52bf35_margin-geometry-images.004/margin-geometry-images.004.jpeg)
![margin5](https://d17h27t6h515a5.cloudfront.net/topher/2018/January/5a52bf47_margin-geometry-images.005/margin-geometry-images.005.jpeg)
![margin6](https://d17h27t6h515a5.cloudfront.net/topher/2018/January/5a52bf73_margin-geometry-images.008/margin-geometry-images.008.jpeg)



## Minimize the error using gradient descent

**C parameter:** Gives a weight for the two kinds of error

> Error = C * Classification error + Margin error

Small C: Large margin and may make classification errors

Large C: Classifies points well and may have a small margin

## Polinomial Kernel

**Kernel trick:** When boundary line can't solve the problem, We add a extra dimension that multiples the values in others dimensions. We split the data in the new dimension with a n-1 dimension boundary hyperplane and turn back to the original number of dimensions.


                    2 dimensions ---> 5 dimensions

                          (x, y) ---> (x, y, x², xy, y²) -> 2 degree

                          (2, 3) ---> (2, 3, 4, 6, 9)

    Degree 2 polynomial boundary <--- 4-dimensional boundary hyperplane

                   Linear kernel ---> Polynomial kernel


## Radial Basis Function Kernel

We draw a mountain range where the high points correspond to the target variable.
Like the Polynomial kernel, We split the mountain range by height and turn back to the original line with a polynomial boundary

To draw the mountain range we create mountains above the points and multiplies with positive or negatives values that correspond to the hyperplane that split the values in n-dimensional plane

** Parameter γ: ** Correspond to the height of the mountain and consequently your width

High γ -> Overfit

γ = 1 / 2σ² (σ: standard deviation)

```python
from sklearn.svm import SVC
model = SVC(kernel='rbf', gamma=10, C=10)
model.fit(x_values, y_values)
y_pred = model.predict(X)
acc = accuracy_score(y, y_pred)
```
hyperparameters:
- C: C parameter
- kernel: 'linear', 'poly' and 'rbf'
- degree: max degree
- gamma : from rbf kernel
