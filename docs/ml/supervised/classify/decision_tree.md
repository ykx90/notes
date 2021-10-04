# Decision Tree

## Information Entropy

$$H(X) = -\displaystyle\sum_{k=1}^N{p_k\log_2{(p_k)}} $$

## Information gain

$$G(D,a) = H(x) -\displaystyle\sum_{\nu=1}^{\Nu}{\frac {\begin{vmatrix}D^{\nu}\end{vmatrix}} {\begin{vmatrix}D\end{vmatrix}} H(D^{\nu})} $$

## C4.5

$$G_{r} = \frac {G(D,a)} {IV(a)}$$
$$IV(a) = \frac {\begin{vmatrix}D^{\nu}\end{vmatrix}} {\begin{vmatrix}D\end{vmatrix}} \log_2{\frac {\begin{vmatrix}D^{\nu}\end{vmatrix}} {\begin{vmatrix}D\end{vmatrix}}}$$

## Gini

$$Gini(D) = 1 - \displaystyle\sum_{k=1}^N{p_k^2}$$
$$Gini_a = \displaystyle\sum_{\nu=1}^{\Nu}{\frac {\begin{vmatrix}D^{\nu}\end{vmatrix}} {\begin{vmatrix}D\end{vmatrix}} Gini(D^{\nu})}$$

## Decision Tree in Python

- DecisionTreeClassifier
- DecisionTreeRegressor
- ExtraTreeClassifier
- ExtraTreeRegressor

## Program

```py
from sklearn.datasets import load_iris
from sklearn.tree import DecisionTreeClassifier


if __name__ == '__main__':
    # input data
    X, y = load_iris(return_X_y=True)
    # create model
    clf = DecisionTreeClassifier().fit(X, y)
    # predict
    y_ = clf.predict(X)
    print('y_: {}'.format(y_))

    # estimate
    s_ = clf.score(X, y)
    print('s_: {}'.format(s_))
```