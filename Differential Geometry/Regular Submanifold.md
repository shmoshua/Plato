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
> We have:
> 1. $\text{SL}(n,\mathbb{R})\leq \text{GL}(n,\mathbb{R})$ is a regular $n^2-1$-submanifold of $\text{GL}(n,\mathbb{R})$.
> 2. $\text{O}(n,\mathbb{R})\leq \text{GL}(n,\mathbb{R})$ is a regular $n(n-1) /2$-submanifold of $\text{GL}(n,\mathbb{R})$.

> [!proof]+
> We have:
> 1. Consider $\det:\text{GL}(n,\mathbb{R})\to \mathbb{R}^\times$, which is smooth. We will show that $\det$ is constant rank. We have for $X\in \text{GL}(n,\mathbb{R})$: $$\begin{align}d_{A}\det(X)&=\left. \frac{d}{dt} \right| _{t=0}\det(A+tX)\\&=\det(A) \left. \frac{d}{dt} \right|_{t=0}\det(I+tA^{-1}X)\\&=\det(A)\cdot d_{I}\det(A^{-1}X) \end{align}$$Since $X\mapsto A^{-1}X$ defines an isomorphism, $\det:\text{GL}(n,\mathbb{R})\to \mathbb{R}^\times$ has a constant rank. Especially, $$\begin{align}d_{I}\det(X)&=\left. \frac{d}{dt} \right|_{t=0}\det(I+tX)\\&= \left. \frac{d}{dt} \right| _{t=0}t^n \det(t^{-1}I+X)\\&= \left. \frac{d}{dt} \right| _{t=0}t^n \det(t^{-1}I-(-X))\\&= \left. \frac{d}{dt} \right| _{t=0}t^n C_{-X}(t^{-1})\\&=\left. \frac{d}{dt} \right| _{t=0}t^n((t ^{-1})^n-(t^{-1})^{n-1}\text{tr}(-X)+(t ^{-1})^{n-2}P(t))\\&=\text{tr}(X)\end{align}$$where $C_{Y}(t):=\det(tI-Y)$ is the characteristic polynomial of $Y$. Therefore, $d_{I}\det(X)$ has rank $1$ and so does $\text{det}$. Using Theorem 1, $\det ^{-1}(1)$ is a regular $n^2-1$-submanifold.
> 2. Consider the smooth map $f:\text{GL}(n,\mathbb{R})\to \text{GL}(n,\mathbb{R}),A\mapsto A^\top A$. Then, $$\begin{align}d_{A}f(X)&=\left. \frac{d}{dt} \right| _{t=0}(A+tX)^\top(A+tX)\\&=\left. \frac{d}{dt} \right| _{t=0}A^\top A+tA^\top X+tX^\top A+t^{2} X^\top X\end{align}$$
