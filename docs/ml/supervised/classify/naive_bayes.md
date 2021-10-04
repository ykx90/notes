# Naive Bayes

## Bayes equation

$$P(y|x) = \frac {P(y)P(x|y)} {P(x)}$$

## Naive Bayes

$$P(x_i|y,x_1,...,x_i,...,x_n) = P(x_i|y)$$
$$P(y|x_1,...,x_n) \propto P(y) \prod_{i=1}^n{P(x_i|y)}$$
$$P(y|x_1,...,x_n) = \frac {P(y) \prod_{i=1}^n{P(x_i|y)}} {P(x_1,...,x_n)}$$

## Optimization
$$\hat{y} = \arg\max_y{P(y)\prod_{i=1}^n{P(x_i|y)}}$$


## Program

```py
from sklearn.datasets import load_iris
from sklearn.naive_bayes import MultinomialNB


if __name__ == '__main__':
    # input data
    X, y = load_iris(return_X_y=True)
    # create model
    clf = MultinomialNB().fit(X, y)
    # predict
    y_ = clf.predict(X)
    print('y_: {}'.format(y_))

    # estimate
    s_ = clf.score(X, y)
    print('s_: {}'.format(s_))
```