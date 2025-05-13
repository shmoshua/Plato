#Definition #AGAO 

> [!definition]
> Let $f:X\to \mathbb{R}$ be a differentiable function. Then, 
> 1. $x\in X$ is called a ***stationary point*** if $\nabla f(x)=0$.

^ea5579

---
##### Properties
> [!lemma] Proposition 1
> Let $f:X\to \mathbb{R}$ be a differentiable function. 
> 1. if $x\in X$ is a local extremum, it is a stationary point.

^2510d3

> [!proof]-
> Let $x$ be a local minimum. Then, for all $d\in \mathbb{R}^n$, $f(x)\leq f(x+\lambda d)$ for some small $\lambda$. Therefore, $$0\leq f(x+\lambda d)-f(x)=\lambda \nabla f(x)^\top d+o(\|\lambda d\|)$$Dividing by $\lambda$ and letting $\lambda\to 0$, we get that $0\leq \nabla f(x)^\top d$. However, by taking $d:=-\nabla f(x)^\top$, we have that $0\leq -\|\nabla f(x)\|^{2}$. Therefore, $\nabla f(x)=0$.

^a5cce7

---
> [!lemma] Proposition 2 (Convex Functions)
> Let $f:X\to \mathbb{R}$ be differentiable and [[Convex Function|convex]] where $X$ is [[convex set|convex]] open.
> 1. if $x\in X$ is a stationary point, then $x$ is a global minimum.

^6b3517

> [!proof]-
> We have that: $$f(y)\geq f(x)+\nabla f(x)^\top(y-x)=f(x),\quad \forall y\in \mathbb{R}^n$$

^7d64c2

---
> [!lemma] Proposition 3
> Let $f:X\to \mathbb{R}$ be a twice differentiable function at $x\in X$.
> 1. if $x$ is a local minimum, $\text{H}_{f}(x) \geq 0$. 
> 2. if $x$ is a stationary point and $\text{H}_{f}(x)> 0$, then $x$ is a local minimum.

> [!proof]-
> We have:
> 1. Let $x\in X$ be a local minimum. Then, as $\nabla f(x)=0$ by Proposition 1, we have that: $$f(x+\lambda d)=f(x)+\frac{\lambda^{2}}{2}d^\top \text{H}_{f}(x)d+o(\lambda^{2}\|d\|^{2}_{2})$$Therefore, we have that: $$0\leq \lim_{ \lambda \to 0^+ } \frac{f(x+\lambda d)-f(x)}{\lambda^{2}}=\frac{1}{2}d^\top \text{H}_{f}(x)d$$
> 2. We have that: $$f(x+\delta)=f(x)+\frac{1}{2}\delta^\top \text{H}_{f}(x)\delta+o(\left\| \delta \right\| ^{2}_{2})\geq f(x)+\frac{\lambda_{\text{min}}}{2}\|\delta\|^{2}_{2}+o(\left\| \delta \right\| ^{2}_{2})$$Therefore, if $\|\delta\|^2_{2}$ is small enough, $f(x+\delta)-f(x)\geq \frac{\lambda_{\text{min}}}{4}\|\delta\|^{2}_{2}> 0$. 
---
