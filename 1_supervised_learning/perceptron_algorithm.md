# Perceptron Algorithm

## Classification problem
Need to return a specific answer
- True or False
- Multi classification

### Boundary line
W*x + b = 0

W = (w1, w2, ...)

x = (x1, x2, ...)

If W*x + b >= 0 -> ŷ = 1

If W*x + b < 0 -> ŷ = 0

Separates the occurrence of a classification on the cartesian plane with a line.

_The Boundary can be a plane or other hyperplane depending the n dimension_

### Perceptrons
structural block of neural networks (coding of the equation in a little graph)

**first node (Σ)**: Receives the inputs and the bias and calculates the linear function result

**second node**: Step function that returns 1 if the result in the linear functions is positive or 0 if not

_Can be represented with the bias inside of the first node or the bias as a input_

**Perceptrons applications as logical operators**

logical operators can be represented with perceptrons (booleans inputs)

Adjust the weights and the bias to:
- AND
- OR
- NOT
- XOR (heterogeneous inputs)

### Creating perceptrons algorithm

1. Start with random weights: w1, ..., wn, b

2. For every misclassified point (x1, ..., xn):
    - 2.1. If prediction = 0:
        - For i = 1, ..., n
            - Change wi + α*xi
        - Change b to b + α
    - 2.2. If prediction = 1:
        - For i = 1, ..., n
            - Change wi - α*xi
        - Change b to b - α
