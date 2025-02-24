#Definition #FunctionalAnalysis 

> [!definition]
> Let $X$ be a [[Convex Set|convex subset]] of a $\mathbb{R}$-vector space and $f:X\to \mathbb{R}$ be a function. 
> 1. $f$ is ***convex*** if for all $x,y\in X$ and $t\in[0,1]$, we have:$$f(tx+(1-t)y)\leq tf(x)+(1-t)f(y)$$
> 2. $f$ is ***strictly convex*** if for all $x,y\in X$ and $t\in(0,1)$, we have:$$f(tx+(1-t)y)< tf(x)+(1-t)f(y)$$
- **Related definition**: $f$ is ***(strictly) concave*** if $-f$ is (strictly) convex.
---
##### Properties
> [!lemma] Proposition 1 (1st order Convexity)
> Let $f:X\to \mathbb{R}$ be a differentiable function. Then, TFAE:
> 1. $f$ is convex.
> 2. for any $x,y\in X$, $f(y)\geq f(x)+(\nabla_{x}f)^\top(y-x)$

> [!proof]+
> We have:
> 1. Let $f$ be convex. Fix $x,y\in X$. For any $t\in [0,1]$, for $z:=(1-t)x+ty$, we have that: $$f(z)=f((1-t)x+ty)\leq (1-t)f(x)+tf(y)$$Therefore, $$f(x+t(y-x))-f(x)\leq t(f(y)-f(x))$$and $$(\nabla _{x}f)^\top(y-x)=\lim_{ t \to 0 }\frac{f(x+t(y-x))-f(x)}{t}= $$
---
> [!lemma] Proposition 2 (2nd order Convexity)
> Let $f:X\to \mathbb{R}$ be twice continuously differentiable.
> 1. if $\nabla^{2}_{x}f\succeq 0$ for all $x\in X$, then $f$ is convex.
> 2. if $\nabla^{2}_{x}f\succ 0$ for all $x\in X$, then $f$ is strictly convex.
> 3. if $f$ is convex, then $\nabla^{2}_{x}f\succeq 0$.
---
> [!lemma] Proposition 1
> For a function $f:X\to \mathbb{R}$ with a convex domain, the following are equivalent.
> 1. $f$ is convex.
> 2. $f(y)\ge f(x)+\nabla_{x}f(x)(y-x)$ for all $x,y\in X$
> 3. $\nabla^2f(x)\succeq0$
---