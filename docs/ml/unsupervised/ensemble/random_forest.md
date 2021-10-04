# Random Forest

## Ensemble learning
1. Bagging Algorithm
2. Boosting Algorithm
3. Stacking Algorithm

## Ensemble in Python

- RandomForestClassifier
- RandomForestRegressor
- ExtraTreesClassifier
- ExtraTreesRegressor
- AdaBoostClassifier
- AdaBoostRegressor
- GradientBoostingClassifier  + CART => Gradient Boosting Decision Tree(GBDT)
- GradientBoostingRegressor

## Program

```py
from sklearn.datasets import load_iris
from sklearn.ensemble import RandomForestClassifier

if __name__ == '__main__':
    # input data
    X, y = load_iris(return_X_y=True)
    # create model
    clf = RandomForestClassifier().fit(X, y)
    print('estimators_: {}'.format(clf.estimators_))
    # predict
    y_ = clf.predict(X)
    print('y_: {}'.format(y_))

    # estimate
    s_ = clf.score(X, y)
    print('s_: {}'.format(s_))
```
