# Naive Bayes
**Bayes theorem:** Switches from that we know to what we infer

| Known | Inferred |
| ---- | ---- |
| P(Red/Alex) | P(Alex/Red) |

![bayes](https://www.is-there-a-god.info/blog/wp-content/uploads/2016/02/Bayes_Theorem.jpg)

**False Negative: Error Type 1**

**False Positive: Error Type 2**

![false_positive](http://www.personal.ceu.hu/students/08/Olga_Etchevskaia/images/errors.jpg)

**P(Red/Alex,Brenda) = P(Red/Alex) * P(Red/Brenda)**
given that Alex and Brenda are independent (Naive)

_Naive Bayes' is an extension of Bayes' theorem that assumes that all the features are independent of each other_

**Bag of words:** Returns a matrix with the frequency of the words in that text

**Precision:** `[True Positives/(True Positives + False Positives)]`

**Recall(sensitivity):** `[True Positives/(True Positives + False Negatives)]`

## advantages
- ability to handle an extremely large number of features
- performs well even with the presence of irrelevant features and is relatively unaffected by them
- relative simplicity
- tuning it's parameters is rarely ever necessary, except usually in cases where the distribution of the data is known
- rarely ever overfits the data
