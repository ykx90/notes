# SVM (Support Vector Machine)


## SVM in Python

- LinearSVC
- LinearSVR
- SVC  (kernel: linear 线性, polynomial 多项式, rbf 径向基, sigmoid, precomputed 预设核值矩阵)分类
- SVR 回归
- NuSVC
- NuSVR
- OneClassSVM

## Program

```py
from sklearn.datasets import load_iris
from sklearn.svm import SVC

if __name__ == '__main__':
    # input data
    X, y = load_iris(return_X_y=True)
    # create model
    clf = SVC().fit(X, y)
    print('kernel: {}'.format(clf.kernel))
    # predict
    y_ = clf.predict(X)
    print('y_: {}'.format(y_))

    # estimate
    s_ = clf.score(X, y)
    print('s_: {}'.format(s_))
```