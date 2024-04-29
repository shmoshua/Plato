#Definition #LST 

> [!definition]
> A ***time invariant linear system*** is denoted as: $$\begin{align}\dot{x}(t)&=Ax(t)+Bu(t)\\y(t)&=Cx(t)+Du(t)\end{align}$$where $$t\in \mathbb{R},x(t)\in \mathbb{R}^n,u(t)\in \mathbb{R}^m,y(t)\in \mathbb{R}^p$$and $A\in \mathbb{R}^{n,n},B\in \mathbb{R}^{n,m},C\in\mathbb{R}^{p,n},D\in \mathbb{R}^{p,m}$.
---
##### Properties

> [!lemma] Theorem 1
> For all $t,t_{0}\in \mathbb{R}$, the [[State Transition Matrix|state transition matrix]] $$\Phi(t,t_{0})=e^{ A(t-t_{0}) }$$

> [!proof]-
> We have that, at $t=t_{0}$, $e^{ A(t-t_{0}) }=I$ and for all $t\in \mathbb{R}$:
> $$\frac{d}{dt}  e^{ A(t-t_{0}) }=\frac{d}{dt} \sum_{n=0}^{\infty} \frac{A^n(t-t_{0})^n}{n!}=\sum_{n=1}^{\infty} \frac{A^n(t-t_{0})^{n-1}}{(n-1)!}=A\sum_{n=0}^{\infty} \frac{A^n(t-t_{0})^n}{n!}=Ae^{A(t-t_{0})}$$
> Therefore, from the uniqueness of linear ODEs, $\Phi(t,t_{0})=e^{A(t-t_{0})}$.
---
> [!lemma] Corollary 2
> A time invariant linear system has following properties:
> 1. For all $t,t_{0},t_{1}\in \mathbb{R}$, $$e^{ At_{0} }e^{ At_{1} }=e^{ A(t_{0}+t_{1}) },\quad (e^{ At })^{-1}=e^{ -At }$$
> 2. For all $t,t_{0}\in \mathbb{R}$: $$\Phi(t,t_{0})=\Phi(t-t_{0},0)$$
> 3. For all $t,t_{0}\in \mathbb{R}, x_{0}\in \mathbb{R}^n,u(\cdot)\in PC(\mathbb{R}, \mathbb{R}^m)$: $$\begin{align}s(t,t_{0},x_{0},u)&=e^{ A(t-t_{0}) }x_{0}+\int_{t_{0}}^{t} e^{ A(t-\tau) }Bu(\tau) \, d\tau\\ \rho(t,t_{0},x_{0},u)&=Ce^{ A(t-t_{0}) }x_{0}+C\int_{t_{0}}^{t} e^{ A(t-\tau) }Bu(\tau) \, d\tau +Du(t) \end{align}$$
> 4. For all $t,\sigma\in \mathbb{R}$, $$\begin{align}K(t,\sigma)&=K(t-\sigma,0)=\begin{cases}e^{ A(t-\sigma) }B&t\geq \sigma\\0&t<\sigma\end{cases}\\H(t,\sigma)&=H(t-\sigma,0)=\begin{cases}Ce^{ A(t-\sigma) }B+D\delta_{0}(t-\sigma)&t\geq\sigma\\0&t<\sigma\end{cases}\end{align}$$

> [!proof]-
> We have that: 
> 1. $$e^{At_{0}}e^{ At_{1} }=\Phi(t_{0},0)\Phi(0,-t_{1})=\Phi(t_{0},-t_{1})=e^{A(t_{0}+t_{1}) }$$ and $$(e^{ At })^{-1}=\Phi(t,0)^{-1}=\Phi(0,t)=e^{-At}$$
> 2. For all $t,t_{0}\in \mathbb{R}$, $$\Phi(t,t_{0})=e^{ A(t-t_{0}) }=\Phi(t-t_{0},0)$$
> 3. Direct application of [[State Transition Matrix|Theorem 2]].
> 4. Direct application of definition.
---
> [!lemma] Lemma 3
> For linear time invariant systems, the solution is invariant to the initial time $t_{0}$, but only on the elapsed time $t-t_{0}$. Therefore, wlog we can take $t_{0}=0$ and get: 
> $$\begin{align}x(t)&=s(t,0,x_{0},u)=e^{At}x_{0}+\int_{0}^{t} e^{ A(t-\tau) }Bu(\tau) \, d\tau\\y(t)&=\rho(t,0,x_{0},u)=Ce^{ At }x_{0} +C\int_{0}^{t} e^{ A(t-\tau) }Bu(\tau) \, d\tau +Du(t) \\K(t)&=K(t,0)=\begin{cases}e^{ At }B&t\geq 0\\0&t<0\end{cases}\\H(t)&=H(t,0)=\begin{cases}Ce^{At}B+D\delta_{0}(t)&t\geq 0\\0&t<0\end{cases}\end{align}$$
> In other words, we have:
> $$\begin{align}x(t)&=e^{ At }x_{0} +(K*u)(t)\\y (t)&=Ce^{ At }x_{0}+(H *u)(t)\end{align}$$
> where $*$ denotes the [[Convolution (Rn)]].

> [!proof]-
> We have: $$\begin{align}(K*u)(t)=\int_{-\infty}^{\infty} K(t-\tau)u(\tau) \, d\tau &=\int_{0}^{t}e^{ A(t-\tau) }Bu(\tau)  \, d\tau \\(H*u)(t)=\int_{-\infty}^{\infty} H(t-\tau)u(\tau) \, d\tau &=\int _{0}^t Ce^{ A(t-\tau) }Bu(\tau)+D\delta_{0}(t-\tau)u(\tau) \, d\tau\\&=C\int _{0}^t e^{ A(t-\tau) }Bu(\tau)\, d\tau +Du(t) \end{align}$$
---
##### Time-invariant Linear Systems and Laplace Transform
We can take the [[Laplace Transform]] on both sides of the equation to get: $$sX(s)-x(0)=AX(s)+BU(s)$$
	Therefore, $X(s)=(sI-A)^{-1}(x(0)+BU(s))$. Similarly, if we take Laplace on the equation in Lemma 3, $$X(s)=(sI-A)^{-1}x_{0}+(sI-A)^{-1}BU(s)$$
If we took the Laplace transform on the output equation, $$Y(s)=CX(s)+DU(s)=C(sI-A)^{-1}x_{0}+C(sI-A)^{-1}BU(s)+DU(s)$$If $x_{0}=0$, then:$$Y(s)=(\underbrace{ C(sI-A)^{-1}B+D }_{ =:G(s) })U(s)$$
where $G(s)$ is called the ***transfer function of the system***.

---
##### Stability
> [!lemma] Theorem 4
> For a time-invariant linear system, the following statements are equivalent: 
> 1. $\hat{x}=0$ is an asymptotically stable equilibrium.
> 2. $\hat{x}=0$ is an exponentially stable equilibrium.
> 3. for all $\lambda\in \text{Spec}(A)$, $\text{Re}(\lambda)<0$.

> [!proof]-
> > [!lemma] Lemma 
> > For all $\varepsilon>0$ there exists $m>0$ s.t. for all $t\in \mathbb{R}_+$$$\left\| e^{At} \right\|\leq me^{(\mu+\varepsilon)t} $$where $\mu:=\max\{\text{Re}(\lambda):\lambda\in \text{Spec}(A)\}$.
> 
> > [!proof]-
> > From Jordan canonical form, we have: $$e^{At}=\sum_{\lambda\in \text{Spec}(A)}^{}\Pi_{\lambda}(t)e^{\lambda t}$$Then, $$\begin{align}\left\| e^{At} \right\|_{\infty}=\left\| \sum_{\lambda\in \text{Spec}(A)}^{}\Pi_{\lambda}(t)e^{\lambda t} \right\| _{\infty}\leq \sum_{\lambda\in \text{Spec}(A)}^{}\|\Pi_{\lambda}(t)e^{\lambda t}\|_{\infty}\leq \sum_{\lambda\in \text{Spec}(A)}^{}\|\Pi_{\lambda}(t)\|_{\infty}|e^{\lambda t}| \\\leq \left( \sum_{\lambda\in \text{Spec}(A)}^{}\|\Pi_{\lambda}(t)\|_{\infty} \right)e^{\mu t}\end{align}$$
> - (2 => 1): is from [[Equilibrium of a System]]
> - (3 => 2): If all eigenvalues have a negative real part, then: $$\mu:=\max\{\text{Re}(\lambda):\lambda\in \text{Spec}(A)\}<0$$Therefore, there exists $m>0$ s.t. $$\left\| e^{At} \right\|\leq me^{-\alpha t}$$Then, for all $(t_{0},x_{0})$ and $t\geq t_{0}$,$$\left\| s(t,t_{0},x_{0}) \right\| =\left\| e^{A(t-t_{0})}x_{0} \right\| \leq \left\| e^{A(t-t_{0})}\right\|\left\| x_{0} \right\| \leq m\left\| x_{0} \right\| e^{-\alpha(t-t_{0})}$$
> - (1 => 3): Assume there exists $\lambda\in \text{Spec}(A)$ s.t. $\text{Re}(\lambda)\geq 0$ and let $v\in \mathbb{C}^n$ denote the corresponding eigenvector. Wlog we take $t_{0}=0$ and $$s(t,0,v)=e^{\lambda t}v$$
> 
>   If $\lambda$ is real, then, $\|s(t,0,v)\|=|e^{\lambda t}|\|v\|$ and the system is either constant or diverges. Therefore, it cannot be asymptotically stable.
>   
>   If $\lambda$ is complex, 
---
> [!lemma] Theorem 5
> For a time-invariant linear system, $\hat{x}=0$ is a stable equilibrium if and only if: 
> 1. for all $\lambda\in \text{Spec}(A)$, $\text{Re}(\lambda)\leq 0$.
> 2. the algebraic and geometric multiplicity of all $\lambda\in \text{Spec}(A)$ with $\text{Re}(\lambda)=0$ are equal.