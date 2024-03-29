---
tags:
  - Knowledge
---
## 对偶问题
### Farkas引理
设$A\in\mathbb{R}^{m\times n},b\in\mathbb{R}^{m}$，则以下两个论断有且只有一个是对的：
1. $\exists x\in\mathbb{R}^{n}$，使得$Ax=b$，且$x\geq0$；
2. $\exists y\in\mathbb{R}^{m}$，使得$A^Ty\geq0$，且$b^Ty<0$。

直观证明可见[知乎上Johnny Richards的回答](https://www.zhihu.com/question/279644412/answer/565859435)。
### 线性规划的对偶问题
考虑一个标准的线性规划
$$\begin{aligned}
\min&\ c^Tx\\
\text{subject to}&\ Ax=b,x\succeq0
\end{aligned}$$
则其对偶问题为
$$\begin{aligned}
\max&\ -b^T\nu\\
\text{subject to}&\ A^T\nu+c\succeq0
\end{aligned}$$
## 拉格朗日乘子法
**拉格朗日乘子法**是把约束条件下的求极值问题转化为求拉格朗日函数的极值问题。

一个标准的凸优化问题
$$
\begin{aligned}
&\min_{x}f(x)\\
s.t.\ &g_{m}(x)=0,&m=1,2,...,M\\
&h_{n}(x)\leq0,&n=1,2,...,N
\end{aligned}
$$
我们可以通过最小化以下函数来取得最优解$$L(x,\lambda,\mu)=f(x)+\sum_{m=1}^{M}\lambda_{m}g_{m}(x)+\sum_{n=1}^{N}\mu_nh_n(x)$$
其中$\lambda,\mu$为**拉格朗日乘子(Lagrange Multiplier)**。可以得到最优解的*必要条件*是：
$$
\left\{\begin{aligned}
\nabla_{x}L&=0\\
g(x)&=0&\text{原等式约束}\\
h(x)&\leq0&\text{原不等式约束}\\
\mu&\geq0\\
\mu_nh_n(x)&=0&\text{互补松弛}
\end{aligned}\right.
$$
此条件也称为**KKT条件**。