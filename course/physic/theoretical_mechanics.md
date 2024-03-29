# 静力学
## 静力学基础
### 静力学公理
#### 二力平衡
只受两个力的单个刚体 (任意形状) 处于平衡状态时, 两个力一定大小相同, 方向相反, 且在同一直线上

#### 力的可传导性
单个刚体上的力可沿其作用线移动而不改变效果

#### 三力交会平衡定理
受三个不平行的力的单个刚体处于平衡状态时, 三个力必定共面且交于一点

#### 作用力与反作用力
相互作用的两个物体间总存在等值, 反向, 共线且分别作用于两个物体的一对力

#### 刚化公理
平衡状态下, 可将变形体视为刚体 (平衡状态下, ==可将柔绳等作为刚体==)

### 力偶
* 两个等值, 平行, 反向的力组成的力系称为力偶
* 力偶间的最短距离 (==垂直==距离) 称为力偶臂 $d$
* 定义平面力偶矩 $M=\pm Fd$, 正负号取决于转动正方向
* 力偶矩与力偶的位置无关

### 约束
约束处存在约束力, 约束力大小未知, 根据主动力变化而变化

#### 光滑接触面约束
约束力为接触点的==公法线==方向 (不一定是竖直方向)

#### 铰链约束
* 铰链对两个连接体的约束力等值反向, 方向任意, 通常分解为 两个正交的未知力
* 当铰链上有两个以上物体时, 对各个物体的约束力之和为 $0$

#### 固定铰链约束
与铰链约束相同, 由于地面通常静止, 因此铰链静止

#### 活动铰链支座
约束力垂直于活动方向

#### 插入端约束
插入端的各点收到多个力, 可等效为两个正交的约束力与一个约束力偶

### 受力分析
1. 未知力以正交分量的形式表现
1. 力的方向 (作用线) 确定, 大小未知时, 指向可以任意 (作为正方向)
1. 可用三力汇交提前确定部分力的方向
1. 先整体再部分, 分析部分注意反作用力
1. 整体受力图不需要表示内力 

## 平面力系的简化
### 力平移定理
刚体内的力 $F$ 移动到任意一点 $B$ 后得到 $F'$, 为了不改变力的作用效果, 需要再补充一个附加力偶, 力偶矩大小 $M=M_{BF}$, 即原来的力 $F$ 对新点 $B$ 之矩

### 分布力系的化简
* 分布力系图示中的细实线 $ab$ 表现了分布力强度 $q(N/m)$ 随位置 $x(m)$ 的变化关系
* 根据积分可得, 等效合力的大小即图形面积
* 将分布力向分布力强度图的形心 $C$ 简化可不产生附加力矩
* 假设 $q_0=bB$

#### 矩形分布力系
![](./theoretical_mechanics_res/rect_sys.jpg)

* 简化后等效合力为 $$R=q_0l$$
* 无附加力矩的简化点为 $$d=\frac{l}{2}$$

#### 三角形分布力系
![](./theoretical_mechanics_res/triangle_sys.jpg)

* 简化后等效合力为 $$R=\frac{q_0l}{2}$$
* 无附加力矩的简化点为 $$d=\frac{2}{3}l$$

### 平面力系的平衡条件
* 当平面力系平衡时, 将会满足 $$\vec{F_R}=\sum \vec{F}=0\\M_O=\sum M+\sum Fd=0$$ 其中 $\vec{F_R}$ 为总和力, $M_O$ 为所有力对任意点之矩, 包括力偶矩
* 根据力系的化简可得, 一个平衡状态下的刚体可以提供 $3$ 个平衡方程
* 可通过指定方向 $F_x=0$ 与对任意点 $O$ 取矩得到三个平衡方程
* 三个方程中对两点 $A,B$ 取矩时, ==$AB$ 不能与 $F$ 分解方向垂直==
* 三个方程对三点取矩时, 三点不能共线 
* 对于二力杆, 取矩无意义, 仅有两个方程

### 平衡方程解题技巧
1. 可以将平衡状态下的组合体 (部分整体) 视为一个刚体使用平衡方程
1. 组合体中, 一个刚体可提供三个方程, 约束可提供等同于其约束反力数的方程, 无论从组合体还是刚体分析, 总方程数不变
1. 优先分析整体, 避免内力
1. 优先对多力交汇点取矩, 减小计算量
1. 优先向不求力的垂直方向分解, 减小计算量
1. 检查: 
    1. 受力分析
    1. 方程是否少力, 少力矩
    1. 确认力矩方向

### 桁架分析
#### 桁架构造
1. 所有杆件和受力均在同一平面内
1. 以三角形为结构基础
1. 支座反力量不超过 $3$ 个
1. 所有杆均为二力杆

#### 内力计算
![](./theoretical_mechanics_res/truss.jpg)

1. 以杆受拉方向为内力正方向 (因此节点所受的反力方向向外)
1. 沿指定方向截切桁架, 将得到部分视为刚体, 除原本所受外力外, 还受到沿被截切方向的, 来自被截切杆的内力 (拉力的反作用力, 方向与拉力相反)
1. 尽量一次仅截出三个未知量, 保证三个平衡方程可解

#### 零力杆分析
由于均为二力杆, 因此外力必定在节点处
内力计算前, 可先移去零力杆, 简化计算

1. 一点两杆无外力
1. 一点两杆有外力, 外力沿其中一杆的方向, 则另一杆为零力杆
1. 一点三杆无外力, 其中两杆共线, 第三杆为零力杆

## 摩擦
### 滑动摩擦力
1. 作用在接触点, 沿接触点切线方向
1. 总是与运动趋势相反
1. 随主动力增大而增大, 满足 $$0\le F_s\le F_{max}=F_Nf_s$$

#### 摩擦自锁
定义 $$\tan\varphi_f=f_s=\frac{F_{max}}{F_N}$$ 当物体所受外力 $\vec{F_R}$ 与接触点的==法线夹角== $\varphi<\varphi_f$ 时, $\vec{F_R}=\vec{F_N}+\vec{F_s}$, 物体总是保持平衡, 称为摩擦自锁

注意支持力 $F_N$ 的方向为法线方向, 即垂直于接触面

### 滚动摩擦力
* 实际情况下, 接触面为一个复杂的力系, 但可以分解为 $F_s,F_N,M_f$, 其中 $M_f$ 为滚阻力偶
* 滚阻力偶总是阻止物体滚动
* 随主矩增大而增大, 满足 $$0\le M_f\le M_{max}=F_N\delta$$
* 对于面接触中, 由于只能相对点翻滚, 因此在临界状态下, 可视为接触点为翻滚点的点接触 ($F_s,F_N$ 作用于此点)

### 摩擦平衡分析
在摩擦平衡分析中, 求临界力/质量时, 仅通过平衡方程一般无法求出所有力, 因此要假设部分摩擦处于临界状态作为已知条件

1. 先比较未知力 (包括未知摩擦力与摩擦滚阻) 与系统平衡方程数, 得到需要补充的临界条件数
1. 轮子逆时针滚动时, 质心向左移动, 存在顺时针的滚阻, 但可能不存在向左的滑动摩擦力 (没有相对滑动)
1. 轮子逆时针滚动时, 更可能出现向右滑动的趋势, 即打滑, 此时滑动摩擦力与滚阻的运动效果均与主矩相反, 更可能达到临界
1. 对于任何物体均存在滚动与滑动两种趋势, 且均有两个方向 (如果没有给出 $\delta$, 则不考虑滚动)
1. 由于 $\delta$ 一般较小, 因此滚动通常会是临界条件

## 空间力系分析
### 空间力矩论
#### 对点之矩
* 对一固定点 $O$ 的力矩 $\vec{M_O}=\vec{r}\times\vec{F}$
* ==其中 $r$ 为点 $O$ 到力作用点的矢量==
* 与平面不同, 此时力矩为矢量

#### 对轴之矩
对于空间的轴, 只有垂直于轴的分量有转动效果, 因此力矩为 $$M_{z}=\pm hF_{xy}$$

* $h$ 为力 $F$ 作用点到轴的距离
* ==力对轴之矩等于力对轴上任一点之矩在轴上的投影== (用于计算任意轴的矩) $$M_{l}=\vec{M_O}\frac{\vec{l}}{|l|}$$

#### 空间力偶
* 定义空间力偶矢 $$\vec{M}=\vec{r}\times\vec{F}$$
* 其中 $\vec{r}$ 为力偶中两力作用点的矢量
* 空间力偶的具体指向可通过右手螺旋定则确定
* 空间力偶性质与平面力偶相同, 可以自由移动

### 空间力系的化简
#### 空间力系的化简结果
对于任意空间力系可化简为 $\vec{F_R},\vec{M_O}$

1. $\vec{F_R}=0,\vec{M_O}=0$, 力系平衡
1. $\vec{F_R}\neq 0,\vec{M_O}=0$, 仅有一个力, 力系最简
1. $\vec{F_R}=0,\vec{M_O}\neq 0$, 无论向那点化简, 始终为一个力偶
1. $\vec{F_R}\neq 0,\vec{M_O}\neq 0$, 向其他点化简可以消去 $\vec{M_O}$, 得到 $\vec{F_R}\neq 0,\vec{M_O}=0$
1. $\vec{F_R}\parallel\vec{M_O}\neq 0$, 无法化简, 为一个力螺旋

#### 空间力系的平衡条件
根据力系的化简可得, 一个平衡状态下的空间刚体可以提供 $6$ 个平衡方程
$$\sum F_x=0\;\sum F_y=0\;\sum F_z=0\\
\sum M_x=0\;\sum M_y=0\;\sum M_z=0$$

与平面类似, 可以对更多的轴取矩, 但不能对通过同一点的 $3$ 根以上的轴取矩, 也不能对 $3$ 根以上的平行轴取矩

* 选取轴时, 不一定是在已知杆上, 也可以是空间中的两点连线
* 选择与未知量共面的轴, 避开求未知量

# 运动学
## 质点运动学
### 自然坐标系
设质点轨迹的指向运动方向的切向为 $\vec{\tau}$, 指向曲率圆心的法向 $\vec{n}$, 将 $\vec{\tau},\vec{n}$ 构成的坐标系称为自然坐标系

#### 速度表示
自然坐标系下, $\vec{\tau}$ 即速度的方向, 因此 $\vec{v}=v\vec{\tau}$

#### 加速度分解
自然坐标系下, 加速度可分解为切向加速度 $a_t$ 与法向加速度 $a_n$, 根据微分关系可表示为 $$\vec{a}=a_t\vec{\tau}+a_n\vec{n}=\frac{dv}{dt}\vec{\tau}+\frac{v^2}{\rho}\vec{n}$$
其中 $v$ 为速度的大小, 不是矢量; $\rho$ 为轨迹的曲率半径, 可通过此方法求出运动轨迹的曲率半径

### 点运动的合成
将点的运动向静系和动系分解, 可得到三种运动

1. 绝对运动 (absolution) 动点相对于静系的运动
1. 相对运动 (relation) 动点相对于动系的运动
1. 牵连运动 (entrainment) 动系相对于静系的运动

解题时必须明确指出所选择的动系与计算的动点

#### 速度合成定律
$$\vec{v_a}=\vec{v_r}+\vec{v_e}$$

#### 加速度合成定律
加速度合成时, 如果动系不是平动 $\omega=0$ , 还==要考虑科氏加速度 $\vec{a_k}=2\vec{\omega}\times\vec{v_r}$ 的影响==
$$\vec{a}=\vec{a_r}+\vec{a_e}+2\vec{\omega}\times\vec{v_r}$$

#### 动系动点的选择
1. 动点为两个框体的交点时, 分别以两个框体为动系, 联立方程
1. 没有稳定接触点时, 使用刚体的平面运动
1. 有稳定接触点时, 动系的选择
    1. 动点不能在动系上, 否则无意义
    1. 动系最好与题目有关 (求动系的 $\omega$ )
    1. 动点轨迹易求
    1. 动系平动 (避免求科氏加速度)
1. 动点选择
    1. 套筒
    1. 铰链
    1. 圆心
    1. 杆的一端

## 刚体的平面运动
### 刚体转动
在刚体上选取任意基点, 刚体上其他点相对于基点的角速度与角加速度相同

### 基点法
将刚体上的点的运动分解为:
* 相对于基点的转动 (刚体上两点距离不变, 只能做转动运动)
* 基点作为动系的平动

选取基点 $A$, 求刚体上的质点 $B$ 的运动有
#### 基点法求速度
$$\vec{v_B}=\vec{v_A}+\vec{v_{BA}}$$

其中
$$\vec{v_{BA}}=\vec{\omega}\cdot\vec{AB}$$

#### 基点法求加速度
$$\vec{a_B}=\vec{a_A}+\vec{a_{BA}^n}+\vec{a_{BA}^e}$$

其中
$$\vec{a_{BA}^n}=|AB|\omega^2=\frac{v_{BA}^2}{AB}$$ $$\vec{a_{BA}^t}=|AB|\alpha$$

#### 速度投影法
将基点法向 $\vec{AB}$ 投影可得, 对于刚体上任意两点, 满足 $$\vec{v_A}\cdot\vec{e_{AB}}=\vec{v_B}\cdot\vec{e_{AB}}$$

反映了刚体上任意两点距离不变的特性

### 速度瞬心法
* 刚体上必定存在一点 $C$, 满足 $v_C=0$
* 通过对刚体上两点速度方向垂线的交线得到 $C$
* 如果垂线平行, 则能判断刚体平动, $\omega=0$
* 对于刚体上任意一点 $M$, $v_M=MC\cdot\omega$
* 速度瞬心的加速度一般不为 $0$

### 加速度投影法
* 当刚体平动 $\omega=0$ 时使用
* 此时没有法向加速度, 只有切向加速度, 表现出类似速度的性质
* 因此有加速度投影法 $$\vec{a_A}\cdot\vec{e_{AB}}=\vec{a_B}\cdot\vec{e_{AB}}$$

### 加速度瞬心
* 一般情况下加速度瞬心无法直接求得
* 如果刚体 $v\neq 0$, 由于法向加速度, 加速度瞬心难以使用
* 当 $v=0$, 与速度瞬心性质类似, 加速度瞬心为两点加速度垂线的交点

### 纯滚动
* 当圆柱体 (齿轮) 等于地面没有相对滑动, 则称为纯滚动
* 设圆心 $O$, 接触点 $A$

#### 纯滚动的运动特性

1. 当纯滚动的接触面为地面时 (静止物体, 圆心水平运动)
    1. 纯滚动中, 接触点 $v_A=0$ 为速度瞬心
    1. 根据速度瞬心法可得 $v_O=r\omega$
    1. 接触点不是加速度瞬心
    1. 圆心的切向加速度满足 $a_O^t=r\alpha$
1. 当纯滚动的接触面为弧面时, 圆心还有法向加速度 $a_O^n=\frac{v_O^2}{r+R}$ (切向加速度不变)
3. 当相对于运动物块纯滚动时, 则以物块为动系, 当物块平动时, 满足 $a_O^r=r\alpha$

#### 纯滚动的其他特性
1. 对于绳子绕在圆柱上, 认为绳子与圆柱的接触点纯滚动
1. 纯滚动的位置通常存在一个拉力 / 滑动摩擦力

#### 齿轮问题
1. 齿轮齿数 $z$ 满足 $$\frac{z_1}{z_2}=\frac{r_1}{r_2}=i_{12}$$ 其中 $i_{12}$ 为齿轮的传动比
1. 齿轮 / 齿条的啮合处 $C$ 为纯滚动, 且对于两齿轮速度相同, 满足 $$r_1\omega_1=-r_2\omega_2=v_C$$
1. ==注意外啮合的两个齿轮转向必定相反, 因此要加负号==

### 刚体绕平行轴转动
对于二维动系中的刚体, 满足 $$\omega_a=\omega_r+\omega_e$$ $$\alpha_a=\alpha_r+\alpha_e$$

#### 曲柄固定齿轮问题
* 对于曲柄固定齿轮的角速度问题, 可以设曲柄为动系, 其他齿轮相对曲柄运动, 此时齿轮圆心相对静止, 易于计算
* 其中固定齿轮 $\omega_a=\omega_r+\omega_e=0$
* 由于要引入科氏加速度, 不适用于加速度计算

### 套筒问题
1. 套筒内的刚体相对于套筒平动, 即刚体上各点的 $v_r$ 相同, 刚体 $\omega_r=0$
1. 根据角速度叠加可得, 套筒内的刚体绝对角速度与绝对角加速度与套筒相同
1. 与套筒转轴的重合点 $P$ 上, $v_e=0$, 因此 $v_r=v_P$ (套筒为动系, $P$ 为动点)

# 动力学
## 动力学普遍定律
### 动量定理
#### 质点系动量定理
对于质心 $C$, 有动量定理 $$m\vec{a_C}=\sum\vec{F}$$

#### 动量守恒定理
当外力之和 $\sum \vec{F^{(e)}}=0$, 则质点系动量守恒, 满足 $$m\vec{v_C}=k$$

当 $\vec{v_C}=0$, 则积分后还可得到 $$m\vec{r_C}=0$$ 初速度为零时, 质心位置不会改变, 对于某个方向的初速度分量也可使用此公式, 可用于计算光滑下滑问题

### 动量矩定理
#### 动量矩定义
对于一==固定点 $O$==, 定义刚体的动量矩
$$\vec{L_O}=\sum(\vec{r}\times m\vec{v})$$
对动量矩求导可得 $$\vec{M_O}=\frac{d\vec{L_O}}{dt}=\sum(\vec{r}\times\vec{F})$$

#### 转动惯量
|形状|轴位置|J|
|---|---|---|
|细杆|杆的一端|$$\frac{1}{3}mL^2$$|
|细杆|杆的中点|$$\frac{1}{12}mL^2$$|
|薄圆筒|中轴线|$$mR^2$$|
|圆盘/柱|中轴线|$$\frac{1}{2}mR^2$$|
|球壳|直径|$$\frac{2}{3}mR^2$$|
|球|直径|$$\frac{2}{5}mR^2$$|
|矩形薄板|矩形中心|$$\frac{m}{12}(a^2+b^2)$$|
##### 平行轴定理
$$J = J_c + md^2$$
特别注意此处 $J_c$ 为通过质心的轴, $d$ 为平行轴到质心轴的距离
##### 正交轴定理
$$J_z = J_x + J_y$$
仅用于薄板，J~z~为垂直于板的轴

#### 质点系动量矩
对于==任意点 $D$==, $C$ 为刚体质心, 刚体角速度为 $\omega$, 在一个瞬间内, 定义刚体的动量矩 $$\vec{L_D}=J_C\vec{\omega}+\vec{r_C}\times m\vec{v_C}$$

对 $\vec{L_D}$ 求导可发现, 一般情况下, $\vec{r_C}\times m\vec{v_C}$ 项的导数难以求解, 为了避开此项, 需要选取特殊的 $D$ 点, 称为动矩心
1. 质心 $C$
1. 刚体的固定转轴
1. 加速度为 $0$ 的点 (加速度瞬心, 瞬时平动时使用)

此时有等式 $$\vec{M_D}=J_D\vec{\omega}$$
==注意, 对于不同的动矩心 $D$, $J_D$ 的取值不同==

#### 刚体平面运动微分方程
* 对于单个刚体的动矩心 $D$ 与 质心 $C$ 有方程
* 用于求解结构简单的单个物体的 $a,v$

$$\begin{cases}ma_{Cx}&=&\sum F_x^{(e)}\\
ma_{Cy}&=&\sum F_y^{(e)}\\
J_D\alpha&=&\sum M^{(e)}\end{cases}$$

### 动能定理
#### 力做功
注意是点乘, 方向不一致需要投影
$$W_{12}=\int \vec{F}d\vec{r}$$

#### 力矩做功
$$W_{12}=\int Md\varphi$$

#### 常见势能计算
==计算势能时, 最好先明确势能零点, 一般取平衡位置==

##### 重力势能
$$E_p=-mg\Delta h=mg(h_{初}-h_{末})$$

##### 弹性势能
$$E_p=\frac{1}{2}k(\Delta l_{初}^2-\Delta l_{末}^2)$$
 
#### 刚体动能
$$E_k=\frac{1}{2}mv_C^2+\frac{1}{2}J_C\omega^2$$

#### 理想约束
由于==刚体内力不做功==, 因此
对于以下约束, 约束力不做功
1. 固定光滑接触面约束
1. 光滑铰链约束
1. 光滑铰链支座约束
1. 静摩擦 (如纯滚动中的静摩擦)
1. 不可伸长的柔绳约束

#### 动能定理
$W_{12}$ 表示从状态 $1$ 到状态 $2$, 外力做功
用于求解结构复杂的单自由度机构的 $v,a,F$

$$E_{2}-E_{1}=W_{12}$$

## 动力学应用
### 功率方程
* 功率可以表示为物体能量的导数, 即 $$P=\frac{d(E_k+E_p)}{dt}$$
* 对于刚体上所有受力点 $i$, 功率也可表示为 (==注意是点乘, 方向不一致需要投影==) $$P=\sum \vec{F_i}\cdot\vec{v_i}$$
* 联立两式即为功率方程
* 功率方程适用于单自由度的复杂机构

#### 功率方程求导注意
* 只有普遍成立的表达式才可以求导
* 题目中一般求得的均为瞬间状态
* 可以先列出普遍成立的表达式, 在对其求导后带入瞬间状态的值


### 达朗贝尔原理
达朗贝尔原理根据动量定理, 引入惯性力与惯性力矩, 平衡外力, 将动力学问题转化为静力学问题

* 对整体使用达朗贝尔原理得到的三个方程于功率方程独立
* 对于物体较少, 多自由度时, 使用达朗贝尔原理

#### 惯性力
定义作用于简化中心 $D$ 的惯性力 (实际应用中会先正交分解惯性力) $$\vec{F_I}=-m\vec{a_C}$$

* ==注意惯性力的大小于简化中心的位置无关, 仅与质心加速度有关==
* 惯性力的简化中心位置无要求

#### 惯性力矩
惯性力矩同样只有在以下特殊简化 $D$ 中心才易于计算
1. 质心 $C$
1. 刚体的固定转轴
1. 加速度为 $0$ 的点 (加速度瞬心, 瞬时平动时使用)
1. 加速度矢量通过质心 (纯滚动中的速度瞬心符合此条件)

此时惯性力矩为 $$\vec{M_I}=-J_D\vec{\alpha}$$

* ==注意惯性力的大小与简化中心的位置有关==
* 力矩在任何位置作用效果相同

### 自由度
* 完全确定一个机构的状态的最少参数
* 一个二维刚体提供 $3$ 个自由度
* 一个约束可减少 $n$ 个自由度
* 自由度可表示为 $$DoF=3m-\sum n_i$$
* 自由度参数可以是坐标 $x$, 也可是角度 $\theta$ 等

#### 动力学解题过程
1. 受力分析图
1. 速度分析图
1. 加速度分析图
1. 列出运动学方程
1. 补充动力学方程
1. 当方程数 = 未知量个数, 解方程

### 虚位移原理
* 虚位移原理本质是引入运动学与功能原理, 解决静力学问题, 避免求内力
* 当系统保持平衡时, 对于一组虚位移, 外力做虚功必定为 $0$ $$\sum \vec{F^{(e)}}\delta\vec{r}=0$$

#### 单自由度应用
* 大部分情况下, 虚位移方向与对应的速度 (坐标) / 角速度 (角度) 方向相同, 因此可直接使用速度 / 角速度代替虚位移, 使用功率方程代替做功
* 单自由度只能得到单个独立的虚位移方程
* 首先要分析机构的速度关系
* 将其中一个速度作为已知量, 表示出其他速度, 列出功率表达式
* 令功率 $P=0$, 消去方程中的已知量, 得到方程

#### 多自由度应用
* 先找出合适的自由度参数
* 固定其他参数, 只保留一个, 以单自由度的方法处理, 得到方程
* 对其他自由度重复, 每有一个自由度, 便得到一个方程
* 固定参数方法: 令参数所表示的速度 / 角速度为 $0$
* 也可以采用限定方向 (使不待求的力 $\vec{F}\cdot\vec{v}=0$) 的方式减小自由度

#### 计算约束力
* 解除需要计算的约束力
* 对于铰链约束, 求某方向的约束力时, 可假设只存在另一方向的约束力
* 对于纯滚动的摩擦力与支持力, 可以类比为固定铰链支座的正交分力, 与铰链约束相同
* 对于桁架, 只需移去待求内力所在杆 (桁架为二力杆, 但两端节点速度无关)

# 解题思路
## 受力分析
1. 二力杆 (仅有两个节点且不受力的刚体) 上, 杆上两点受力方向必定在两点连线且方向相反
1. 对部分受力分析时, 通常不带上销钉, 销钉单独分析
1. 多个物体中, 注意作用力与反作用力

## 静力学
1. 先从整体分析, 看能否解出题目要求的量, 如果不能, 则移去受力复杂且与待求量无关的部分再分析
1. 优先对未知量的交汇点取矩, 避免未知量
1. 对于同一点在铰链上与在杆一端上的受力情况不同
1. 先不使用虚位移定理, 特别是没有特殊角度, 只有特殊垂直长度时, 有一个以上的待求力, 不使用虚位移
1. 对于方向未知 / 复杂的力, 先分解为 x, y 方向

## 运动学
1. ==先分析各点之间的长度与角度==
1. 再分析速度, 加速度
1. 不能忘记科氏加速度 $a_k=2\vec{\omega}\times\vec{v_r}$
1. 对点分析时, 要指出动点与动系
1. 点的物理量表示方法
    * 字母: 表示速度 $v$ / 加速度 $a$
    * 下标: 
    物理量所在点, 重合时, 优先认为是动点 (质点运动分析) + 分解方向
    基点 + 所在点 (刚体运动分析)
    * 上标: 绝对值无上标, 与动系关系 $r/e/k$ + 在转动中的属性 $t/n$ (加速度)

## 动力学
### 功率方程
1. 分析物体的能量时, 应先列出原始表达式, 并对原始表达式求导
1. 注意刚体的动能 $E_k=\frac{1}{2}mv_c^2+\frac{1}{2}J_c\omega^2$, 其中 $J_c$ 为质心转矩
1. 对求导后的方程带入瞬时值计算
1. 注意方程中的物理量为向量, 不能直接相乘
    * $P=\vec{F}\vec{v}$
    当重力与速度不不平行时, 注意夹角
    * $\frac{dE}{dt}=m\vec{v}\vec{a}$
    对于匀速转动的点, 有 $\vec{v}\vec{a}=0$, 因此 $\frac{dE}{dt}=0$

### 动静法
1. 开始与运动学相同, 最后列出受力分析
1. 根据受力分析推断需要补充的方程
1. 当找不到方程时
    1. 分析质心与刚体上各个已知点的加速度关系
    1. 标记出已知量, 未知量以及不同方程组中的相关量
    1. 投影避开未知量, 联立相关量, 特别是与角加速度相关的量 (角加速度)
    1. 得出质心加速度与角加速度之间的关系

## 计算检查
1. 点长度是否正确
1. 带入计算时是否漏负号
1. 是否要考虑重力 (铅垂平面)
