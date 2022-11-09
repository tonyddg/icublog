## 一阶常微分方程
### 线性方程
$$\frac{dy}{dx} + a(x)y = b(x)$$
求解
$$y = e^{-\int{a(x)dx}}(C+\int{b(x)e^{\int{a(x)dx}}dx})$$
### 伯努利方程
n = 0, 1下为线性方程 
$$\frac{dy}{dx} + a(x)y = b(x)y^n$$
除以y^n^实现变量代换，转换为线性方程
### 变量代换（一阶非线性常微分方程）
$$(1)u = f(x, y)$$
$$(2)du = f_x(x, y)dx + f_y(x, y)dy$$
用(1)消去(2)中的x或y，实现变量代换
### 可降解二次方程
$$对于y'' = f(y, y')$$
$$令p=\frac{dy}{dx}有$$
$$\frac{dp}{dy} = \frac{d^2y}{dydx}$$
$$\frac{d^2y}{dx^2}=\frac{d^2y}{dydx}\frac{dy}{dx}=\frac{dp}{dy}p$$
通过$p=y'\; y''=pp'$代换实现降解