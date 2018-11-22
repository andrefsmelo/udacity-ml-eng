# Ensemble Methods
Take a bunch of models and join them together to get a better model.

**Weak Learners -> Strong Learner**

## Bagging (Bootstrap aggregating)
Models predict **samples** of the data, and after that, we choice the mean of the models results (or the most frequently result)

## Boosting
Tries to exploit the models strengths. Models predict the data where they achieve the better results

#### AdaBoost (Boosting Algorithm)
Builds weak learners in sequence using all data. After each model, gives more weight to the missclassifieds points and build another model. <br>
After a new weak learner, multiplies the weight of each misclassified point for **#Correct/#Incorrect** and the weight of each model will be **ln(#Correct/#Incorrect)**. <br>
After all, the strong learner will be weighted sum of weak models.


#### Sklearn AdaBoost
```
from sklearn.ensemble import AdaBoostClassifier
from sklearn.tree import DecisionTreeClassifier

model = AdaBoostClassifier(base_estimator = DecisionTreeClassifier(max_depth=2), n_estimators = 4)

model.fit(x_train, y_train)

model.predict(x_test)
```
#### Hyperparameters

- base_estimator: The weak learners model

- n_estimators: The maximum number of weak learners
