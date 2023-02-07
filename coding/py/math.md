# Numpy
## 导入模块
```python
import numpy as np
```
习惯将 numpy 以 np 缩写导入

## 数组
### 创建数组
#### 一维数组
1. np.array([列表], dtype=[numpy 数据类型])
    1. 将列表转为数组, 嵌套列表则转为多维数组
    2. 使用 dtype 指定数据类型, 如 np.float, np.int16 等
2. np.arange([首相], [末项](, [步长]))
创建等差数列
3. np.linspace([首相], [末项], [长度])
创建等差数列

#### 二维数组
1. np.eye([大小])
创建单位矩阵
2. np.diag([对角线上的元素])
创建对角矩阵

#### 任意维度
1. np.ones/zeros([各维度大小的元组(shape)])
创建特殊数列
2. np.full([各维度大小的元组(shape)], [默认值])
#### 随机数
1. np.random.random([各维度大小的元组(shape)])
创建随机数组
2. np.random.randint([左区间], [右区间], size=[各维度大小的元组(shape)]) 
创建整数范围的随机数组

### 数组操作与合并
直接读取子队列

### 成员
1. 数组维度
np.array.ndim
2. 数组长度
np.array.shape
3. 数组元素数
np.array.size
4. 数组的数据类型
np.array.dtype

### 索引
1. 多个中括号
2. 一个中括号, 使用逗号区分维度
3. 多个索引也可使用
eg.
```python
arr[1:, 3]
```
4. 也可使用布尔法索引(同 matlab)
np.where([布尔数组], [索引数组], [默认值])
默认值通常使用 np.nan(非数字)

### 拷贝
1. 浅拷贝
new_arr = old_arr.view()
2. 深拷贝
new_arr = np.arr.copy()

### 合并
1. np.concatenate
2. np.insert


