---
draft: false
series: 未分类
title: 第十八届全国大学生数学竞赛（非数学A类）初赛解析
date: 2026-11-17T14:03:44+08:00
lastmod: 2026-11-19T10:54:43+08:00
---
# 一

**(1)** $\lim_{x \to 0}\left(\dfrac{1}{x\sin x}-\dfrac{1}{x^{2}}\right)=$ ___

**(2)** 若 $f(x)=\begin{cases} c^x(\sin x+\cos x), & x\ge 0,\\ abx^2+ax+2a+b, & x<0\end{cases}$ 的导函数在 $\mathbb{R}$ 上连续，则 $3a+2b=$ ___

**(3)** 点 $(2024, 2025, 2026)$ 关于直线 $\begin{cases} 2x+y-6076=0, \\ y+2z-6080=0 \end{cases}$ 的对称点为 ___

**(4)** 设 $f(x, y)$ 具有连续偏导数，$f(1,1)=1$，$f_x^{\prime}(1,1)=1$，$f_y^{\prime}(1,1)=2$。若 $\varphi(x)=f(x, f(x, x))$，则 $\varphi^{\prime}(1)=$ ___

解析：

**知识点**

多元复合函数链式法则：$z=f(u,v)$，则
$$
\frac{dz}{dx}=f'_1\cdot u'+f'_2\cdot v'
$$
$f'_1$、$f'_2$ 分别是对第一、第二个位置的偏导。

**步骤**
记 $u(x)=f(x,x)$：
$$
u'(x)=f'_1(x,x)+f'_2(x,x)
$$
对 $\varphi(x)=f(x,u(x))$ 求导：
$$
\varphi'(x)=f'_1(x,u)+f'_2(x,u)\cdot u'(x)
$$
代回 $u=f(x,x)$：
$$
\varphi'(x)=f'_1(x,f(x,x))+f'_2(x,f(x,x))\left[f'_1(x,x)+f'_2(x,x)\right]
$$
取 $x=1$，由 $f(1,1)=1$ 得内层取值均为 $(1,1)$：
$$
\varphi'(1)=f'_1(1,1)+f'_2(1,1)\left[f'_1(1,1)+f'_2(1,1)\right]=1+2\times(1+2)=7
$$
**答案：$7$**

**(5)** $\lim_{n \to \infty}\dfrac{1}{n}\left(\sqrt{1+\sin\dfrac{\pi}{3n}}+\sqrt{1+\sin\dfrac{2\pi}{3n}}+\cdots+\sqrt{1+\sin\dfrac{3n\pi}{3n}}\right)=$ ___

解析：

**知识点：定积分定义（黎曼和）**

求 $y=f(x)$ 在 $[0,1]$ 下方那块面积。
把 $[0,1]$ 切成 $n$ 个小长条，每个宽 $\frac{1}{n}$。
第 $k$ 个长条取高度 $f(\frac{k}{n})$，面积约等于 高乘宽：
$$
f\left(\frac{k}{n}\right)\cdot \frac{1}{n}
$$
把所有小长条面积加起来：
$$
S_n=\frac{1}{n}\sum_{k=1}^{n}f\left(\frac{k}{n}\right)
$$
$n$ 越大越精确，$n\to\infty$ 就是真实面积：
$$
\int_0^1 f(x)\,dx=\lim_{n\to\infty}\frac{1}{n}\sum_{k=1}^{n}f\left(\frac{k}{n}\right)
$$
标准模板：
$$
\frac{1}{n}\sum_{k=1}^{n}f\left(\frac{k}{n}\right)\to\int_0^1 f(x)\,dx
$$
**步骤**
$$
\frac{1}{n}\sum_{k=1}^{3n}\sqrt{1+\sin\frac{k\pi}{3n}}
$$
这里不是到 $n$，而是到 $3n$ 项。令 $t_k=\frac{k}{3n}$。
那么 $\frac{k\pi}{3n}=\pi t_k$，而 $\frac{1}{n}=3\cdot\frac{1}{3n}$。
所以原式 $=3\int_0^1\sqrt{1+\sin\pi t}\,dt$。
用恒等式：
$$
1+\sin\theta=\left(\sin\frac{\theta}{2}+\cos\frac{\theta}{2}\right)^2
$$
开方（$t\in[0,1]$ 时非负）：
$$
\sqrt{1+\sin\pi t}=\sin\frac{\pi t}{2}+\cos\frac{\pi t}{2}
$$
$$
\int_0^1\sin\frac{\pi t}{2}dt=\left[-\frac{2}{\pi}\cos\frac{\pi t}{2}\right]_0^1=\frac{2}{\pi}
$$
$$
\int_0^1\cos\frac{\pi t}{2}dt=\left[\frac{2}{\pi}\sin\frac{\pi t}{2}\right]_0^1=\frac{2}{\pi}
$$
合起来 $\frac{4}{\pi}$，乘 3：
$$3\times\frac{4}{\pi}=\frac{12}{\pi}$$
**答案：$\frac{12}{\pi}$**

**二、(本题 14 分)** 设函数 $f(x,y)$ 在点 $(0,0)$ 的某个邻域内连续，且

$$
\lim_{(x,y)\to(0,0)}\frac{f(x,y)-xy}{x^{2}+y^{2}}=c.
$$

**(1)** 若 $c>\frac{1}{2}$，$f(0,0)$ 是否为 $f(x,y)$ 的极值？证明你的结论。

**解**

由题设

$$
f(x,y)=xy+(x^{2}+y^{2})\cdot\frac{f(x,y)-xy}{x^{2}+y^{2}},
$$

其中分式在 $(0,0)$ 的去心邻域内局部有界，与无穷小 $(x^{2}+y^{2})$ 相乘后趋于 $0$，又 $xy\to0$，故 $f(x,y)\to0$。由 $f$ 在 $(0,0)$ 连续得

$$
f(0,0)=0.
$$

取 $\varepsilon=\frac{c-\frac{1}{2}}{2}>0$，由局部保号性，存在去心邻域，在其中

$$
\frac{f(x,y)-xy}{x^{2}+y^{2}}>c-\varepsilon=\frac{c+\frac{1}{2}}{2}.
$$

于是

$$
f(x,y)>\frac{1}{2}\left(c+\frac{1}{2}\right)(x^{2}+y^{2})+xy.
$$

又 $|xy|\le\frac{1}{2}(x^{2}+y^{2})$，即 $xy\ge-\frac{1}{2}(x^{2}+y^{2})$，故

$$
f(x,y)>\frac{1}{2}\left(c+\frac{1}{2}\right)(x^{2}+y^{2})-\frac{1}{2}(x^{2}+y^{2})=\frac{1}{2}\left(c-\frac{1}{2}\right)(x^{2}+y^{2})>0=f(0,0).
$$

所以 $f(0,0)$ 是 $f(x,y)$ 的严格极小值。

**(2)** 若 $c=\frac{1}{2}$，则 (1) 中的结论还成立吗？

**解**

不成立。取

$$
f(x,y)=xy+\frac{1}{2}(x^{2}+y^{2})-y^{3}.
$$

则

$$
\frac{f(x,y)-xy}{x^{2}+y^{2}}=\frac{1}{2}-\frac{y^{3}}{x^{2}+y^{2}},
$$

而

$$
\left|\frac{y^{3}}{x^{2}+y^{2}}\right|=|y|\cdot\frac{y^{2}}{x^{2}+y^{2}}\le|y|\to0,
$$

故该极限为 $\frac{1}{2}$，满足题设，且 $f(0,0)=0$。

沿直线 $y=-x$ 有

$$
f(x,-x)=\frac{1}{2}(x-x)^{2}-(-x)^{3}=x^{3}.
$$

当 $x>0$ 时 $f(x,-x)>0$，当 $x<0$ 时 $f(x,-x)<0$，故在 $(0,0)$ 的任意邻域内 $f$ 既有大于 $f(0,0)$ 的点，也有小于 $f(0,0)$ 的点，因此 $f(0,0)$ 不是极值。
# 三、求微分方程 $x^{2}y'+xy=y^{2}\ln x\ (x>0)$ 的全部解。
**知识点**

凑微分 $x^{2}y'+xy=x(xy)'$；变量可分离方程两边积分；分部积分。

**步骤**

$$
x^{2}y'+xy=x(xy)'\ \Longrightarrow\ x(xy)'=y^{2}\ln x\ \Longrightarrow\ (xy)'=\frac{(xy)^{2}\ln x}{x^{3}}
$$

令 $w=xy$，分离变量：

$$
\frac{\mathrm{d}w}{w^{2}}=\frac{\ln x}{x^{3}}\mathrm{d}x
$$

两边积分，其中

$$
\int\frac{\ln x}{x^{3}}\mathrm{d}x=-\frac{\ln x}{2x^{2}}-\frac{1}{4x^{2}}
$$

得

$$
-\frac{1}{xy}=-\frac{\ln x}{2x^{2}}-\frac{1}{4x^{2}}-C
$$

两边乘 $-x$：

$$
\frac{1}{y}=Cx+\frac{2\ln x+1}{4x}\ \Longrightarrow\ y=\frac{4x}{4Cx^{2}+2\ln x+1}
$$

又 $y\equiv0$ 满足原方程，亦为解。

**答案**

$$
y=\frac{4x}{4Cx^{2}+2\ln x+1}\qquad\text{及}\qquad y\equiv0\qquad(x>0)
$$

（$C$ 为任意常数，且使分母不为零。）
