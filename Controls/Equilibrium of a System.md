#Definition #LST 

> [!definition]
> For a general non-linear, time varying system defined by the differential equation: $$\dot{x}(t)=p(x(t),t)$$
> for $t\in \mathbb{R}, x(t)\in \mathbb{R}^n,p:\mathbb{R}^n\times \mathbb{R}\to \mathbb{R}^n$ [[Lipschitz Function|Lipschitz continuous]] in first argument and piecewise continuous in the second. 
> 
> Let $s(t,t_{0},x_{0})$ denote the unique solution at time $t$ with the initial condition $(t_{0},x_{0})$. A state $\hat{x}\in \mathbb{R}^n$ is called an ***equilibrium*** of the system, if for all $t\in \mathbb{R}$:$$p(\hat{x},t)=0$$
> 
> An equilibrium $\hat{x}\in \mathbb{R}^n$ is called:
> 1. ***stable*** if for all $t_{0}\in \mathbb{R}$ and $\varepsilon>0$, there exists $\delta>0$ s.t. $$\|x_{0}-\hat{x}\|<\delta\implies\|s(t,t_{0},x_{0})-\hat{x}\|<\varepsilon\quad \forall t\geq t_{0}$$
> 2. ***unstable***, if it is not stable.
> 3. ***uniformly stable***, if for all $\varepsilon>0$ there exists $\delta>0$ s.t. for all $t_{0}\in \mathbb{R}$,$$\|x_{0}-\hat{x}\|<\delta\implies\|s(t,t_{0},x_{0})-\hat{x}\|<\varepsilon\quad \forall t\geq t_{0}$$
> 4. ***locally asymptotically stable***, if it is stable and for all $t_{0}\in \mathbb{R}$, there exists $M>0$ s.t. $$\left\| x_{0}-\hat{x} \right\|<M \implies \lim_{ t \to \infty } \|s(t,t_{0},x_{0})-\hat{x}\|=0 $$
> 5.  ***globally asymptotically stable***, if it is stable and for all $(t_{0},x_{0})\in \mathbb{R}\times \mathbb{R}^n$, $$\lim_{ t \to \infty } \|s(t,t_{0},x_{0})-\hat{x}\|=0 $$
> 6. ***locally exponentially stable***, if for all $t_{0}\in \mathbb{R}$, there exists $\alpha,m,M>0$ s.t. for all $t\geq t_{0}$, $$\left\| x_{0}-\hat{x} \right\|<M \implies \left\| s(t,t_{0},x_{0})-\hat{x} \right\| \leq m\left\| x_{0}-\hat{x} \right\| e^{-\alpha(t-t_{0})}$$
> 5.  ***globally exponentially stable***, if for all $t_{0}\in \mathbb{R}$, there exists $\alpha,m>0$ s.t. for all $x_{0}\in \mathbb{R}^n$ and $t\geq t_{0}$,  $$\left\| s(t,t_{0},x_{0})-\hat{x} \right\| \leq m\left\| x_{0}-\hat{x} \right\| e^{-\alpha(t-t_{0})} $$
---
##### Properties
> [!lemma] Fact 1
> If $\hat{x}\in \mathbb{R}^n$ is an equilibrium of the system, then $s(t,t_{0},\hat{x})=\hat{x}$ for all $t,t_{0}\in \mathbb{R}$.

> [!proof]-
> $$\frac{d}{dt}s(t,t_{0},x)=\frac{d}{dt}\hat{x}=0=p(\hat{x},t)=p(s(t,t_{0},\hat{x}),t)$$
---
> [!lemma] Fact 2
> We have that:
> 1. uniform stability => stability
> 2. local asymptotic stability => stability
> 3. global asymptotic stability => local asymptotic stability
> 4. local exponential stability => local asymptotic stability
> 5. global exponential stability => global asymptotic stability
> 6. global exponential stability => local exponential stability

> [!proof]
---
> [!lemma] Fact 3
> An equilibrium $\hat{x}\in \mathbb{R}^n$ is stable if and only if for all $t_{0}\in \mathbb{R}$, the function $s(t,t_{0},\cdot):\mathbb{R}^n\to C([t_{0},\infty),\mathbb{R},\mathbb{R}^n)$ is continuous at $\hat{x}$ w.r.t. infinity norm for $t\geq t_{0}$.

> [!proof]-
> Fix $t_{0}\in \mathbb{R}$ and $s(\cdot,t_{0},\cdot)$ is continuous at $\hat{x}$ if and only if for all $\varepsilon> 0$ there exists $\delta>0$ s.t. $$\|x_{0}-\hat{x}\|<\delta\implies\|s(\cdot ,t_{0},x_{0})-s(\cdot ,t_{0},\hat{x})\|_{t_{0},\infty}=\sup_{t\geq t_{0}}\|s(t ,t_{0},x_{0})-s(t ,t_{0},\hat{x})\|<\varepsilon$$
> which is equivalent to $$\|x_{0}-\hat{x}\|<\delta\implies\|s(t ,t_{0},x_{0})-\hat{x}\|<\varepsilon\quad \forall t\geq t_{0}$$which is the definition of stability.
---
> [!lemma] Fact 4
> Let $\hat{x}\in \mathbb{R}^n$ be an equilibrium to the system and assume that there exists $k>0$ s.t. for all $t\in \mathbb{R}$ and all $x,x'\in \mathbb{R}^n$, $\left\| p(x,t)-p(x',t) \right\|\leq k\|x-x'\|$. Then, for all $t_{0}\in \mathbb{R}$ and $t\geq t_{0}$, $$\left\| x_{0}-\hat{x} \right\| e^{-k(t-t_{0})}\leq \left\| s(t,t_{0},x_{0})-\hat{x} \right\| \leq \left\| x_{0}-\hat{x} \right\| e^{k(t-t_{0})}$$

> [!proof]-
> If $x_{0}=\hat{x}$, it is true. If $x_{0}\neq \hat{x}$, then $s(t,t_{0},x_{0})\neq \hat{x}$ for all $t\in \mathbb{R}$. Then, 
> $$\begin{align}\left| \frac{d}{dt}\left\| s(t,t_{0},x_{0})-\hat{x} \right\| ^{2} \right| &=\left| 2(s(t,t_{0},x_{0})-\hat{x})^\top(p(s(t,t_{0},x_{0}),t)-p(\hat{x},t))\right|\\&\leq 2\|s(t,t_{0},x_{0})-\hat{x} \|\|p(s(t,t_{0},x_{0}),t)-p(\hat{x},t)\|\\&\leq 2k\|s(t,t_{0},x_{0})-\hat{x} \|\|s(t,t_{0},x_{0})-\hat{x}\| \end{align}$$and $$\left| \frac{d}{dt}\left\| s(t,t_{0},x_{0})-\hat{x} \right\| ^{2} \right|= \left| 2\|s(t,t_{0},x_{0})-\hat{x}\| \frac{d}{dt}\left\| s(t,t_{0},x_{0})-\hat{x} \right\|  \right| $$Therefore, $$\left| \frac{d}{dt}\left\| s(t,t_{0},x_{0})-\hat{x} \right\|  \right| \leq k\|s(t,t_{0},x_{0})-\hat{x}\|$$
> From [[Gronwall Lemma]], we then have: $$\|s(t,t_{0},x_{0})-\hat{x}\|\leq\|\hat{x}-x_{0}\|e^{k(t-t_{0})}$$
> where the left hand side is proven analogously.