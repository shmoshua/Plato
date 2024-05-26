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
> Let $M,M'$ be [[Smooth Manifold|smooth manifolds]] and $f\in C^\infty(M,M')$ with constant [[rank]] $k$. 
> 1. For $q\in f(M), f^{-1}(q)$ is a regular submanifold of $M$ of dimension $m-k$.

> [!proof]- Proof (Incomplete)
> Let $p\in f^{-1}(q)$. 
---
##### Examples
> [!h] Example 1
> $\text{SL}(n,\mathbb{R})\leq \text{GL}(n,\mathbb{R})$ is a regular $n^2-1$-submanifold of $\text{GL}(n,\mathbb{R})$.

> [!proof]+
> Consider $\det:\text{GL}(n,\mathbb{R})\to \mathbb{R}^\times$, which is smooth. We will show that $\det$ is constant rank. We have for $X\in \text{GL}(n,\mathbb{R})$: $$\begin{align}d_{A}\det(X)&=\left. \frac{d}{dt} \right| _{t=0}\det(X+tA)\\&=\end{align}$$