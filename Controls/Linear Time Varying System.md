#Definition #LST 

> [!definition]
> A ***linear time varying system*** is denoted as: $$\begin{align}\dot{x}(t)&=A(t)x(t)+B(t)u(t)\\y(t)&=C(t)x(t)+D(t)u(t)\end{align}$$where $$t\in \mathbb{R},x(t)\in \mathbb{R}^n,u(t)\in \mathbb{R}^m,y(t)\in \mathbb{R}^p$$such that
> $$\begin{align}&A(\cdot ):\mathbb{R} \to \mathbb{R}^{n,n},B(\cdot ):\mathbb{R} \to \mathbb{R}^{n,m}\\&C(\cdot ):\mathbb{R} \to \mathbb{R}^{p,n},D(\cdot ):\mathbb{R} \to \mathbb{R}^{p,m}\end{align}$$
---
##### Definition with General Vector Spaces
Let $(X,\mathbb{R}), (U,\mathbb{R})$ and $(Y,\mathbb{R})$ be finite-dimensional [[Vector Space|linear spaces]], of dimensions $n,m$ and $p$ respectively. We also fix the bases $\{ e_{i} \}_{i=1}^n$, $\{ f_{i} \}_{i=1}^j$ and $\{ g_{i} \}_{i=1}^p$. Consider the family of linear functions: 
1. $\mathcal{A}(t):X \to X$
2. $\mathcal{B}(t):U \to X$
3. $\mathcal{C}(t):X \to Y$
4. $\mathcal{D}(t):U \to Y$
   
parametrized by a real number $t\in \mathbb{R}$. This also defines matrices $A(t),B(t),C(t),D(t)$ w.r.t the bases, where we assume that $A(\cdot),B(\cdot),C(\cdot),D(\cdot)$ are piecewise continuous. Then, for all piecewise continuous $u(\cdot):\mathbb{R} \to \mathbb{R}^m$ and $(t_{0},x_{0})$ there exists a unique solution $x(\cdot)$ and $y(\cdot)$ for the following system: $$\begin{align}\dot{x}(t)&=A(t)x(t)+B(t)u(t)\\y(t)&=C(t)x(t)+D(t)u(t)\end{align}$$
The unique solution defines two functions:
1. $x(t)=s(t,t_{0},x_{0},u)$ called the ***state transition map***
2. $y(t)=\rho(t,t_{0},x_{0},u)$ called the ***output response map***

Then, we also have that $\rho(t,t_{0},x_{0},u)=C(t)s(t,t_{0},x_{0},u)+D(t)u(t)$

> [!lemma] Theorem 1
> Assume that $A(\cdot),B(\cdot),C(\cdot),D(\cdot)$ are piecewise continuous. Let $D_{x}$ denote the union of discontinuity sets of $A(\cdot),B(\cdot),u(\cdot)$ and let $D_{y}$ be the union of discontinuity sets of $C(\cdot),D(\cdot),u(\cdot)$. Then, 
> 1. For all $(t_{0},x_{0})\in \mathbb{R} \times \mathbb{R}^n$ and $u(\cdot)\in PC(\mathbb{R},\mathbb{R}^m)$:
> 	- $x(\cdot)=s(\cdot,t_{0},x_{0},u)$ is continuous and differentiable for all $t \in \mathbb{R} \backslash D_{x}$.
> 	- $y(\cdot)=\rho(\cdot,t_{0},x_{0},u)$ is piecewise continuous with discontinuity set $D_{y}$.
> 2. For all $t,t_{0}\in \mathbb{R}$, $u(\cdot)\in PC(\mathbb{R},\mathbb{R}^m)$
> 	- $s(t,t_{0},\cdot,u):\mathbb{R}^n\to \mathbb{R}^n$ is continuous.
> 	- $\rho(t,t_{0},\cdot,u):\mathbb{R}^n \to \mathbb{R}^p$ is continuous.
> 3. For all $t,t_{0}\in \mathbb{R}$, $x_{01},x_{02}\in \mathbb{R}^n, u_{1}(\cdot),u_{2}(\cdot)\in PC(\mathbb{R},\mathbb{R}^m),a_{1},a_{2}\in \mathbb{R}$:
> 	- $s(t,t_{0},a_{1}x_{01}+a_{2}x_{02},a_{1}u_{1}+a_{2}u_{2})=a_{1}s(t,t_{0},x_{01},u_{1})+a_{2}s(t,t_{0},x_{02},u_{2})$
> 	- $\rho(t,t_{0},a_{1}x_{01}+a_{2}x_{02},a_{1}u_{1}+a_{2}u_{2})=a_{1}\rho(t,t_{0},x_{01},u_{1})+a_{2}\rho(t,t_{0},x_{02},u_{2})$
> 4. For all $t,t_{0}\in \mathbb{R},x_{0}\in \mathbb{R}^n, u\in PC(\mathbb{R},\mathbb{R}^m)$:
> 	- $s(t,t_{0},x_{0},u)=s(t,t_{0},x_{0},0)+s(t,t_{0},0,u)$
> 	- $\rho(t,t_{0},x_{0},u)=\rho(t,t_{0},x_{0},0)+\rho(t,t_{0},0,u)$

> [!proof]-
> 1 is clear from definition. We will now show 3. Then, the rest follows. Let:
>   -  $x_{1}(t):=s(t,t_{0},x_{01},u_{1})$
>   - $x_{2}(t):=s(t,t_{0},x_{02},u_{2})$ 
>   - $x(t)=s(t,t_{0},a_{1}x_{01}+a_{2}x_{02},a_{1}u_{1}+a_{2}u_{2})$ 
>   - $\phi(t)=a_{1} x_{1}(t)+a_{2} x_{2}(t)$
>     
>   Then, we need to show $\phi(t)=x(t)$ for all $t\in \mathbb{R}$. By definition, $$x(t_{0})=a_{1}x_{01}+a_{2}x_{02}=a_{1}x_{1}(t_{0})+a_{2}x_{2}(t_{0})=\phi(t_{0})$$
>   Moreover, if we let $u(t)=a_{1}u_{1}(t)+a_{2}u_{2}(t)$, then for all $t\in \mathbb{R} \backslash D$
>   $$\begin{align}\dot{x}(t)&=A(t)x(t)+B(t)u(t)\\ \dot{\phi}(t)&=a_{1}\dot{x_{1}}(t)+a_{2}\dot{x}_{2}(t)\\&=a_{1}(A(t)x_{1}(t)+B(t)u_{1}(t))+a_{2}(A(t)x_{2}(t)+B(t)u_{2}(t))\\&=A(t)(a_{1}x_{1}(t)+a_{2}x_{2}(t))+B(t)(a_{1}u_{1}(t)+a_{2}u_{2}(t))\\&=A(t)\phi(t)+B(t)u(t)\end{align}$$
>   Therefore, $x(t)=\phi(t)$ by the uniqueness of linear ODE. 
---


##### Linearization of a non-linear trajectory
Consider the non-linear system modeled by the [[Ordinary Differential Equation|ODE]]$$\begin{align}\dot{x}(t)&=f(x(t),u(t))\\y(t)&=h(x(t),u(t))\end{align}$$where $t\in \mathbb{R},x(t)\in \mathbb{R}^n,u(t)\in U \subseteq\mathbb{R}^m, f:\mathbb{R}^n \times U \to \mathbb{R}^n$. To ensure that a solution exists for the system, assume that $f$ is [[Lipschitz Function|globally Lipschitz]] w.r.t. first argument and continuous w.r.t. 2nd argument. Then, we will restrict ourselves to input trajectories $u(\cdot):\mathbb{R} \to U$ that are piecewise continuous. 

Assume that we want a minimum effort solution for following optimization problem: $$\begin{align}\min_{\begin{subarray}{r} \ x(\cdot ):[0,T]\to  \mathbb{R}^n\text{ continuous}\\u(\cdot ):[0,T]\to U\text{ piecewise continuous}\end{subarray}}&&&\int_{0}^{T} \ell(x(t),u(t)) \, dt \\\text{subject to}\qquad\quad&&&x(0)=x_{0}\\&&&x(T)=x_{F}\\&&&\dot{x}(t)=f(x(t),u(t))\end{align}$$
where $x_{0}$ and $x_{F}$ are given points.

---
##### Stability

> [!lemma] Theorem 2
> For a time-varying linear system, the equilibrium $\hat{x}=0$ is: 
> 1. stable if and only if there exists $K>0$ s.t. $\left\| \Phi(t,0) \right\|\leq K$ for all $t\geq 0$.
> 2. locally asymptotically stable if and only if $\lim_{ t \to \infty }\|\Phi(t,0)\|=0$.

> [!proof]-
> We show that: 
> 1. wlog assume that we have $K>1$ s.t. $\left\| \Phi(t,0) \right\|\leq K$ for all $t\geq 0$. Fix $t_{0}\in \mathbb{R}$ and we have: 
> 	1. $t_{0}<0$, in this case, let $M(t_{0})=\sup_{\tau\in[t_{0},0]}\left\| \Phi(\tau,t_{0}) \right\|$. Then, if $t_{0}\leq t\leq 0$: $$\left\| s(t,t_{0},x_{0}) \right\| \leq \left\| \Phi (t,t_{0})\right\| \left\| x_{0} \right\| \leq M(t_{0})\left\| x_{0} \right\| $$if $t>0$, then: $$\left\| s(t,t_{0},x_{0}) \right\| =\left\| \Phi(t,0)\Phi(0,t_{0})x_{0} \right\| \\\leq KM(t_{0})\|x_{0}\|$$
> 	2. $t_{0}\geq 0$, in this case, let $M(t_{0})=\left\| \Phi(0,t_{0}) \right\|$. Then, for $t\geq t_{0}\geq0$: $$\left\| s(t,t_{0},x_{0}) \right\|\leq KM(t_{0})\|x_{0}\|$$
> 
>    In all cases, we have: $$\|s(t,t_{0},x_{0})\|_{t_{0},\infty}\leq KM(t_{0})\|x_{0}\|$$
>    Therefore, the solution function is bounded and therefore continuous. This means that $\hat{x}=0$ is stable by [[Equilibrium of a System|Fact 3]].
>    
>    Conversely, if $\|\Phi(t,0)\|$ is unbounded, then $\hat{x}=0$ cannot be stable. For $\varepsilon=1$, we have that for all $\delta>0$, if we choose $K=2/\delta$, then there exists $t$ s.t. $\|\Phi(t,0)\|>K$. Therefore, there exists $x\in \mathbb{R}^n$ s.t. $\|x\|=1$ and $\|\Phi(t,0)x\|>K$. Let $x_{0}=x \delta/2$. Then, $$\left\| s(t,0,x_{0}) \right\| =\left\| \Phi(t,0)x \delta /2 \right\|>K \delta /2\geq 1 $$
>  2. Assume that $\lim_{ t \to \infty }\left\| \Phi(t,0) \right\|=0$. For all $(t_{0},x_{0})$: $$\left\|s(t,t_{0},x_{0})  \right\|=\left\| \Phi(t,t_{0})x_{0} \right\| \leq \left\| \Phi(t,0) \right\| \left\| \Phi(0,t_{0})x_{0} \right\|  $$
> 	 Therefore, for all $(t_{0},x_{0})$, the second term is constant and $\lim_{ t \to \infty }\|s(t,t_{0},x_{0})\|=0$. It follows that it suffices to show that $\hat{x}$ is stable. Note that the function $\left\| \Phi(\cdot,0) \right\|:\mathbb{R}_{+}\to \mathbb{R}$ is continuous and bounded as it converges to 0. 
> 	 
> 	 Thus, $\hat{x}$ is locally asymptotically stable.
> 	
> 	 Conversely, assume that $\hat{x}$ is locally asymptotically stable. Then, there exists $M>0$ s.t. for all $(t_{0},x_{0})$ with $\|x_{0}\|<M$, $$\lim_{ t \to \infty } \|s(t,t_{0},x_{0})\|\leq\lim_{ t \to \infty } \|\Phi(t,0)\|\|\Phi(0,t_{0})x_{0}\|=0$$Therefore, $\lim_{ t \to \infty }\|\Phi(t,0)\|=0$.
---

> [!lemma] Fact 3
> For a time-varying linear system, the equilibrium $\hat{x}=0$ is: 
> 1. globally asymptotically stable if and only if it is locally asymptotically stable
> 2. globally exponentially stable if and only if it is locally exponentially stable

> [!proof]-
> For 1, global => local is trivial. For the converse, we have $\lim_{ t \to \infty }\left\| \Phi(t,0) \right\|=0$ from Theorem 2. Therefore, for any $(t_{0},x_{0})$, $$\lim_{ t \to \infty }\left\| s(t,t_{0},x_{0}) \right\| \leq \lim_{ t \to \infty } \left\| \Phi(t,0) \right\| \left\| \Phi(0,t_{0}) \right\| \left\| x_{0} \right\| =0 $$which shows the global asymptotic stability.
> 
> For 2, 
---
