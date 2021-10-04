# Neural Network

## Active Functions

1. Sigmoid

$$Sigmoid(z) = \frac {1} {1 + e^{-z}} $$

2. Tanh
$$\tanh(x) = \frac {\sinh(x)} {\cosh(x)} = \frac {e^x-e^{-x}} {e^x + e^{-x}}$$

3. ReLu
$$ReLu(x) = \max{(0,x)}$$



## Program

```py
from sklearn.datasets import load_iris
from sklearn.neural_network import MLPClassifier

if __name__ == '__main__':
    # input data
    X, y = load_iris(return_X_y=True)
    # create model
    clf = MLPClassifier().fit(X, y)
    # predict
    y_ = clf.predict(X)
    print('y_: {}'.format(y_))

    # estimate
    s_ = clf.score(X, y)
    print('s_: {}'.format(s_))
```