# Logistic Regression

## Logistic equation

$$Logistic(z) = \frac {1} {1 + e^{-z}} $$

$$H(x) = \frac {1} {1 + e^{-(w^Tx_i+b)}}$$

## Loss equation
$$L(x) = -y\log{H(x)}-(1-y)\log{(1-H(x))}$$

## Logistic Regression in Python

1. Linear Regression Class

$$L(x) = \min_w{\begin{Vmatrix} X_w - y \end{Vmatrix}_2^2}$$

2. Ridge Class

$$L(x) = \min_w{\begin{Vmatrix} X_w - y \end{Vmatrix}_2^2} + a\begin{Vmatrix} w \end{Vmatrix}_2^2$$

3. Lasso Class

$$L(x) = \min_w{\frac {1} {2n} \begin{Vmatrix} X_w - y \end{Vmatrix}_2^2} + a\begin{Vmatrix} w \end{Vmatrix}_2^2$$


## Program

```py

from sklearn.linear_model import  LogisticRegression
from sklearn.datasets import load_iris
import matplotlib.pyplot as plt

if __name__ == '__main__':
    # input data
    X, y = load_iris(return_X_y=True)
    # create model
    clf = LogisticRegression().fit(X, y)
    # predict
    y_ = clf.predict(X)
    print('y_: {}'.format(y_))

    # estimate
    s_ = clf.score(X, y)
    print('s_: {}'.format(s_))

```