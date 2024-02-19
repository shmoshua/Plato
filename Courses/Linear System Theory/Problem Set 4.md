#Series #LST 

##### Exercise 1
1. The system is non-linear due to $x_{1}(t)^{3}$ in the second equation. More formally, if we define: 
	$$\begin{bmatrix} x_{1}(t)\\x_{2}(t)\end{bmatrix}=p(x(t)):=\begin{bmatrix} x_{2}(t)\\x_{1}(t)-x_{1}(t)^{3} -x_{2}(t)\end{bmatrix}$$Then, $p:\mathbb{R}^n\to \mathbb{R}^n$ is not linear, as $p([1,0]^\top)=[0,0]^\top$ but $p([2,0]^\top)=[0,-6]^\top$ .
2. Let's compute the equilibria. We need that: $$\begin{align}\hat{x}_{2}&=0\\\hat{x}_{1}-\hat{x}_{1}^{3}-\hat{x}_{2}&=0\end{align}$$
	Therefore, $\hat{x}=[0,0]^\top$,$\hat{x}=[-1,0]^\top$ and $\hat{x}=[1,0]^\top$.
3. We will define $e_{x}(t):=x(t)-\hat{x}$, where $\hat{x}\in \mathbb{R}^2$ is an equilibrium. Then, $$\dot{e}_{x}(t)=\dot{x}(t)=p(x(t))=p(\hat{x}+e_{x}(t))$$Using Taylor approximation, we can approximate this into: $$\dot{e}_{x}(t)\approx \underbrace{ p(\hat{x}) }_{ =0 }+ \frac{ \partial p }{ \partial x } (\hat{x})e_{x}(t)= \frac{ \partial p }{ \partial x } (\hat{x})e_{x}(t)$$for small $\dot{e}_{x}(t)$. Therefore, we have a new system: $$\dot{e}_{x}(t)= Ae_{x}(t)$$where $A:= \frac{ \partial p }{ \partial x }(\hat{x})\in \mathbb{R}^{2,2}$. We have that: $$A:=\begin{bmatrix}0&1\\1-3\hat{x}_{1}^{2}&-1\end{bmatrix}$$
	- $\hat{x}=[0,0]^\top$: Then, $$A=\begin{bmatrix}0&1\\1&-1\end{bmatrix}$$has eigenvalues $\lambda= \frac{{-1 \pm \sqrt{ 5 }}}{2}$. As $\frac{-1+\sqrt{ 5 }}{2}>0$, $\hat{e}_{x}=[0,0]^\top$ is unstable in the linear system. This also shows that the equilibrium $\hat{x}$ is unstable in the original system.
	- $\hat{x}=[-1,0]^\top$ or $\hat{x}=[1,0]^\top$: Then, $$A=\begin{bmatrix}0&1\\-2&-1\end{bmatrix}$$has eigenvalues $\lambda= \frac{-1\pm 7i}{2}$ and therefore $\hat{e}_{x}=[0,0]^\top$ is stable in the resulting linear system as $\text{Re}(\lambda)=-1 /2$ for all eigenvalues $\lambda$. Therefore, $\hat{x}$ is stable.
---
##### Exercise 2
1. From the first lemma, we have $c,\rho>0$ s.t.
	1. $c\|x\|^2-x^\top P x\geq 0$
	2. $x^\top P x-\rho\|x\|^2\geq 0$
	
	Then, 
	$$\rho\|x\|^2\leq x^\top Px\leq c\|x\|^2$$for all $x\in \mathbb{R}^n$. Then, $$\frac{d}{dt}(x(t)^\top Px(t))\leq-x(t)^\top Qx(t)\leq -\lambda_{\min}(Q)\|x(t)\|^2\leq-\frac{\lambda_{\min}(Q)}{c}x(t)^\top Px(t)$$
	Using the Gronwall's lemma, we get that: $$x(t)^\top Px(t)\leq x(0)^\top Px(0)\cdot e^{\int_{0}^{t} -\frac{\lambda_{\min}(Q)}{c} \, ds }$$and
	$$\sqrt{ x(t)^\top Px(t) }\leq e^{-\mu t}\sqrt{ x(0)^\top Px(0) }$$
	
	where $\mu:= \lambda_{\min}(Q) /2c>0$ as $\lambda_{\min}(Q)>0$ from $P$ and $Q$ being spd. Therefore,$$\left\| x(t) \right\| \leq \frac{\sqrt{ x(t)^\top Px(t) }}{\sqrt{ \rho }}\leq \frac{1}{\sqrt{ \rho }}e^{-\mu t}\sqrt{ x(0)^\top Px(0) }\leq \sqrt{  \frac{c}{\rho} }e^{-\mu t}\left\| x(0) \right\| $$ 

	If $f(x)=Ax$, then $$\frac{d}{dt}(x(t)^\top P x(t))=\frac{d}{dt}x(t)^\top Px(t)+x(t)^\top P \frac{d}{dt}x(t)=x(t)^\top A^\top P x(t)+x(t)^\top PAx(t)$$Therefore, we have: $x(t)^\top(A^\top P+PA)x(t)\leq x(t)^\top(-Q)x(t)$ for all $t\in\mathbb{R}$. This condition is equivalent to $A^\top P + PA\leq-Q$.
2. Without loss of generality we can take $t_{0}=0$. Then, for $t\geq 0$, we have: $$\begin{align}\left\| x(t) \right\| &=\left\| e^{At}x_{0}+\int_{0}^{t}e^{A(t-\tau)}Bu(\tau)  \, d\tau  \right\| \\&\leq\left\| e^{At}x_{0}\right\|+\int_{0}^{t}\left\|e^{A(t-\tau)}Bu(\tau) \right\| \, d\tau  \\&\leq ce^{-\mu t}\left| x_{0} \right|+cM\|B\|\int_{0}^{t}e^{-\mu(t-\tau)} \, d\tau \\&\leq ce^{-\mu t}\left| x_{0} \right|+\frac{cM\|B\|}{\mu}(1-e^{-\mu t})  \end{align}$$
	As $0\leq e^{-\mu t}\leq 1$ for $t\geq0$, $$\sup_{0\leq t}\|x(t)\|\leq c|x_{0}|+c M\|B\| / \mu$$which shows that $x(t)$ is bounded.
3. Let $\|u\|_{0,\infty}\leq 1$. Then, for $x_{0}=0$, we have that $M=1$ and: $$\sup_{\|u\|_{0,\infty}\leq 1 }\left\| x(t) \right\| _{0,\infty}\leq \frac{c \|B\|}{\mu}$$As linear operators are continuous if bounded, this linear operator is continuous.
---
##### Exercise 3
1. Let $\hat{x}=0$ be an asymptotically stable equilibrium under zero input. Then, by Theorem 6.4, $\hat{x}$ is exponentially stable. Then, by Theorem 6.8, $$\left\| y(t) \right\| _{0,\infty}\leq m\left\| C \right\| \left\| x_{0} \right\|_{1}+\left[ \frac{m}{\alpha}\left\| C \right\| \left\| B \right\| +\left\| D \right\|  \right] \left\| u(t) \right\| _{0,\infty}$$which shows that if $u$ is bounded, $y$ is bounded, i.e. the system is BIBO secure.
2. We have that: $$\begin{align}\dot{x}(t)&=\begin{bmatrix}0&0\\0&-1\end{bmatrix}x(t)+\begin{bmatrix}1\\1 \end{bmatrix}u(t)\\y(t)&=\begin{bmatrix}1&1 \end{bmatrix}x(t)\end{align}$$
	Then, as the $\text{Spec}(A)=\{ 0,-1 \}$ we have that the system is stable. However, we have for $t_{0}=0$, $x_{0}=0$ and $u\equiv 1$, $$\rho(t,0,0,u)=\int_{0}^{t} \begin{bmatrix}1&1\end{bmatrix}\begin{bmatrix}1&0\\0&e^{-(t-\tau)}\end{bmatrix}\begin{bmatrix}1\\1\end{bmatrix} \, d\tau =\int_{0}^{t} 1+e^{-(t-\tau)} \, d\tau=t+(1-e^{-t})\to \infty $$Therefore, the system is not BIBO-stable.
---
##### Exercise 4
1. Let $z\in C$ and $y:[0,1]\to \mathcal{H}$ defined as $y(t)=tz+(1-t)P_{C}(x)$. As $z,P_{C}(x)\in C$ and $C$ is convex, we have that $y(t)\in C$ for all $t\in [0,1]$. Then, $$\begin{align}\left\| y(t)-x\right\| ^{2}&=\left\|tz+(1-t)P_{C}(x)-x \right\| ^{2}\\&=\left\| (z-P_{C}(x))t-(x-P_{C}(x)) \right\|^{2}\\&=\|z-P_{C}(x)\|^{2}t^{2}-(\braket{ z-P_{C}(x) ,x-P_{C}(x)  }+\braket{ x-P_{C}(x) ,z-P_{C}(x)  } ) t+\left\| x-P_{C}(x) \right\| ^{2}\\&=\|z-P_{C}(x)\|^{2}t^{2}-(\overline{\braket{ x-P_{C}(x) ,z-P_{C}(x)}}+\braket{ x-P_{C}(x) ,z-P_{C}(x)  } ) t+\left\| x-P_{C}(x) \right\| ^{2}\\&=\|z-P_{C}(x)\|^{2}t^{2}-2\text{Re}\braket{ x-P_{C}(x) ,z-P_{C}(x)  } t+\left\| x-P_{C}(x) \right\| ^{2}\end{align}$$Further, notice that for all $t\in[0,1]$, $$\left\| x-P_{C}(x) \right\| \leq \left\| x-y(t) \right\| $$as $y(t)\in C$ for all $t\in[0,1]$. Therefore, we get that: 
	$$0\leq t(\|z-P_{C}(x)\|^{2}t-2\text{Re}\braket{ x-P_{C}(x) ,z-P_{C}(x)  } )$$
	For all $t\in(0,1]$, as $t\geq 0$, we then have that: $$\begin{align}0&\leq\|z-P_{C}(x)\|^{2}t-2\text{Re}\braket{ x-P_{C}(x) ,z-P_{C}(x)  }\\\text{Re}\braket{ x-P_{C}(x) ,z-P_{C}(x)  }&\leq \frac{1}{2}\|z-P_{C}(x)\|^{2}t\end{align}$$By taking $t\to 0$, we have that: $$\text{Re}\braket{ x-P_{C}(x) ,z-P_{C}(x)  }\leq 0$$
	If $F=\mathbb{R}$, this means that the two vectors $x-P_{C}(x)$ and $z-P_{C}(x)$ cannot form an acute angle. If it were to form an obtuse angle, $P_{C}(x)$ will not  be the projection with the minimum distance, as we can draw a perpendicular line onto the segment $z$ to $P_{C}(x)$ from $x$, which would result in a shorter distance. 
1. From part 1, we have that: $$\text{Re}\braket{ x_{1}-P_{C}(x_{1}) ,P_{C}(x_{2})-P_{C}(x_{1})  } \leq 0$$and$$\text{Re}\braket{ x_{2}-P_{C}(x_{2}) ,P_{C}(x_{1})-P_{C}(x_{2})  } \leq 0$$Therefore, $\text{Re}\braket{ x_{1}-P_{C}(x_{1}) ,P_{C}(x_{1})-P_{C}(x_{2})  } \geq 0$ and: $$\text{Re}\braket{ (x_{1}-x_{2})-(P_{C}(x_{1})-P_{C}(x_{2})) ,P_{C}(x_{1})-P_{C}(x_{2})  } \geq 0$$It follows that: $$\begin{align}\text{Re}\braket{ x_{1}-x_{2} ,P_{C}(x_{1})-P_{C}(x_{2})  } &\geq \text{Re}\braket{ P_{C}(x_{1})-P_{C}(x_{2}),P_{C}(x_{1})-P_{C}(x_{2})  }\\&=\text{Re }\|P_{C}(x_{1})-P_{C}(x_{2})\|^{2}\\&=\|P_{C}(x_{1})-P_{C}(x_{2})\|^{2}\end{align}$$
	Then, using Cauchy-Schwarz,
	$$\begin{align}\|P_{C}(x_{1})-P_{C}(x_{2})\|^{2}&\leq\text{Re}\braket{ x_{1}-x_{2} ,P_{C}(x_{1})-P_{C}(x_{2})  } \\&\leq \left| \braket{ x_{1}-x_{2} ,P_{C}(x_{1})-P_{C}(x_{2})  }  \right|\\&=\|x_{1}-x_{2}\|\cdot \|P_{C}(x_{1})-P_{C}(x_{2})\| \end{align}$$
	From which it holds that: $$ \|P_{C}(x_{1})-P_{C}(x_{2})\|\leq\|x_{1}-x_{2}\|$$
---
