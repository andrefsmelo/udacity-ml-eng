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
