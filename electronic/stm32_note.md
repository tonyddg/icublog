## C 部分
### 定义结构体
c 为面向过程语言, 没有类
通常定义结构需要使用语法
```c
struct [struct类型] 变量名;
```

使用 typedef 可以避免
```c
typedef struct
{
    ...
}example1;

// 使用 typedef 不需要 struct
example1 a;

struct example2
{
    ...
};

// 需要 struct 标记
struct example2 b;
```

### 二进制/十六进制字面量
```c
unsigned a = 0xFFFF;// 十六进制字面量

unsigned b = 0b1110111;// 二进制字面量
```

字面量默认为 int 型, 直接与 uint8/16 加减将溢出, ==使用字面量时(特别是作为二进制命令), 在最后加上 u, eg. 0xB1u== 

### 逻辑
比较两个逻辑量是否相等时, 应用异或, 或转为数字, 比较是否相等

## 电路部分
### 电源
1. PCB 上结号编号表示等位点, 结号编号相同的两个点为并联关系的等位点
当核心板任意一个 5V Vcc 节点与电源连接, 即所有 5V Vcc 节点与电源连接, 具有 5V 的电压
通过降压芯片, 使所有 3.3V Vcc 获得 3.3V 电压
2. 任何非 5V 的电源不能与 5V Vcc 节点连接, 必须通过降压芯片

### 引脚不能供电
引脚通过核心芯片引出, 不能作为电源, 否则当电流过大, 会烧坏芯片

## 库函数部分
### 初始化外设
1. 库函数均通过 XXX_InitTypedef 与 XXX_Init 实现初始化
2. 初始化的选项必然为 XXX_InitTypedef.(成员名) = (成员名)_(初始化选项)

### 标志的使用
1. 使用 XXX_GetFlagStatus(一般) / XXX_GetITStatus(中断) 获取标志信息 RESET 表示 0, SET 表示 1
2. 通过 XXX_GetFlagStatus / XXX_GetITStatus 获得标志后, 必须使用 XXX_ClearFlag/XXX_ClearITPendingBit

### 中断
部分中断服务函数没有在启动文件中声明, 需要手动添加

### SPI
1. 全双工模式下, 写入后必须马上读取

## BUG 诊断部分
### 通用
1. 任何需要初始化的函数是否在程序中调用 是否调用了 XXXInit
### 库函数
1. 是否正确初始化时钟 RCC_XXXPeripheralClockCmd
2. 重复使用由 XXX_Cmd(XXX, ENABLE) 开启的功能时(如 DMA), 必须先调用 XXX_Cmd(XXX, DISABLE) 关闭后再开启
3. 将 GPIO 设置为输入/复用/重映射/EXITn时, 需要启动 AFIO 功能 RCC_APB2PeriphClockCmd(RCC_APB2Periph_AFIO,ENABLE);
### Cube
1. 检查外设的初始化方式是否正确
### 中断
1. Cube 中是否添加了 NVIC
2. 代码中中断是否使能
3. UART 中的 TXE 中断最好仅在必要时开启
### 语言
1. 使用 C++ 时, 所有 C 部分均要使用 extern "C" 修饰(直接对 include 使用即可)
2. 使用十六进制码表示指令时, 在末尾加上 u 修饰, 表示为无符号
3. 调试中如果进入 HardFault_Handler 时, 根据调用堆栈判断出错位置
4. 使用标准库时, 其中的 stm32f10x_it.c/h 不能注释里面已定义的中断函数
5. 使用 DMA 时, 将数组作为传输地址时, 注意数组名即数组地址, 不需要再取地址
### EIDE
1. 烧录配置中 接口属性使用 cmsis-dap.cfg
2. debug 出错时, 检查是否勾选选项中的 将 axf 转为 elf
3. debug 前先烧录程序
4. 使用 ADC连续转换+DMA 可能会导致无法烧录的 bug, 需要在烧录前关闭此功能或关闭ADC连续转换功能

### UART
1. 中断是否使能
2. 是否添加 NVIC
3. 波特率是否匹配
