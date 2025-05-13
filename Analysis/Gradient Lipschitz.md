#Definition #AGAO 

> [!definition]
> Let $f:X\to \mathbb{R}$ be a differentiable function where $X\subseteq \mathbb{R}^n$ is convex, open. 
> 1. $f$ is ***$\beta$-gradient Lipschitz/$\beta$-smooth*** if for all $x,y\in X$, $$\left\| \nabla f(x)-\nabla f(y) \right\| _{2}\leq \beta \left\| x-y \right\| _{2}$$

---
##### Properties
> [!lemma] Proposition 1
> Let $f\in C^2(X)$. Then,
> 1. $f$ is $\beta$-gradient Lipschitz if and only if $\left\| \nabla^{2}f(x) \right\|\leq \beta$ for all $x\in X$.
---
> [!lemma] Proposition 2
> Let $f:X\to \mathbb{R}$ be $\beta$-gradient Lipschitz. 
> 1. for all $x,y\in X$, $$f(y)\leq f(x)+\nabla f(x)^\top(y-x)+\frac{\beta}{2}\left\| y-x \right\| ^{2}_{2}$$

> [!proof]-
> From [[Taylor's Theorem|Theorem 1]], we have that: $$f(y)=f(x)+\int_{0}^{1} \nabla f(x+t(y-x))^\top(y-x) \, dt $$Therefore, $$\begin{aligned}f(y)&=f(x)+\int_{0}^{1} \nabla f(x+t(y-x))^\top(y-x) \, dt\\&=f(x)+\int_{0}^{1} \nabla f(x)^\top(y-x) \, dt+\int_{0}^{1} (\nabla f(x+t(y-x))-\nabla f(x))^\top(y-x) \, dt \\&\leq f(x)+\int_{0}^{1} \nabla f(x)^\top(y-x) \, dt+\int_{0}^{1} \|\nabla f(x+t(y-x))-\nabla f(x)\|\cdot \|y-x\|  \, dt\\&\leq f(x)+\int_{0}^{1} \nabla f(x)^\top(y-x) \, dt+\beta\int_{0}^{1}  t\|y-x\|^{2}  \, dt \\&\leq f(x)+ \nabla f(x)^\top(y-x) +\frac{\beta}{2}\|y-x\|^{2} \end{aligned}$$

---
> [!lemma] Theorem 3 (Gradient Descent)
> Let $f:X\to \mathbb{R}$ be a convex, $\beta$-gradient Lipschitz function and $x_{0}\in X$. 
> 1. 