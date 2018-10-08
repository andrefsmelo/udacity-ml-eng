# Decision Tree

## Entropy
Measures the heterogeneity in a set place (opposite of knowledge)

![entropy](http://dni-institute.in/blogs/wp-content/uploads/2015/08/Entrop.png)

 **pi**: Probability of a target variable in a sample

**Information gain:** Change in Entropy

**Split rule:** Best information gain

## Random Forest
Selects aleatory columns to set trees. The result in prediction is the most common result in the forest

## Hyperparameters

- max_depth: The maximum depth of the tree (number of leafs = 2^max_depth)

- min_samples_leaf: The minimum number of samples required to be at a leaf node

- min_samples_split: The minimum number of samples required to split an internal node

- max_features: The number of features to consider when looking for the best split

## Sklearn decision trees

```
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score

model = DecisionTreeClassifier(max_depth = 7, min_samples_leaf = 10)

model.fit(x_values, y_values)

y_pred = model.predict(x_values)

acc = accuracy_score(y, y_pred)
```
