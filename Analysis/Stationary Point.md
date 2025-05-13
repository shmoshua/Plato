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