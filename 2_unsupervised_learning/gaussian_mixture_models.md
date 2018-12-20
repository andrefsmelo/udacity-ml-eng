# Gaussian Mixture Models
Assumes that each cluster follows a certain statistical distribution (Gaussian distribution). Gives the probability of a point belonging to each of **k** clusters.

![gaussianmixture](https://www.mathworks.com/matlabcentral/mlc-downloads/downloads/submissions/54568/versions/1/screenshot.png) k=3

## Expectation Maximization Algorithm

1. Initialize K Gaussian distributions: To give a mean and a standard deviation for each one. To set the cluster we use K-Means.
2. Soft-Cluster data - "Expectation"
3. Re-Estimate the Gaussians - "Maximization"
4. Evaluate Log-Likelihood to check for convergence
    - If not: repeat step 2 until converged
