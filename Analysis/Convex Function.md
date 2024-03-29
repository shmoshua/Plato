#Definition #FunctionalAnalysis 

> [!definition]
> Let $X$ be a [[Convex Set|convex subset]] of a $\mathbb{R}$-vector space and $f:X\to \mathbb{R}$ be a function. $f$ is ***convex*** if for all $x,y\in X$ and $t\in[0,1]$, we have:$$f(tx+(1-t)y)\leq tf(x)+(1-t)f(y)$$
- **Related definition**: $f$ is ***concave*** if $-f$ is convex.
---
##### Properties
> [!lemma] Proposition 1
> For a function $f:X\to \mathbb{R}$ with a convex domain, the following are equivalent.
> 1. $f$ is convex.
> 2. $f(y)\ge f(x)+\nabla_{x}f(x)(y-x)$ for all $x,y\in X$
> 3. $\nabla^2f(x)\succeq0$
---