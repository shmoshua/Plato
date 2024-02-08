#LST #Series 

##### Exercise 1
We will show that the induced norm satisfies the three norm axioms. 
1. Triangle inequality: for $\mathcal{F},\mathcal{G}:U \to V$, using the definitions and the triangle inequality of $\|\cdot\|_{V}$, 
	$$\begin{align}\left\| \mathcal{F}+\mathcal{G} \right\| &=\sup_{u\in U:u \neq \theta_{U}} \frac{\left\| \mathcal{F}(u)+\mathcal{G}(u) \right\|_{V}}{\|u\|_{U}} \\&\leq\sup_{u\in U:u \neq \theta_{U}} \frac{\left\| \mathcal{F}(u)\right\|_{V}+\left\|\mathcal{G}(u) \right\|_{V}}{\|u\|_{U}} \\&\leq \sup_{u\in U:u \neq \theta_{U}} \frac{\left\| \mathcal{F}(u)\right\|_{V}}{\|u\|_{U}}+\sup_{u\in U:u \neq \theta_{U}} \frac{\left\| \mathcal{G}(u)\right\|_{V}}{\|u\|_{U}}=\|\mathcal{F}\|+\|\mathcal{G}\|\end{align}$$
2. Absolute homogeneity: for all $\mathcal{F}:U \to V$ and $a\in F$: $$\left\|  a\mathcal{F} \right\| =\sup_{u\in U:u \neq \theta_{U}} \frac{\left\| a\mathcal{F}(u) \right\| _{V}}{\|u\|_{U}}=\sup_{u\in U:u \neq \theta_{U}} \frac{|a|\left\| \mathcal{F}(u) \right\| _{V}}{\|u\|_{U}}=|a|\cdot \sup_{u\in U:u \neq \theta_{U}} \frac{\left\| \mathcal{F}(u) \right\| _{V}}{\|u\|_{U}}=|a|\cdot \left\| \mathcal{F} \right\| $$
3. Positive definiteness: If $\left\|  \mathcal{F} \right\|=0$, then as $\|\cdot\|_{V}$ and $\|\cdot\|_{U}$ are both positive definite, for any $u\in U$ with $u\neq\theta_{U}$:$$0\leq\frac{\left\| \mathcal{F}(u) \right\|_{V}}{\|u\|_{U}}\leq \left\| \mathcal{F} \right\| =0$$Therefore, $\left\| \mathcal{F}(u) \right\|_{V}=0$ and consequently $\mathcal{F}(u)=\theta_{V}$. As $\mathcal{F}$ is continuous, we also have that $\mathcal{F}(\theta_{U})=\theta_{V}$ and $\mathcal{ F}$ is the constant function $\theta_{V}$, therefore the neutral element. 
   
	Conversely, if $\mathcal{ F}=0$, i.e. for any $u\in U$, $\mathcal{F}(u)=\theta_{V}$, then, for any $u\in U$, $\|\mathcal{ F}(u)\|_{V}=0$. Therefore, the supremum $\left\|  \mathcal{F} \right\|=0$.
---
##### Exercise 2
We will show that the system satisfies the Theorem 3.6. We have: 
$$\dot{x}(t)=p(x(t),t):=\begin{bmatrix}p_{1}(x(t),t)\\p_{2}(x(t),t)\end{bmatrix}=\begin{bmatrix}-x_{1}(t)+e^t\cos(x_{1}(t)-x_{2}(t))\\ -x_{2}(t)+\sin(x_{1}(t)-x_{2}(t))\end{bmatrix}$$
Then, for all $y\in \mathbb{R}^2$, $p_{1}(y,\cdot)$ is a continuous function, as $e^t$ is continuous and $p_{1}(y,\cdot)$ is an affine transformation of $e^t$. Further, $p_{2}(y,\cdot)$ is a constant function and therefore continuous. In total, $p$ is continuous with respect to its second argument. 

Moreover, for all $x,x'\in\mathbb{R}^2$ and $t\in \mathbb{R}$, we have:

$$\begin{align}\left| p_{1}(x,t)-p_{1}(x',t) \right|&= \left| -(x_{1}-x'_{1})+e^t(\cos(x_{1}-x_{2})-\cos(x'_{1}-x'_{2})) \right|\\&\leq \left| x_{1}-x'_{1} \right|+\left| 2e^t \sin \frac{x_{1}-x_{2}+x'_{1}-x'_{2}}{2}\sin \frac{(x_{1}-x'_{1})-(x_{2}-x'_{2})}{2} \right| \\&\leq \left| x_{1}-x'_{1} \right|+\left| 2e^t \sin \frac{(x_{1}-x'_{1})-(x_{2}-x'_{2})}{2} \right| \\&\leq \left| x_{1}-x'_{1} \right|+\left| e^t(x_{1}-x'_{1})-(x_{2}-x'_{2})\right|\\&\leq \left| x_{1}-x'_{1} \right|+|e^t|(\left| x_{1}-x'_{1}\right|+\left|x_{2}-x'_{2}\right|)\\&\leq (1+\left| e^t \right| ) \|x-x'\|_{1} \end{align}  $$
and $$\begin{align}\left| p_{2}(x,t)-p_{2}(x',t) \right| &=\left| -(x_{2}-x'_{2})+\sin(x_{1}-x_{2})-\sin(x'_{1}-x'_{2}) \right| \\&\leq \left| x_{2}-x'_{2} \right| +\left| 2\cos \frac{x_{1}-x_{2}+x'_{1}-x'_{2}}{2}\sin \frac{(x_{1}-x'_{1})-(x_{2}-x'_{2})}{2} \right| \\&\leq \left| x_{2}-x'_{2} \right| +\left| 2\sin \frac{(x_{1}-x'_{1})-(x_{2}-x'_{2})}{2} \right|  
\\&\leq \left| x_{2}-x'_{2} \right| +\left|(x_{1}-x'_{1})-(x_{2}-x'_{2})\right| \\&\leq 2\|x-x'\|_{1}\end{align}$$
Therefore, we have:
$$\|p(x,t)-p(x',t)\|_{1}=|p_{1}(x,t)-p_{1}(x',t)|+\left| p_{2} (x,t)-p_{2}(x',t)\right| \leq(3+|e^t|)\left\| x-x' \right\| _{1} $$
It follows that $p$ is globally Lipschitz with respect to the first argument with Lipschitz constant as $$k(t):=3+\left| e^t \right| $$


---
##### Exercise 3
For any $n\in \mathbb{N}$, 
$$\left\| f_{n} \right\| _{1}= \int_{0}^{1/n}  (n-n^2x ) \, dx =1- \frac{1}{2}=\frac{1}{2}$$
$$\left\| f_{n} \right\| _{2}=\sqrt{ \int_{0}^{1/n}  (n-n^2x )^{2} \, dx }  =\sqrt{ n-n+\frac{n}{3} }=\sqrt{ \frac{n}{3} }$$
$$\left\| f_{n} \right\| _{\infty}=\max_{x\in[0,1/n]} (n-n^2x ) =n$$as $n^2>0$. 

Therefore, for $n$, the norms have pairwise different order of magnitude. This means there cannot exist constants $m_{u}\geq m_{l}>0$ s.t. $m_{l}\left\| f_{n} \right\|_{j}\leq\|f_{n}\|_{i}\leq m_{u} \left\| f_{n} \right\|_{j}$ for any two norms from above. It follows that none of these three norms are equivalent. 

---
##### Exercise 4
1. Let $t\in \mathbb{R}$. Then, we have:
	$$\begin{align}\left\| x(t)-\bar{x} \right\| &=\left\| x(t)-x_{0}+x_{0}-\bar{x} \right\| \\&\leq \left\| x(t)-x_{0} \right\| +\left\| x_{0}-\bar{x} \right\| &&|\text{ triangle inequality}\\&=\left\| x(t)-x(0) \right\| +\left\| x_{0}-\bar{x} \right\|&&|\  x_{0}=x(0)\\&=\left\| \int_{0}^{t} \dot{x}(\tau) \, d\tau  \right\| +\left\| x_{0}-\bar{x} \right\| &&|\text{ Fundamental Theorem of Calc.}\\&=\left\| \int_{0}^{t} f(x(\tau)) \, d\tau  \right\| +\left\| x_{0}-\bar{x} \right\|&&|\ \dot{x}=f(x)\text{}\\&\leq \left| \int_{0}^{t} \left\| f(x(\tau)) \right\|  \, d\tau  \right| +\left\| x_{0}-\bar{x} \right\| &&|\text{ Fact 3.7}\\&=\left| \int_{0}^{t} \left\| f(x(\tau)) -f(\bar{x})\right\|  \, d\tau  \right| +\left\| x_{0}-\bar{x} \right\| &&|\ f(\bar{x})=0\\&\leq\left| \int_{0}^{t} K\left\| x(\tau) -\bar{x}\right\|  \, d\tau  \right| +\left\| x_{0}-\bar{x} \right\|  &&|\ f\text{ is Lipschitz}\end{align}$$
Therefore, we can use the Grönwall lemma for $u(t):=\left\| x(t)-\bar{x} \right\|$, $k(t):=K$ and $c_{1}:=\left\| x_{0} -\bar{x}\right\|_{}$. Then, for all $t\in \mathbb{R}$, $$\left\| x(t)-\bar{x} \right\| \leq \exp \left( \left| \int_{0}^{t} K \, d\tau  \right|  \right)\left\| x_{0}-\bar{x} \right\| $$
	For all $t\geq 0$, it follows that: 
	$$\left\| x(t)-\bar{x} \right\| \leq \exp \left( \int_{0}^{t} K \, d\tau  \right)\left\| x_{0}-\bar{x} \right\| =\exp \left( Kt \right)\left\| x_{0}-\bar{x} \right\| $$
2. Assume we have two different solutions $\phi,\psi:\mathbb{R}_{+}\to \mathbb{R}^n$. Then, we have:
	$$\begin{align}\frac{d}{d\tau}(\phi(\tau)-\psi(\tau))&=A(\tau)\phi(\tau)-A(\tau)\psi(\tau)\\&=A(\tau)(\phi(\tau)-\psi(\tau))\end{align}$$By taking the integral and the norm on both sides, 
	$$\begin{align}\left\| \phi(t)-\psi(t) \right\| &=\left\| \int_{0}^{t}  A(\tau)(\phi(\tau)-\psi(\tau))\, d\tau \right\| \\&\leq\left| \int_{0}^{t}  \left\| A(\tau)(\phi(\tau)-\psi(\tau)) \right\| \, d\tau \right| \\&\leq\left| \int_{0}^{t}  \left\| A(\tau)\right\|\left\|\phi(\tau)-\psi(\tau) \right\| \, d\tau \right| \\&\leq\left| \int_{0}^{t}  \left\| A(\tau)\right\|\left\|\phi(\tau)-\psi(\tau) \right\| \, d\tau \right| +c_{1}\end{align} $$for every $c_{1}\geq 0$. As $\left\| A(t) \right\|$ and $\left\| \phi(t)-\psi(t) \right\|$ are piecewise continuous, using Grönwall lemma, we have: $$\begin{align}\left\|  \phi(t)-\psi(t)\right\|\leq c_{1}\exp \left| \int_{0}^t \left\| A(\tau) \right\| \, d\tau  \right|  \end{align}$$As the exponent is bounded for all $t$, we have that $0 \leq\left\| \phi(t)-\psi(t) \right\|\leq 0$ and $\left\| \phi(t)-\psi(t) \right\|=0$. This implies that $\phi(t)-\psi(t)=0$, i.e. $\phi(t)=\psi(t)$ for all $t\in \mathbb{R_{+}}$. This contradicts that $\phi\neq\psi$. Therefore, the solution is unique.
---
##### Exercise 5
1. For any $u,v\in L_{2}$ and $a,b\in \mathbb{C}$, we have that: 
	$$\begin{align}\mathcal{G}(au+bv)&=\int_{-\infty}^{+\infty} (au(t)+bv(t) ) e^{-j\omega t} \, dt=a\int_{-\infty}^{+\infty}  u(t)e^{-j\omega t}\, dt+b\int_{-\infty}^{+\infty}  v(t)e^{-j\omega t}\, dt =a\mathcal{G}(u)+b\mathcal{G}(v)\end{align}$$
2. Let $u\in L_{2}$ s.t. $\|u\|_{L_{2}}=1$. Then,
	$$\left\| \mathcal{G}(u) \right\| _{L_{2}}=\left\| U(\omega )\right\|_{L_{2}}=\left( \int_{-\infty}^{\infty}  \overline{U(\omega)}^\top U(\omega)\, d\omega   \right)^{1/2}=\sqrt{ 2\pi }\|u\|_{L_{2}}=\sqrt{ 2\pi }$$
	Therefore, the induced norm of $\mathcal{ G}$ is:
		$$\left\| \mathcal{G} \right\|_{L_{2}}=\sup_{u\in L_{2}, \|u\|_{L_{2}}=1}\left\| \mathcal{G}(u) \right\|_{L_{2}} =\sqrt{ 2\pi }$$
---