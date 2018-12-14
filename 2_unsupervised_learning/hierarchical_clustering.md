# Hierarchical Clustering and based on density

Although KMeans is good, We need to learn new tools to work in cases where KMeans don't work so well.

## Hierarchical Clustering

### Agglomerative Clustering
Presuppose that in the beginning each point is a cluster

1. Each point is a cluster
2. Calculates the distance between each point and each other points
3. Joint the two closest clusters
4. Repeat 2 and 3 until remain just one cluster

How to measure the distance to a cluster with more than 1 point to another? <br>
There are a lot of ways and each one results in a different algorithm (Distance Measure)

#### Single-Link Clustering
Distance Measure: The distance between two clusters is the distance between the two closest points inside those clusters
- Elongated clusters

#### Complete-Link Clustering
Distance Measure: The distance between two clusters is the distance between the two farthest points inside those clusters
- Compacted clusters

#### Average-Link Clustering
Distance Measure: The mean of the distance between all points of a cluster to all other points of another cluster

#### Ward's Method
Distance Measure: The variance calculated on the central point of all other points minus the already existing variance in the separated clusters

```python
from sklearn import cluster

clust = cluster.AgglomerativeClustering(n_clusters=3, linkage='ward')

labels = clust.fit_predict(X)
```

#### Dendogram
![Dendogram](https://www.researchgate.net/profile/Joao_Junqueira2/publication/301419462/figure/download/fig1/AS:352927538532357@1461155890608/Figura-1-Dendograma-de-similaridade.png) <br>
Helps to choose the number of cluster that best fit your data

```python
from scipy.cluster.hierarchy import dendogram, ward, single
from sklearn import datasets
import matplotlib.pyplot as plt

X = datasets.load_iris().data[:10]

linkage_matrix = ward(X)

dendogram(linkage_matrix)

plt.show()
```
## Density Clustering
