---
tags:
  - Knowledge
---
## 随机变量
### 基本概念
- **方差**：$$D(X)=E[(X-E(X))^2]=E(X^2)-E(X)^2$$
- **协方差(Covariance)**：用来衡量两个随机变量的变化趋势是否一致。对于两个随机变量$X,Y$，其协方差为$$\sigma(X,Y)=E((X-E(X))\cdot(Y-E(Y)))=E(XY)-E(X)E(Y)$$
	从数值上来说，协方差越大，说明两个变量的同向趋势越大；协方差越小，说明两个变量的反向趋势越大；协方差越趋近于零，两个变量越不相关。
- **协方差矩阵**：对于$d$个随机变量，我们可以求出一个协方差矩阵：
	$$
	\Sigma=
	\begin{bmatrix}
	\sigma(X_1,X_1) & \cdots & \sigma(X_1,X_d) \\
	\vdots & \ddots & \vdots \\
	\sigma(X_d,X_1) & \cdots & \sigma(X_d,X_d)
	\end{bmatrix}
$$ ^8w027v
## 参数估计
- **似然函数(Likelihood Function)**：对于函数$P(x|\theta)$，其中$x$表示实际数据，$\theta$表示模型参数，则若$x$固定，$P(x|\theta)$随$\theta$变化，那么这个函数叫做似然函数。
	> [!note] 似然函数与概率函数
	> 若$\theta$固定，$P(x|\theta)$随着$x$变化，则此函数是一个固定模型的概率函数。
- **最大似然估计(Maximum Likelihood Estimation, MLE)**：当我们有一组数据$x_1,x_2,\cdots,x_{n}$时，我们需要求出那个最可能得出这组数据的模型参数$\theta^*$，也即求$$\mathop{\arg\max}\limits_{\theta}\prod_{i=1}^{n}P(x_i|\theta)\equiv\mathop{\arg\max}\limits_{\theta}\sum_{i=1}^{n}\log P(x_i|\theta)$$ ^tyfz0r
### Logit
- **Odds**：也是用来表示概率大小的量，不过概率的取值范围为$[0,1]$，而odds的取值范围为$[0,+\infty)$，其公式为$$Odds(P)=\frac{P}{1-P}$$
- **Logit函数**：在odds的基础上取对数，即可得到Logit$$Logit(P)=\log Odds(P)=\log\frac{P}{1-P}$$其图像如下：![[Pasted image 20240317154521.png|400]]
- **Sigmoid函数**：是Logit的反函数$$\sigma(x)=\frac{1}{1+e^{-x}}$$![[Pasted image 20240317155319.png|400]]