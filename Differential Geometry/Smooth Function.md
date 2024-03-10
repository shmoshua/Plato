#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]]. A map $\varphi:M\to N$ is $C^k$ or ***$k$-times continuously differentiable***, if for any chart $(U,x)$ in $M$ and $(V,y)$ in $N$, $$y\circ \varphi \circ x^{-1}:x(U)\to y(V)\in C^k(\mathbb{R}^m,\mathbb{R}^n)$$If $\varphi\in C^k$ for all $k\geq 1$, $\varphi$ is ***smooth***, i.e. $\varphi\in C^\infty$.
- **Related definition**:
---
##### Properties
> [!lemma] Lemma 1
> Let $M,N,L$ be smooth manifolds and $\varphi:M\to N$ and $\psi:N\to L$ be smooth maps. Then, $$\psi \circ \varphi:M\to L$$ is smooth.

> [!proof]-
> Let $p\in M$ and $(U,x)$ a chart on $M$ containing $p$. Further, let $(V,y)$ be a chart on $N$ containing $\varphi(p)$ and $(W,z)$ a chart on $L$ containing $\psi(\varphi(p))$.  Then, $$z\circ (\psi \circ \varphi)\circ x^{-1}=(z\circ \psi \circ y^{-1})\circ (y\circ \varphi \circ x^{-1})$$which is a composition of two smooth functions in Euclidean space, which is smooth.
---
##### Examples
> [!h] Example 1
> Let $M$ be a smooth manifold and $W\subseteq M$ be an open set. Then, the inclusion $\iota:W\hookrightarrow M$ is smooth.
---
