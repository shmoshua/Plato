#Definition #FunctionalAnalysis 

> [!definition]
> Let $X$ be a [[Convex Set|convex subset]] of a $\mathbb{R}$-vector space $V$ and $f:X\to \mathbb{R}$ be a function. 
> 1. $f$ is ***convex*** if for all $x,y\in X$ and $t\in[0,1]$, we have:$$f(tx+(1-t)y)\leq tf(x)+(1-t)f(y)$$
> 2. $f$ is ***strictly convex*** if for all $x,y\in X$ and $t\in(0,1)$, we have:$$f(tx+(1-t)y)< tf(x)+(1-t)f(y)$$

^c94c8e

- **Related definition**: $f$ is ***(strictly) concave*** if $-f$ is (strictly) convex.
---
##### Properties
> [!lemma] Proposition 1 (1st order Convexity)
> Let $f:X\to \mathbb{R}$ be a differentiable function. Then, TFAE:
> 1. $f$ is convex.
> 2. for any $x,y\in X$, $f(y)\geq f(x)+(\nabla f(x))^\top(y-x)$

^4455df

> [!proof]-
> We have:
> 1. Let $f$ be convex. Fix $x,y\in X$. For any $t\in [0,1]$, for $z:=(1-t)x+ty$, we have that: $$f(z)=f((1-t)x+ty)\leq (1-t)f(x)+tf(y)$$Therefore, $$f(x+t(y-x))-f(x)\leq t(f(y)-f(x))$$and $$(\nabla f(x))^\top(y-x)=\lim_{ t \to 0 }\frac{f(x+t(y-x))-f(x)}{t}\leq f(y)-f(x) $$
> 2. Let $x,y\in X$ and $t\in [0,1]$. Further, let $z:=(1-t)x+ty$. Then, $$\begin{align}(1-t)f(x)+tf(y)&\geq f(z)+(1-t)(\nabla f(z))^\top(x-z)+t(\nabla f(z))^\top(y-z)\\&\geq f(z)+(\nabla f(z))^\top((1-t)x+ty-z)\\&\geq f(z)+(\nabla f(z))^\top 0\\&=f((1-t)x+t y)\end{align}$$

^7dbca8

---
> [!lemma] Proposition 2 (2nd order Convexity)
> Let $f:X\to \mathbb{R}$ be twice continuously differentiable.
> 1. if $\nabla^{2}_{x}f\succeq 0$ for all $x\in X$, then $f$ is convex.
> 2. if $\nabla^{2}_{x}f\succ 0$ for all $x\in X$, then $f$ is strictly convex.
> 3. if $f$ is convex, then $\nabla^{2}_{x}f\succeq 0$.

> [!proof]-
> We have that:
> 1. By Taylor's theorem, for all $y\in X$, there exists $z\in X$ s.t. $$f(y)=f(x)+(\nabla _{x}f)^\top(y-x)+\frac{1}{2}((y-x)^\top \nabla^{2}_{z}f(y-x))$$Then, by positive semidefiniteness, $f(y)\geq f(x)+(\nabla _{x}f)^\top(y-x)$ and it follows from Proposition 1.
> 2. Analogous to 1. 
> 3. Let $f$ be convex. For $x\in X$ and some $\lambda>0$. For any $d\in V$, we have $x+\lambda d\in X$. Hence, by Taylor, we get: $$f(x)+\lambda(\nabla _{x}f)^\top d\leq f(x+\lambda d)=f(x)+\lambda \nabla _{x}f^\top d+\frac{\lambda^{2}}{2}d^\top \nabla^{2}_{x}f d+o(\lambda^{2}\left\| d \right\| ^{2})$$Hence, $0\leq d^\top \nabla^{2}_{x}fd+o(\|d\|^{2})$ for all $d\in V$. Therefore, $\nabla_{x}^{2}f\succeq 0$.
---
> [!lemma] Proposition 1
> For a function $f:X\to \mathbb{R}$ with a convex domain, the following are equivalent.
> 1. $f$ is convex.
> 2. $f(y)\ge f(x)+\nabla_{x}f(x)(y-x)$ for all $x,y\in X$
> 3. $\nabla^2f(x)\succeq0$
---