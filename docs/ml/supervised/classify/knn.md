# KNN (K-Nearest Neighbor)

## Minkowski distance

$$d_P(x,y) = (\displaystyle\sum_{i=1}^n{\begin{vmatrix} x_i - y_i \end{vmatrix}^P})^{\frac {1} {P}}$$

## Manhattan distance

$$d(x,y) = \displaystyle\sum_{i=1}^n{\begin{vmatrix} x_i - y_i \end{vmatrix}}$$

## KNN in Python

- KNeighborsClassifier
- KNeighborsRegression
- RadiusNeighborsClassifier
- NearestNeighbors
- KDTree
- BallTree


## Program

```py
from sklearn.datasets import load_iris
from sklearn.neighbors import KNeighborsClassifier

if __name__ == '__main__':
    # input data
    X, y = load_iris(return_X_y=True)
    # create model
    clf = KNeighborsClassifier().fit(X, y)
    # predict
    y_ = clf.predict(X)
    print('y_: {}'.format(y_))

    # estimate
    s_ = clf.score(X, y)
    print('s_: {}'.format(s_))
```