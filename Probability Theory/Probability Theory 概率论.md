# Probability Theory 概率论

## 基础

### 概率的公理化定义

![1562987588084](.\Probability Theory 概率论.assets\1562987588084.png)

概率的公理化定义虽刻画了概率的本质，但是没有告诉人们如何确定概率。因此可以将之前的古典定义、统计定义和主观定义视作确定概率的三种方法。

### 古典方法

基本思想如下：

![1562987911832](.\Probability Theory 概率论.assets\1562987911832.png)

可检验，古典方法得到的概率符合公理化定义。

### 频率方法

基本思想如下：

![1562988081161](.\Probability Theory 概率论.assets\1562988081161.png)

### 主观方法

![1562988194467](.\Probability Theory 概率论.assets\1562988194467.png)

### 条件概率

![1562988599077](.\Probability Theory 概率论.assets\1562988599077.png)

#### 性质

首先其必定满足公理化定义的三条性质

- 非负性：$P(A|B)\ge 0$
- 正则性：$P(\Omega|B)=1$
- 可加性：假如事件 $A_1$与 $A_2$ 互不相容

$$
P\left(A_{1} \cup A_{2} | B\right)=P\left(A_{1} | B\right)+P\left(A_{2} | B\right)
$$

此外，还有一些特殊性质：

- 乘法公式：对任意两个事件A和B
  $$
  P(A B)=P(A | B) P(B)=P(B | A) P(A)
  $$
  其中，要求 $P(B)\ge 0, P(A)\ge 0$

- 假设事件 $A,B$ 独立，且 $P(B)>0$，则 $P(A|B)=P(A)$，反之亦然。

- 一般乘法公式：
  $$
  P\left(A_{1} A_{2} A_{3}\right)=P\left(A_{1}\right) P\left(A_{2} | A_{1}\right) P\left(A_{3} | A_{1} A_{2}\right)
  $$
  其中 $P\left(A_{1} A_{2}\right)>0$

### 全概率公式

设 $A,B$任意两个事件，加入 $0<P(B)<1$，则
$$
P(A)=P(A | B) P(B)+P(A | \overline{B}) P(\overline{B})
$$
![1562989276061](.\Probability Theory 概率论.assets\1562989276061.png)

### 贝叶斯公式

![1562989310230](.\Probability Theory 概率论.assets\1562989310230.png)
$$
P\left(B_{k} | A\right)=\frac{P\left(A | B_{k}\right) P\left(B_{k}\right)}{\sum_{i=1}^{n} P\left(A | B_{i}\right) P\left(B_{i}\right)}, \quad k=1,2, \cdots, n
$$

### 随机变量的分布函数

设 $X$ 是一个随机变量，对任意实数 $x$ ，事件”$X\leq x$“ 的概率为 $x$ 的函数，记作：
$$
F(x)=P(X \leqslant x)
$$
称为 **X的累积概率分布函数**

### 概率的可列可加性公理

若 $A_{1}, A_{2}, \cdots$ 是一列互不形容事件，则有
$$
P\left(\bigcup_{n=1}^{\infty} A_{n}\right)=\sum_{n=1}^{\infty} P\left(A_{n}\right)
$$
**可列：** 如果一个集合与[正整数](https://baike.baidu.com/item/正整数)集合之间存在[一一对应](https://baike.baidu.com/item/一一对应)，则这个[集合](https://baike.baidu.com/item/集合)称为可列集（或[可数集](https://baike.baidu.com/item/可数集)）； 也就是说， 存在一个从该[集合](https://baike.baidu.com/item/集合)到正整数集合的[双射](https://baike.baidu.com/item/双射)（也称可逆映射）。

### 期望

期望由帕斯卡的分赌本问题引出

设离散随机变量X的分布列为
$$
P\left(X=x_{i}\right)=p\left(x_{i}\right), \quad i=1,2, \cdots, n
$$
则其数学期望为
$$
\sum_{i=1}^{n} x_{i} p\left(x_{i}\right)
$$
期望可以理解为在考虑各种情况后的预测产出。



## 离散随机变量

### 二项分布

#### 概率公式

$$
P(X=x)=\left(\begin{array}{l}{n} \\ {x}\end{array}\right) p^{x}(1-p)^{n-x}, \quad x=0,1, \cdots, n
$$

#### 数学期望

$$
E(X)=\sum_{x=0}^{n} x\left(\begin{array}{l}{n} \\ {x}\end{array}\right) p^{x}(1-p)^{n-x}
$$

### 泊松分布

#### 泊松定理

![1563001099604](.\Probability Theory 概率论.assets\1563001099604.png)
$$
\left(\begin{array}{l}{n} \\ {x}\end{array}\right) p_{n}^{x}\left(1-p_{n}\right)^{n-x} \rightarrow \frac{\lambda^{x}}{x !} e^{-\lambda} \quad(n \rightarrow \infty)
$$

$$
P(X=x)=\frac{\lambda^{x}}{x !} e^{-\lambda}, \quad x=0,1, \cdots
$$

#### 数学期望

$$
\begin{aligned} E(X) &=\sum_{x=0}^{\infty} x \cdot \frac{\lambda^{x}}{x !} e^{-\lambda} \\ &=\lambda e^{-\lambda} \sum_{x=1}^{\infty} \frac{\lambda^{x-1}}{(x-1) !}=\lambda \end{aligned}
$$

### 超几何分布

#### 概率公式

![1563001729430](.\Probability Theory 概率论.assets\1563001729430.png)
$$
P(X=x)=\frac{\left(\begin{array}{c}{M} \\ {x}\end{array}\right)\left(\begin{array}{c}{N-M} \\ {n-x}\end{array}\right)}{\left(\begin{array}{l}{N} \\ {n}\end{array}\right)}, \quad x=0,1, \cdots, r
$$

#### 数学期望

$$
\begin{aligned} E(X) &=\sum_{x=0}^{r} x \frac{\left(\begin{array}{c}{M} \\ {x}\end{array}\right)\left(\begin{array}{c}{N-M} \\ {n-x}\end{array}\right)}{\left(\begin{array}{c}{N} \\ {n}\end{array}\right)} \\ &=\frac{n M}{N} \sum_{x=1}^{r} \frac{\left(\begin{array}{c}{M-1} \\ {x-1}\end{array}\right)\left(\begin{array}{c}{N-M} \\ {n-x}\end{array}\right)}{\left(\begin{array}{c}{N-1} \\ {n-1}\end{array}\right)}=\frac{n M}{N} \\ \end{aligned}
$$

## 连续随机变量

连续随机变量的取值充满取值空间 $(a,b)$ ，因此无法使用离散的分布列形式表示，而要改用概率密度函数表示。

**概率密度函数的性质**

- 非负性：$p(x)\ge 0$
- 正则性：$\int_{-\infty}^{\infty} p(x) \mathrm{d} x=1$

$$
P(a \leqslant X \leqslant b)=\int_{a}^{b} p(x) \mathrm{d} x
$$

![1563002834375](.\Probability Theory 概率论.assets\1563002834375.png)

### 均匀分布 $U(a,b)$

#### 密度函数

$$
p(x)=\left\{\begin{array}{l}{\dfrac{1}{b-a}, \quad a\leq x\leq b} \\ {0, \qquad 其他}\end{array}\right.
$$

![1563003658881](.\Probability Theory 概率论.assets\1563003658881.png)

#### 分布函数

$$
F(x)=\left\{\begin{array}{ll}{0,} & {x<a} \\ {\dfrac{x-a}{b-a},} & {a \leqslant x \leqslant b} \\ {1,} & {x>b}\end{array}\right.
$$

![1563003966000](.\Probability Theory 概率论.assets\1563003966000.png)

#### 数学期望

$$
\begin{aligned} E(X) &=\int_{-\infty}^{\infty} x p(x) \mathrm{d} x=\int_{a}^{b} x \cdot \frac{1}{b-a} \mathrm{d} x \\ &=\frac{1}{b-a}\left.\frac{x^{2}}{2}\right|_{a} ^{b}=\frac{b^{2}-a^{2}}{2(b-a)} \\ &=\frac{a+b}{2} \end{aligned}
$$

### 指数分布 $Exp(\lambda)$

#### 密度函数                                                                                                                                                                                                                                                                                                            

$$
p(x)=\left\{\begin{array}{ll}{\lambda e^{-k x},} & {x \geqslant 0} \\ {0,} & {x<0}\end{array}\right.
$$

![1563003769928](.\Probability Theory 概率论.assets\1563003769928.png)

#### 分布函数

$$
F(x)=\left\{\begin{array}{ll}{0,} & {x<0} \\ {1-e^{-k},} & {x \geqslant 0}\end{array}\right.
$$

![1563004010600](.\Probability Theory 概率论.assets\1563004010600.png)

#### 数学期望

$$
E(X)=\int_{0}^{\infty} e^{-i x} \mathrm{d} x=-\frac{1}{\lambda}\left.e^{-\lambda x}\right|_{0} ^{\infty}=\frac{1}{\lambda}
$$

### 正态分布 $N(\mu,\sigma^2)$

#### 密度函数

$$
p(x)=\frac{1}{\sqrt{2 \pi} \sigma} \exp \left\{-\frac{(x-\mu)^{2}}{2 \sigma^{2}}\right\}, \quad-\infty<x<\infty
$$

#### 分布函数

$$
F(x)=\frac{1}{\sqrt{2 \pi} \sigma} \int_{-\infty}^{x} \exp \left\{-\frac{(x-\mu)^{2}}{2 \sigma^{2}}\right\} \mathrm{d} x, \quad-\infty<x<\infty
$$

![1563005381272](.\Probability Theory 概率论.assets\1563005381272.png)

#### 数学期望

$$
\begin{aligned} E(X) &=\frac{1}{\sqrt{2 \pi} \sigma} \int_{-\infty}^{\infty} x \exp \left\{-\frac{(x-\mu)^{2}}{2 \sigma^{2}}\right\} \mathrm{d} x \\ &=\frac{1}{\sqrt{2 \pi}} \int_{-\infty}^{\infty}(\sigma z+\mu) e^{-z^{2} / 2} \mathrm{d} z \\ &=\frac{1}{\sqrt{2 \pi}}\left[\sigma \int_{-\infty}^{\infty} z e^{-z^{2} / 2} \mathrm{d} z+\mu \int_{-\infty}^{\infty} e^{-z^{2} / 2} \mathrm{d} z\right] \end{aligned}
$$

#### 线性变换

$U\sim N(0,1)$ 为标准正态分布，其他正态分布 $X\sim (\mu,\sigma^2)$ 均可以通过线性变换转化为标准正态分布：
$$
U=\frac{X-\mu}{\sigma}
$$
通过线性变换，简化了正态分布概率的计算。

### Gamma分布 $Ga(\alpha,\lambda)$

#### Gamma函数

$$
\Gamma(\alpha)=\int_{0}^{\infty} x^{\alpha-1} e^{-x} \mathrm{d} x, \quad \alpha>0
$$

**性质**

- $\Gamma(1)=1, \Gamma\left(\frac{1}{2}\right)=\sqrt{\pi}$
- 递推公式 $\Gamma(\alpha+1)=\alpha \Gamma(\alpha)$ 由分部积分可得；特别地，对自然数n，$\Gamma(n+1)=n !$
- $\int_{0}^{\infty} x^{\alpha-1} e^{-\lambda x} \mathrm{d} x=\Gamma(\alpha) / \lambda^{\alpha}$

#### 密度函数

$$
p(x)=\left\{\begin{array}{ll}{\dfrac{\lambda^{\alpha}}{\Gamma(\alpha)} x^{\alpha-1} e^{-\lambda x},} & {x>0} \\ {0,} & {x \leqslant 0}\end{array}\right.
$$

其含有两个正参数 $\alpha,\lambda$。其中 $\alpha$是形状参数，$\lambda$为尺度参数。

形状参数 $\alpha=1$的Gamma为**指数函数**。

![1563006262699](.\Probability Theory 概率论.assets\1563006262699.png)

#### 分布函数

通过泊松分布导出Gamma分布
$$
1-F(t)=\sum_{x=0}^{k-1} \frac{(\lambda t)^{x}}{x !} e^{-\lambda t}=\frac{\lambda^{k}}{\Gamma(k)} \int_{t}^{\infty} x^{k-1} e^{-\lambda x} \mathrm{d} x
$$

$$
F(t)=\frac{\lambda^{k}}{\Gamma(k)} \int_{0}^{t} x^{k-1} e^{-\lambda x} \mathrm{d} x
$$

#### 数学期望

$$
E(X)=\frac{\lambda^{\alpha}}{\Gamma(\alpha)} \int_{0}^{\infty} x^{a} e^{-\lambda x} \mathrm{d} x=\frac{\Gamma(\alpha+1)}{\Gamma(\alpha)} \frac{1}{\lambda}=\frac{\alpha}{\lambda}
$$

### Beta分布 $Be(\alpha,\beta)$

#### Beta函数

$$
\beta(a, b)=\int_{0}^{1} x^{a-1}(1-x)^{b-1} \mathrm{d} x, \quad a>0, \quad b>0
$$

**性质**：

- $\beta(a, b)=\beta(b, a)$

- Beta和Gamma的关系:
  $$
  \beta(a, b)=\frac{\Gamma(a) \Gamma(b)}{\Gamma(a+b)}
  $$

#### 密度函数

$$
p(x)=\frac{\Gamma(a+b)}{\Gamma(a) \Gamma(b)} x^{a-1}(1-x)^{b-1}, \quad 0 \leqslant x \leqslant 1
$$

其中，$a,b$均为形状参数。

$a=b=1$时，Beta为均匀分布。

![1563007331558](.\Probability Theory 概率论.assets\1563007331558.png)

#### 数学期望

$$
\begin{aligned} E(X) &=\frac{\Gamma(a+b)}{\Gamma(a) \Gamma(b)} \int_{0}^{1} x^{a+1-1}(1-x)^{b-1} \mathrm{d} x \\ &=\frac{\Gamma(a+b)}{\Gamma(a) \Gamma(b)} \cdot \frac{\Gamma(a+1) \Gamma(b)}{\Gamma(a+b+1)} \\ &=\frac{a}{a+b} \end{aligned}
$$