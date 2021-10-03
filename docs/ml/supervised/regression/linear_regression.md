# Linear Regression

`Linear Regression` is using linear model to resolve regression questions，the data fluctuated near the regression line. Focus points as bellow.
- Regression questions
- Linear equqtion
- Deviasion measurement
- Weight update

## Linear regression question

The essence is try the best to fit an unknown equation by a linear model which is trained based on history data.

### Linear equation 
`1-1` $$\hat{y} = w^{T}x_i + b$$ 

### Loss equation （L2 Norm Regularization）
`1-2` $$L(x) = \begin{Vmatrix} \hat{y} - y \end{Vmatrix}^2_2$$
$$\begin{Vmatrix} x \end{Vmatrix}_1 = \displaystyle\sum_{i=1}^n \begin{vmatrix} x_i \end{vmatrix}$$
$$\begin{Vmatrix} x \end{Vmatrix}_2 = \sqrt{\displaystyle\sum_{i=1}^n x^2_i}$$

$$\begin{cases} \hat{w} = \frac {\displaystyle\sum_{i=1}^n{ (x_i - \bar{x})(y_i - \bar{y})} }{ \displaystyle\sum_{i=1}^n{(x_i - \bar{x})^2} } = \frac {\displaystyle\sum_{i=1}^n{x_iy_i - n\bar{x}\bar{y}}} {\displaystyle\sum_{i=1}^n{x_i^2 - n\bar{x}^2}} \\ \hat{b} = \bar{y} - \hat{w}\bar{x} \end{cases}$$

### Loss equation optimization
`1-3` $$\min_{w,b}\begin{Vmatrix} \hat{y} - y \end{Vmatrix}^2_2$$

### Weight adjust equation
`1-4` $$w_{new} = w_{old} - \alpha * loss$$

*$\alpha$ is learning rate.*


## Resolution

- Step 1
Configurate the $w$ for the assumed function, draw a staight line by the assumed function, which means we calculate the output
as prediction values based on input data.

- Step 2
Calculate loss value by the loss function.

- Step 3
Based on the loss value, adjust the weight by sort of optimaztion funciton such as the gradient descent to minimum the loss value.
Repeat these steps above.

## Program

```py
import matplotlib.pyplot as plt
import numpy as np
from sklearn.linear_model import LinearRegression

if __name__ == '__main__':
    # vector of x
    x = np.linspace(-3, 3, 30)
    # vector of y
    y = 2 * x + 1

    # add random noise
    x = x + np.random.rand(30)

    # convert to 2-dimensions [1,2] -> [[1], [2]]
    x = [[i] for i in x]
    y = [[i] for i in y]

    print('x: {}, \ny: {}'.format(x, y))

    # predict target
    x_ = [[1], [2]]

    # create model
    model = LinearRegression()
    # fit linear equation
    model.fit(x, y)
    print('w: {}'.format(model.coef_))
    print('b: {}'.format(model.intercept_))
    # predict value
    y_ = model.predict(x_)
    print('x_: {}, \ny_: {}'.format(x_, y_))

    # result line 
    x__ = np.array([[-3], [3]])
    # y = w*x + b
    y__ = x__ * model.coef_ + model.intercept_
    # [[-3], [3]] -> [-3, 3]
    y__.resize(2)
    print('x__: {}, \ny__: {}'.format(x__, y__))

    # x,y scatter
    plt.scatter(x, y)
    # predicted scatter
    plt.scatter(x_, y_)
    # predict line
    plt.plot(x__, y__)
    plt.show()

```