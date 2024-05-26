#Definition #DifferentialGeometry 
> [!definition]
> Let $M$ be a $m$-dimensional [[smooth manifold]]. A subset $N\subseteq M$ is a $n$-dimensional ***regular submanifold***, if for any $p\in N$, there is a chart $(U,\varphi)$ at $p$ s.t. 
> 1. $\varphi(p)=0$, 
> 2. $\varphi(U)=(-\varepsilon,\varepsilon)^m$ and
> 3. $\varphi(U\cap N)=\{ x\in (-\varepsilon,\varepsilon)^m: x_{n+1}=\dots=x_{m}=0 \}$
- **Remark**: For the atlas $\{ (U_{\alpha},\varphi_{\alpha}) \}$ on $M$, $\{ (U_{\alpha}\cap N,\varphi_{\alpha}|_{U_{\alpha}\cap N}) \}_{\alpha}$ defines an atlas on $N$.
---
##### Properties
> [!lemma] Theorem 1
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $F\in C^\infty(N,M)$ with constant rank $k$. For $q\in F(N), F^{-1}(q)$ is a submanifold of $N$ of dimension $n-k$.

> [!proof]-
> Let $p\in F^{-1}(q)$. Then, by [[Rank|Corollary 2]], there are charts $(U,\varphi),(W,\psi)$ at $p,F(p)$ respectively s.t. 
> 1. $\varphi(p)=0$, $\psi(q)=0$ and
> 2. $\varphi(U)=(-\varepsilon,\varepsilon)^n$ and $\psi(W)=(-\varepsilon,\varepsilon)^m$ as well as:
> 3. $\psi \circ F\circ\varphi ^{-1}(x_{1},\dots,x_{n})=(x_{1},\dots,x_{k},0,\dots,0)$