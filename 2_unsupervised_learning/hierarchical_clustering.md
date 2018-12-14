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
### Advantages
- Resulting hierarchical representation can be very informative
- Provides an additional ability to visualize
- Especially potent when the dataset contains real hierarchical relationships (e.g. Evolutionary biology)

### Disadvantage
- Sensitive to noise and outliers
- Computationally intense O(N²)

## Density Clustering

### DBSCAN (Density-Based Spatial Clustering of Applications with Noise)

- For each point selected randomly:
    1. Search distance **ε** around point and how many other points are inside:
        - If the number of other points is greater than **n**:
            - The point is a cluster
                - If there is some other cluster inside the **ε** area:
                    - The point belongs to the same cluster
                - If there isn't:
                    - The point's cluster is new
        - If the number of other points is less than **n**:
            - It is a Noise Point

**ε:** Epsilon<br>
**n:** Minimum number

```python
from sklearn import datasets, cluster

X = datasets.load_iris().data

db = cluster.DBSCAN(eps=0.5, min_sample=5)

db.fit_predict(X)
```
### Advantages
- We don't need to specify the number of clusters
- Flexibility in the shapes & sizes of clusters
- Able to deal with noise and outliers

### Disadvantage
- Border points that are reachable from two clusters
- Face difficulty finding clusters of varying densities (HDBSCAN)
