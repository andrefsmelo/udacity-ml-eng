# Ensemble Methods
Take a bunch of models and join them together to get a better model.

**Weak Learners -> Strong Learner**

## Bagging (Bootstrap aggregating)
Models predict **samples** of the data, and after that, we choice the mean of the models results (or the most frequently result)

## Boosting
Tries to exploit the models strengths. Models predict the data where they achieve the better results

#### AdaBoost (Boosting Algorithm)
Builds weak learners in sequence using all data. After each model, gives more weight to the missclassifieds points and build another model. We choice the most frequently result.

After a new weak learner, multiplies the weight of each misclassified point for ln(Correct/Incorrect)
