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

____

_Minimize the error using gradient descent_

**C parameter: **
Gives a weight for the two kinds of error

> Error = C * Classification error + Margin error

Small C: Large margin and may make classification errors

Large C: Classifies points well and may have a small margin
