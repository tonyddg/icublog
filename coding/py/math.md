# 在 Python 中绘图与运算
## 通用注意
### 函数参数
注意函数参数的传入方式
1. 普通传参
1. 指定参数的传参
1. 不定长传参
1. 通过元组 () 或数组 [] 传入不定长参数

### 模拟抽象
1. 在模拟前需要先确定 $dt$ 长度等物理常数
1. 可将 $dt$ 作为 np.arange() 的 step

## numpy 注意
### 小数迭代
1. 使用 np.arange() 可以实现将小数用于迭代
1. 可在迭代中使用一个临时变量 i 记录迭代次数, 以用于向记录数组添加元素

### 数组使用
1. 使用数组前, 最好使用 np.zeros() 确定足够的空间
1. 由公式确定空间时, 需要使用 np.floor() 等与 int() 将小数转为整数

### 数组生成
1. np.array() 将 python 内部的数据结构转为 np.array
1. np.zeros/random() 等, 提供一个表示各维度大小的元组

### 矢量/点数组
1. 创建矢量 vec = np.array((x, y)).T
1. 创建矢量数组 vecArr = np.zeros((2, size))
1. 修改/读取矢量数组元素 vecArr[..., i] = vec 
1. 将矢量数组作为点绘制 axe.plot(vecArr[0], vecArr[1])

## mlp 注意
### 功能抽象
1. 在实现功能后, 对某些绘图功能进行抽象
1. 先提取出有关物理参数, 作为全局变量
1. 将绘制图片的 axe 作为参数传入, 可以在外部创建 axe 后传入, 在绘制完成后对 axe 进行进一步设置
1. 将使用到的函数 / 方程作为参数传入, 可通过 def fun(x): return full_fun(x, y = ...) 的方式传入可设置的函数
