#Series #FunctionalAnalysis 

##### Problem 2
Fix $\varepsilon>0$. Then, we have: $$\left\| \frac{x+y}{2} \right\| ^2=\frac{\|x\|^{2}}{2}+\frac{\|y\|^{2}}{2}-\left\| \frac{x-y}{2} \right\| ^{2} <1-\frac{\varepsilon^{2}}{4}$$
Therefore, $\delta(\varepsilon):=1-\sqrt{ 1-\frac{\varepsilon^{2}}{4} }$

---
##### Problem 3
We have that: $$f(t)=\|z-tx-(1-t)y\|^2=\|z-y-t(x-y)\|^2=\|z-y\|^2+2t\text{Re}\braket{ z-y , y-x }+t^2\|y-x\|^2 $$Then, $f''(t)=2\|y-x\|^2>0$. Therefore, $f$ is strictly convex.

---
##### Problem 4
Let $x\in \mathcal{H}$. By shifting the whole system by $-x$, we can assume that $x=0$. Let $(x_{n})_{n}\subseteq C$ be a sequence with $\lim_{ n \to \infty }d(0,x_{n})=\lim_{ n \to \infty }\|x_{n}\|=d(0,C)$. Then, assume that $(x_{n})_{n}$ is not Cauchy, i.e. for some $\varepsilon>0$ it holds that for all $N\in \mathbb{N}$, there exists $n,m \geq N$ s.t. $$\left\| x_{n}-x_{m} \right\| > \varepsilon $$ Let $\delta>0$ and $N>0$ s.t. $\|x_{n}\|-d(0,C)<\delta$ for all $n\geq N$. As $C$ is convex, $d(0,C) \leq \left\| \frac{x_{n}+x_{m}}{2} \right\|$ and, $$d(0,C)^{2}\leq \left\| \frac{x_{n}+x_{m}}{2} \right\|^{2}=\frac{1}{2}(\|x_{n}\|^2+\|x_{m}\|^2)-\left\| \frac{x_{n}-x_{m}}{2} \right\|^{2}  <(d(0,C)+\delta)^2-\frac{\varepsilon^{2}}{4}$$By letting $\delta \to 0$, we have $0 < -\frac{\varepsilon^{2}}{4}$ which is a contradiction. 

Further, let $x_{1},x_{2}$ s.t. $d(x,x_{1})=d(x,C)=d(x,x_{2})$. Assume that $x_{1} \neq x_{2}$. Then, by exercise 3, $f(t)=\left\| x-c(t) \right\|^2=d(x,c(t))^2$ is strongly convex. However, as $C$ is convex, $\frac{x_{1}+x_{2}}{2}\in C$. Therefore, 
$$d(x,C)\leq d\left( x,\frac{x_{1}+x_{2}}{2} \right) <\frac{d(x,x_{1})+d(x,x_{2})}{2}=d(x,C)$$
which is a contradiction. This proves that $x_{1}=x_{2}$.

---
##### Problem 5
Let $(f_{n})_{n}\subseteq \Lambda^\alpha(\mathbb{R})$ be a Cauchy sequence of functions. Then, for all $x\in \mathbb{R}$, $\lim_{ n \to \infty }f_{n}(x)$ exists, as $$\left| f_{n}(x)-f_{m}(x) \right| \leq \left\| f_{n}-f_{m} \right\| _{\Lambda^\alpha}$$
Therefore, we can define $f(x):=\lim_{ n \to \infty }f_{n}(x)$. We first show that $f\in \Lambda^\alpha(\mathbb{R})$. As $(f_{n})_{n}$ is Cauchy, there exists $C>0$ s.t. $\left\| f_{n} \right\|_{\Lambda^\alpha}<C$ for all $n\in \mathbb{N}$. Then, we have that for all $y,z\in \mathbb{R}$ $$\left| f_{n}(y)-f_{n}(z) \right| <C \left| y-z \right| ^\alpha$$ It follows that $\left| f(y)-f(z) \right|<C\left| y-z \right|^\alpha$. Similarly, $\left| f(x) \right|<C$. Therefore, $f\in \Lambda^\alpha$.

For $\varepsilon>0$, we have $$\left\| f_{n}-f \right\| _{\Lambda^\alpha}=$$

---
##### Problem 6
---

