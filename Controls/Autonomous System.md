#Definition #LST 

> [!definition]
> An ***autonomous system*** is a system defined by the equation: $$\dot{x}(t)=p(x(t))$$
> for $x:\mathbb{R}\to \mathbb{R}^n$ and $p:\mathbb{R}^n\to \mathbb{R}^n$ is [[Lipschitz Function|Lipschitz]].
---
##### Stability
> [!lemma] Proposition 1
> Let $\hat{x}\in \mathbb{R}^n$ be an [[Equilibrium of a System|equilibrium]]. Then, $\hat{x}$ is stable if and only if it's uniformly stable.
---
> [!lemma] Theorem 2
> Let $\hat{x}\in \mathbb{R}^n$ be an [[Equilibrium of a System|equilibrium]] of $\dot{x}(t)=p(x(t))$. Assume that there exists a differentiable function $V:\mathbb{R}^n\to \mathbb{R}$ and $\varepsilon_{1},\varepsilon_{2}>0$ s.t. 
> 1. $V(\hat{x})=0$ and $V(x)>0$ for all $x\neq\hat{x}$ with $\left\| x-\hat{x} \right\|<\varepsilon_{1}$ and 
> 2. $\mathcal{L}_{p}V(x)\leq 0$ for all $x$ with $\left\| x-\hat{x} \right\|<\varepsilon_{2}$ where $\mathcal{L}_{p}$ denotes the [[Lie Derivative]]
> 
> Then, $\hat{x}$ is stable.

> [!proof]-
> As the system is autonomous, we will take $t_{0}=0$ without loss of generality. We can write $s(t,x_{0})$ for the solution at time $t$ starting at $(0,x_{0})$.
> 
> For $\varepsilon> 0$, we choose $\varepsilon_{3}<\min(\varepsilon,\varepsilon_{1},\varepsilon_{2})$. As $S(\hat{x},\varepsilon_{3}):=\overline{B}(\hat{x},\varepsilon_{3})\backslash B(\hat{x},\varepsilon_{3})$ is compact and $V$ is continuous, $V$ admits a minimum $m$ on $S(\hat{x},\varepsilon_{3})$. As $V$ is continuous, we have $\delta>0$ s.t. for all $x_{0}\in B(\hat{x},\delta)$, $$\left| V(x_{0})-V(\hat{x}) \right| =V(x_{0})<m$$
> 
> Choose arbitrary $x_{0}\in B(\hat{x},\delta)$ and assume that $s(T,x_{0})\notin B(\hat{x},\varepsilon_{3})$ for some $T>0$ s.t. 
> 1. $s(T,x_{0})\in S(\hat{x},\varepsilon_{3})$ and
> 2. $s(t,x_{0})\in B(\hat{x},\varepsilon_{3})$ for all $t<T$.
> 
> Then, as $\varepsilon_{3}<\varepsilon_{2}$, for all $t\leq T,$$$\mathcal{L}_{p}V(s(t,x_{0}))\leq 0$$
> It follows that the function $V(s(\cdot,x_{0}))$ is non-increasing over $[0,T]$. Then, we have: $$m\leq V(s(T,x_{0}))\leq V(s(0,x_{0}))=V(x_{0})<m$$which is a contradiction. Therefore, $s(t,x_{0})\in B(\hat{x},\varepsilon_{3})$ for all $t\geq 0$.
---
> [!lemma] Theorem 3
> Let $\hat{x}\in \mathbb{R}^n$ be an [[Equilibrium of a System|equilibrium]] of $\dot{x}(t)=p(x(t))$. Assume that there exists a differentiable function $V:\mathbb{R}^n\to \mathbb{R}$ and $\varepsilon_{1},\varepsilon_{2}>0$ s.t. 
> 1. $V(\hat{x})=0$ and $V(x)>0$ for all $x\neq\hat{x}$ with $\left\| x-\hat{x} \right\|<\varepsilon_{1}$ and 
> 2. $\mathcal{L}_{p}V(x)< 0$ for all $x\neq \hat{x}$ with $\left\| x-\hat{x} \right\|<\varepsilon_{2}$
> 
> Then, $\hat{x}$ is locally asymptotically stable.

> [!proof]-
> Since $\hat{x}$ is in equilibrium, we have that $p(\hat{x})=0$. Therefore, $\mathcal{L}_{p}V(\hat{x})=0$ and by Theorem 1, $\hat{x}$ is a stable equilibrium.
> 
> Now, to establish the local asymptotic stability, we need to show that there exists $M>0$ s.t. for all $x_{0}\in B(\hat{x},M)$, $$\lim_{ t \to \infty } s(t,x_{0})=\hat{x}$$Let $\varepsilon_{3}:=\min(\varepsilon_{1},\varepsilon)$. Let $\underline{m}:=\min\{ V(x)|x\in S(\hat{x},\varepsilon_{3}) \}$ and pick $M>0$ s.t. $V(x_{0})<\underline{m}$ for all $x_{0}\in B(\hat{x},M)$. Then, $s(t,x_{0})\in B(\hat{x},\varepsilon_{3})$ for all $t\geq 0$.
> 
> Take an arbitrary $x_{0}\in B(\hat{x},M)$ and fix $\varepsilon>0$. Since $\hat{x}$ is stable, there exists $\delta$ s.t. if $s(T,x_{0})\in B(\hat{x},\delta)$ then $s(t,x_{0})\in B(\hat{x} ,\varepsilon)$ for all $t\geq T$. Therefore, it suffices to show that there exists $T$ s.t. $s(T,x_{0})\in B(\hat{x},\delta)$. If this is not the case, then $\delta\leq \left\| s(t,x_{0})-\hat{x} \right\|\leq \varepsilon_{3}$ for all $t\geq 0$.
> 
> Since $\{ x\in \mathbb{R}^n:\delta\leq \left\| x-\hat{x} \right\|\leq \varepsilon_{3} \}$ is compact and $\mathcal{L}_{p}V$ is continuous, $\mathcal{L}_{p}V$ attains a maximum $\overline{m}<0$. Therefore, $$0\leq V(s(t,x_{0}))=V(s(0,x_{0}))+\int_{0}^{t} \frac{d}{d\tau}V(s(\tau,x_{0})) \, d\tau<V(x_{0})+\overline{m}t\to - \infty $$which is a contradiction.
---
