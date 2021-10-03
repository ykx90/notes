# Basic Usage of Numpy


## 1. Functions

Function | Type | Description
:-:   | :-:    | :-:
array | Create | 传入数组，向量来创建张量
zeros | Create | 全零张量
ones  | Create | 全一张量
eye   | Create | 单位矩阵
arange | Create | 等差数值
linspace | Create | 可设定终值的等差数值
random.rand | Create | $[0,1)$随机数
reshape | Operate | 不改变原数据的维度变换
resize | Operate | 改变原数据的维度变换
T | Operate | 改变原数据的转置
append | Operate | 追加
insert | Operate | 插入
delete | Operate | 删除
concatenate | Operate | 按行/列连接
add | Calculate | 加
subtract | Calculate | 减
multiply | Calculate | 乘
divide | Calculate | 除
exp | Calculate | 以e为底的指数
log | Calculate | 以2为底的指数
dot | Calculate | 点乘
mean | Statistic | 平均值
sum | Statistic | 和
max | Statistic | 最大值
min | Statistic | 最小值
var | Statistic | 方差
std | Statistic | 标准差
corrcoef | Statistic | 相关系数

## 2. Usages

```python
# create data
a1 = np.array([1, 2, 3])
print('array: {}'.format(a1))
a2 = np.zeros((2, 2))
print('zeros: {}'.format(a2))
a3 = np.ones((2, 2))
print('ones: {}'.format(a3))
a4 = np.eye(2)
print('eye: {}'.format(a4))
a5 = np.arange(1, 5)
print('arange: {}'.format(a5))
a6 = np.linspace(1, 5, 6)
print('linspace: {}'.format(a6))
a7 = np.random.rand(2)
print('random.rand: {}'.format(a7))
# data operate
a8 = np.random.randint(1, 100, 9)
a8 = a8.reshape((3, 3))
print('reshape: {}'.format(a8))
a9 = a8.T
print('T: {}'.format(a9))
a9.resize(9)
print('resize: {}'.format(a9))
a9 = np.append(a9, [11])
print('append: {}'.format(a9))
a9 = np.insert(a9, 1, 5)
print('insert: {}'.format(a9))
a10 = np.insert(a8, 1, 5, axis=1)  # axis=0 : row, axis=1 : column
print('insert axis: {}'.format(a10))
a11 = np.delete(a10, 1, axis=1)
print('delete: {}'.format(a11))
a12 = a11.flatten()
print('flatten: {}'.format(a12))
a13 = np.concatenate((a10, a11), axis=1)
print('concatenate: {}'.format(a13))
# calculate
a14 = np.array([1, 2, 3])
a15 = np.array([4, 5, 6])
a16 = np.add(a14, a15)
print('add: {}'.format(a16))
a17 = np.subtract(a14, a15)
print('subtract: {}'.format(a17))
a18 = np.multiply(a14, a15)
print('multiply: {}'.format(a18))
a19 = np.divide(a14, a15)
print('divide: {}'.format(a19))
a20 = np.exp(a14)
print('exp: {}'.format(a20))
a21 = np.log(a14)
print('log: {}'.format(a21))
a22 = np.dot(a14, a15)
print('dot: {}'.format(a22))
# statistic
a23 = np.mean(a14)
print('mean: {}'.format(a23))
a24 = np.sum(a14)
print('sum: {}'.format(a24))
a25 = np.max(a14)
print('max: {}'.format(a25))
a26 = np.min(a14)
print('min: {}'.format(a26))
a27 = np.var(a14)
print('var: {}'.format(a27))
a28 = np.std(a14)
print('std: {}'.format(a28))
a29 = np.corrcoef(a14, a15)
print('corrcoef: {}'.format(a29))
```

## 3. Console Outputs

```txt
array: [1 2 3]
zeros: [[0. 0.]
 [0. 0.]]
ones: [[1. 1.]
 [1. 1.]]
eye: [[1. 0.]
 [0. 1.]]
arange: [1 2 3 4]
linspace: [1.  1.8 2.6 3.4 4.2 5. ]
random.rand: [0.93553183 0.63210419]
reshape: [[ 4 81 68]
 [92  8 61]
 [57 74  4]]
T: [[ 4 92 57]
 [81  8 74]
 [68 61  4]]
resize: [ 4 81 68 92  8 61 57 74  4]
append: [ 4 81 68 92  8 61 57 74  4 11]
insert: [ 4  5 81 68 92  8 61 57 74  4 11]
insert axis: [[ 4  5 81 68]
 [92  5  8 61]
 [57  5 74  4]]
delete: [[ 4 81 68]
 [92  8 61]
 [57 74  4]]
flatten: [ 4 81 68 92  8 61 57 74  4]
concatenate: [[ 4  5 81 68  4 81 68]
 [92  5  8 61 92  8 61]
 [57  5 74  4 57 74  4]]
add: [5 7 9]
subtract: [-3 -3 -3]
multiply: [ 4 10 18]
divide: [0.25 0.4  0.5 ]
exp: [ 2.71828183  7.3890561  20.08553692]
log: [0.         0.69314718 1.09861229]
dot: 32
mean: 2.0
sum: 6
max: 3
min: 1
var: 0.6666666666666666
std: 0.816496580927726
corrcoef: [[1. 1.]
 [1. 1.]]

```