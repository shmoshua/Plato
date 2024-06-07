#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $f:M\to N$ [[Differentiable Function|differentiable]] at $p\in M$. For $(U,\varphi)$ at $p$ and $(W,\psi)$ at $f(p)$, the ***rank*** of $f$ at $p$ is the rank of $d_{\varphi(p)}(\psi  f\varphi ^{-1}):\mathbb{R}^m\to \mathbb{R}^n$.
- **Related definition**: A value $y\in N$ is ***regular*** if $f$ has rank $n$ at every point in $f^{-1}(y)$.
---
##### Properties
![[Smooth Function#^374b28]]
![[Smooth Function#^c35ca3|p]]
![[Smooth Function#^a2f39f|p]]
---
> [!lemma] Corollary 1 
> Let $M,N$ be smooth manifolds and $f\in C^\infty(M,N)$. If $M$ is connected, then TFAE:
> 1. for each $p\in M$, there exists charts at $p$ and $f(p)$ s.t. the coordinate representatin of $f$ is linear.
> 2. $f$ has constant rank.