# K-means

## Minkowski distance

$$d_P(x,y) = (\displaystyle\sum_{i=1}^n{\begin{vmatrix} x_i - y_i \end{vmatrix}^P})^{\frac {1} {P}}$$

## Euclidean distance

$$d_2{(x,y)} = \sqrt{\displaystyle\sum_{i=1}^n{(x_i - y_i)^2}}$$

## K-means in Python
- KMeans
- MiniBatchKMeans
- DBSCAN
- MeanShift
- AffinityPropagation

## Program

```py
from sklearn.datasets import make_blobs
from matplotlib import pyplot as plt
from sklearn.cluster import KMeans

if __name__ == '__main__':
    # input data
    n_samples = 1500
    X, y = make_blobs(n_samples=n_samples)
    # create model
    # p = KMeans(n_clusters=3).fit_predict(X)
    p = KMeans(n_clusters=3).fit(X)
    p_ = p.predict(X)
    plt.scatter(X[:,0], X[:,1],c=p_)
    plt.show()
```