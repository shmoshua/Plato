#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $f:M\to N$ [[Differentiable Function|differentiable]] at $p\in M$. For $(U,\varphi)$ at $p$ and $(W,\psi)$ at $f(p)$, the ***rank*** of $f$ at $p$ is the rank of $d_{\varphi(p)}(\psi  f\varphi ^{-1}):\mathbb{R}^m\to \mathbb{R}^n$.
- **Related definition**: A value $y\in N$ is ***regular*** if $f$ has rank $n$ at every point in $f^{-1}(y)$.
---
##### Properties
> [!lemma] Theorem 1 
> Let $A_{0}\subseteq \mathbb{R}^n$, $B_{0}\subseteq \mathbb{R}^m$ be open and let $F\in C^r(A_{0},B_{0})$. If $F$ has constant rank $k$ on $A_{0}$, then given $a_{0}\in A_{0}$, there exists open subsets $A\subseteq A_{0},B\subseteq B_{0}$ and $C^r$-diffeomorphisms $G:A\to U\subseteq \mathbb{R}^n$ and $H:B\to V\subseteq \mathbb{R}^m$ s.t. 
> 1. $a_{0}\in A$ and $F(a)\in B$
> 2. $U,V$ are open
> 3. $G(a_{0})=0$ and $H(F(a_{0}))=0$
> 4. we have: $$HFG^{-1}(x_{1},\dots,x_{n})=(x_{1},\dots,x_{k},0, \dots,0)$$

> [!proof]- Proof (Incomplete)
> Altering $G,H$ with translations if necessary, we may assume that $a_{0}=0$ as well as $F(a_{0})=0$. Now, let $D_{x}F(0)=\left[ \frac{ \partial F_{j} }{ \partial x_{i} } \right]_{ij}\in \text{M}_{n,m}(\mathbb{R})$ has rank $k$. Modulo permuting coordinates in $\mathbb{R}^n$ and $\mathbb{R}^m$, we may assume that the first principal $k\times k$-minor of $D_{x}F(0)$ has non-zero determinant, that is: $$\det \begin{bmatrix}\frac{ \partial F_{1} }{ \partial x_{1} }&\dots&\frac{ \partial F_{1} }{ \partial x_{k} } \\ \vdots&&\vdots\\\frac{ \partial F_{k} }{ \partial x_{1} }&\dots&\frac{ \partial F_{k} }{ \partial x_{k} } \end{bmatrix}\neq 0$$
> Define $G(x):=(F_{1}(x),\dots,F_{k}(x),x_{k+1},\dots,x_{n})$. Then, $G(0)=0$ and for all $x\in A_{0}$: $$D_{x}G=\begin{bmatrix}[\partial_{i}F_{j}]_{i,j}^k&*\\0&I_{n-k}\end{bmatrix}$$Therefore, $\det D_{x}G=\det [\partial_{i}F_{j}]_{i,j}^k\neq 0$. Using the inverse function theorem on $G$, there exists open subsets $A\subseteq A_{0}$ and $U\subseteq \mathbb{R}^n$, both containing $0$, s.t. $G:A\to U$ is a $C^r$-diffeomorphism. 
> 
> Then, for $y\in U$, there exists $x\in A$ s.t. $G(x)=y$. We have: $$\begin{align}(F\circ G^{-1})(y)&=F(x_{1},\dots,x_{n})\\&=(F_{1}(x),\dots,F_{m}(x))\\&=(y_{1},\dots,y_{k},f_{k+1}(y),\dots,f_{m}(y))\end{align}$$where $f_{\ell}(y)=F_{\ell}(x)$ for all $\ell\geq k+1$. Now observe that $F\circ G^{-1}$ has constant rank $k$ on $U$ and that for $y\in U$, we have $$D_{y}(F\circ G^{-1})=D_{G^{-1}(y)}F\circ D_{y}G$$ Hence the
---
> [!lemma] Corollary 2
> Let $M,N$ be smooth manifolds and $F\in C^\infty(M,N)$ of constant rank $k$. Then, for $p\in M$, there exists charts $(U,\varphi)$ at $p$ and $(W,\psi)$ at $F(p)$ and $\varepsilon>0$ s.t. 
> 1. $\varphi(p)=0$, $\psi(F(p))=0$
> 2. $\varphi(U)=(-\varepsilon,\varepsilon)^m$, $\psi(W)=(-\varepsilon,\varepsilon)^n$
> 3. $$\psi F\varphi ^{-1}(x_{1},\dots,x_{n})=(x_{1},\dots,x_{k},0,\dots,0)$$