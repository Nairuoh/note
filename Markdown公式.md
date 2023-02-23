## Markdown (LaTex公式)

### 1 基本位置

正文某一行内插入公式使用`$ ... $`

正文单独一行插入公式使用`$$ ... $$`,此时公式居中显示。

#### 1.1 字母位置

上、下标：`$ C_5^2 $`------$C_5^2$

矢量：　　`$ \vec x $`------$\vec x$

拔：　　　`$ \bar x $`------$\bar x$

上波浪：　`$ \tilde x $`------$\tilde x$

估计：　　`$ \hat x $`------$\hat x$

#### 1.2 括号位置

尖括号：　　`$ \langle \rangle $`------$\langle \rangle$
小括号：

+ 直接使用 `$ ( \frac xy ) $`------$( \frac xy )$
+ 转义引用,括号大小自适应调整 `$ \left(\frac xy \right) $`------$\left(\frac xy \right)$

大括号：
+ 直接使用大括号{}不会显示，会使包裹在其中的公式合在一起`$ \frac{xy}{ab}  $`------$ \frac{xy}{ab} $
+ 使用转义字符直接显示 `$ \{xy\}  $`------$ \{xy\} $

### 2 特殊字母

#### 2.1 希腊字母

![希腊字母表](https://gitee.com/st1711460741/blog_image_1/raw/master/img/22.PNG)

+ 大写字母：令首字母大写，如`$ \Omega $`------$\Omega$
+ 斜体字母：加上前缀var,如`$ \varOmega $`------$\varOmega$

特殊：
`$ \varphi $`------$\varphi$
`$ \phi $`------$\phi$

#### 2.2 数学符号

无穷:`$ \infty $`------$\infty$
虚数:`$ \imath $`------$\imath$

所有：`$ \forall $`------$\forall$
存在：`$ \exists $`------$\exists$

梯度(倒三角)：`$ \nabla $`------$\nabla$

#### 2.3 箭头

上箭头：`$ \uparrow $`------$\uparrow$
下箭头：`$ \downarrow $`------$\downarrow$
左箭头：`$ \leftarrow $`------$\leftarrow$
右箭头：`$ \rightarrow $`------$\rightarrow$

#### 2.4 逻辑符号

与：`$ \vee $`------$\vee$
或：`$ \wedge $`------$\wedge$
非：`$ \lnot $`------$\lnot$

### 3 数值运算

乘：　`$ \times $`------$\times$
除：　`$ \div $`------$\div$
加减：`$ \pm $`------$\pm$
减加：`$ \mp $`------$\mp$

不等于：　`$ \neq $`------$\neq$
小于等于：`$ \leq $`------$\leq$
大于等于：`$ \geq $`------$\geq$
约等于：　`$ \approx $`------$\approx$
恒等于：　`$ \equiv $`------$\equiv$

分式：`$ \frac {x}{y} $`------$\frac {x}{y}$
求和：`$ \sum $`------$\sum$
极限：`$ \lim $`------$\lim$
积分：`$ \int $`------$\int$
偏导：`$ \partial $`------$\partial$



### 4 集合运算

属于：　`$ \in $`------$\in$
不属于：`$ \notin $`------$\notin$

真子集：`$ \subset $`------$\subset$
子集：　`$ \subseteq $`------$\subseteq$

并集：　`$ \cup $`------$\cup$
交集：　`$ \cap $`------$\cap$
空集：　`$ \emptyset $`------$\emptyset$
　　　　`$ \varnothing $`------$\varnothing$


### 5 矩阵

#### 5.1 基本语法

起始标记`\begin{matrix}`，结束标记`\end{matrix}`
每一行末尾标记`\\\`，行间元素之间以`&`分隔
```
$$\begin{matrix}
1&0&0\\
0&1&0\\
0&0&1\\
\end{matrix}$$
```
$$\begin{matrix}
1&0&0\\
0&1&0\\
0&0&1\\
\end{matrix}$$

#### 5.2 矩阵边框

+ 在起始、结束标记处用下列词替换 `matrix`
+ `pmatrix` ：小括号边框
+ `bmatrix` ：中括号边框
+ `Bmatrix` ：大括号边框
+ `vmatrix` ：单竖线边框
+ `Vmatrix` ：双竖线边框

#### 5.3 省略元素

+ 横省略号：`\cdots`
+ 竖省略号：`\vdots`
+ 斜省略号：`\ddots`
```
$$\begin{bmatrix}
{a_{11}}&{a_{12}}&{\cdots}&{a_{1n}}\\
{a_{21}}&{a_{22}}&{\cdots}&{a_{2n}}\\
{\vdots}&{\vdots}&{\ddots}&{\vdots}\\
{a_{m1}}&{a_{m2}}&{\cdots}&{a_{mn}}\\
\end{bmatrix}$$
```
$$\begin{bmatrix}
{a_{11}}&{a_{12}}&{\cdots}&{a_{1n}}\\
{a_{21}}&{a_{22}}&{\cdots}&{a_{2n}}\\
{\vdots}&{\vdots}&{\ddots}&{\vdots}\\
{a_{m1}}&{a_{m2}}&{\cdots}&{a_{mn}}\\
\end{bmatrix}$$

#### 5.4 阵列

+ 需要`array`环境：起始、结束以`{array}`声明
+ 对齐方式：在`{array}`后以`{}`逐行统一声明
  + 左对齐：`1` 居中：`c` 右对齐：`r`
  + 竖直线：在声明对齐方式时，插入`|`竖直线
+ 插入水平线：`\hline`

```
$$\begin{array}{c|lll}
{↓}&{a}&{b}&{c}\\
\hline
{R_1}&{c}&{b}&{a}\\
{R_2}&{b}&{c}&{c}\\
\end{array}$$
```
$$\begin{array}{c|lll}
{↓}&{a}&{b}&{c}\\
\hline
{R_1}&{c}&{b}&{a}\\
{R_2}&{b}&{c}&{c}\\
\end{array}$$

### 6 方程组

+ 需要cases环境：起始、结束处以{cases}声明
```
$$\begin{cases}
a_1x+b_1y+c_1z=d_1\\
a_2x+b_2y+c_2z=d_2\\
a_3x+b_3y+c_3z=d_3\\
\end{cases}
$$
```

$$\begin{cases}
a_1x+b_1y+c_1z=d_1\\
a_2x+b_2y+c_2z=d_2\\
a_3x+b_3y+c_3z=d_3\\
\end{cases}
$$


## Markdown 进阶(html语法)

### 1 字体

#### 1.1 调整字体、颜色和尺寸：
`<font face="黑体" color=green size=5>我是黑体，绿色，尺寸为5</font>`------
<font face="黑体" color=green size=5>我是黑体，绿色，尺寸为5</font>

#### 1.2 背景色

以表格形式写，填充表格背景色：
`<table><tr><td bgcolor=yellow>背景色yellow</td></tr></table>`------
<table><tr><td bgcolor=yellow>背景色yellow</td></tr></table>

### 2 图片

<img src="https://i.loli.net/2021/05/29/hKVz6SFgafyoTm4.jpg" style="zoom:25%;" />

#### 2.1 设置图片百分比显示

<img src="https://i.loli.net/2021/05/29/hKVz6SFgafyoTm4.jpg" width="50%" height="50%">

#### 2.1 设置图片大小

<img src="https://i.loli.net/2021/05/29/hKVz6SFgafyoTm4.jpg" width="251" height="350" >

#### 2.1 设置图片居中

<div align=right><img src="https://i.loli.net/2021/05/29/hKVz6SFgafyoTm4.jpg" width="50%" height="50%"></div>
