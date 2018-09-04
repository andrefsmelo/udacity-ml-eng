# Perceptron Algorithm

## Classification problem
Need to return a specific answer
- True or False
- Multi classification

### Boundary line
Separates the occurrence of a classification on the cartesian plane with a line.

_The Boundary can be a plane or other hyperplane depending the n dimension_

### Perceptrons
structural block of neural networks (coding of the equation)

**first node (Σ)**: Receives the inputs and the bias and calculates the linear function result

**second node**: Step function that returns 1 if the result in the linear functions is positive or 0 if not

_Can be represented with the bias inside of the first node or the bias as a input_

**Perceptrons with logical operators**
- AND
- OR
- NOT
- XOR

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
