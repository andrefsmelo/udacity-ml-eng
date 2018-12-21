# Gaussian Mixture Models
Assumes that each cluster follows a certain statistical distribution (Gaussian distribution). Gives the probability of a point belonging to each of **k** clusters.

![gaussianmixture](gauss.png) k=2

## Expectation Maximization Algorithm

1. Initialize K Gaussian distributions: To give a mean and a variance for each one. To set the distributions we use clusters created by K-Means.

2. Soft-Cluster data - "Expectation": Calculate the membership of each to each clusters

![Expectation](expectation.png)

3. Re-Estimate the Gaussians - "Maximization": **Pondered**

![NewMu](newmu.png)
![NewVar](newvar.png)

4. Evaluate Log-Likelihood to check for convergence
    - If not: repeat step 2 until converged

![loglike](loglike.png)
- The higher this number is, the more sure we are taht the mixer model fits the dataset that we have. The purpose here is to maximize this value
- π: The mixing coefficient

> Better results using covariance matrix instead of a variance

## Scikit-learn Implementation

```python
from sklearn import dataset, mixture

X = datasets.load_iris().data[:10]

gmm = mixture.GaussianMixture(n_components=3)

gmm.fit(X)

clustering = gmm.predict(X)
```
### Advantages
- Soft-Clustering (sample membership of multiple clusters)
- Cluster shape flexibility

### Disavantages
- Sensitive to initialization values
- Possible to converge to a local optimum
- Slow convergence rate

## Cluster Analysis

- Feature Selection/Extraction: PCA (principle components analysis)
- Clustering Algorithm Selection & Tuning: We also have to choose a proximity measure (Euclidean Measure/Cosine Similarity/Pearson Correlation)
- Clustering Validation: 
