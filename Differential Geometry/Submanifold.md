#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be a [[smooth manifold]]. 
> 1. $N$ is an ***immersed submanifold*** of $M$, if there exists $F\in C^\infty(N,M)$ that is an injective [[Differential|immersion]].
> 2. $N$ is a ***regular submanifold*** of $M$, if there exists $F\in C^\infty(N,M)$ that is an ***embedding***, i.e. $F$ is an injective immersion that is also a [[homeomorphism]] to its image.
---

> [!definition]
> Let $M$ be a [[smooth manifold]]. A subset $N\subseteq M$ is a ***regular $n$-submanifold***, if for any $p\in N$, there is a chart $(U,\varphi)$ at $p$ s.t. 
> 1. $\varphi(p)=0$, 
> 2. $\varphi(U)=(-\varepsilon,\varepsilon)^m$ and
> 3. $\varphi(U\cap N)=\{ x\in (-\varepsilon,\varepsilon)^m: x_{n+1}=\dots=x_{m}=0 \}$
- **Remark**: For the atlas $\{ (U_{\alpha},\varphi_{\alpha}) \}$ on $M$, $\{ (U_{\alpha}\cap N,\varphi_{\alpha}|_{U_{\alpha}\cap N}) \}_{\alpha}$ defines an atlas on $N$.
---
##### Properties
> [!lemma] Proposition 1
> Let $M,N$ be smooth manifolds. Then, the following are equivalent:
> 1. $N$ is a regular $n$-submanifold of $M$ with embedding $F$.
> 2. for any $p\in N$, there exists a chart $(U,\varphi)$ of $M$ centered at $F(p)$ s.t. $\varphi(U)=(-\varepsilon,\varepsilon)^m$ and: $$\varphi(U\cap F(N))=\{ x\in (-\varepsilon,\varepsilon)^m:x_{n+1}=\dots=x_{m}=0 \}$$

> [!proof]-
> Assume $N$ is a regular $n$-submanifold with embedding $F$. Then, for every open subset $U\subseteq N$, there exists an open subset $V\subseteq M$ s.t. $f(U)\subseteq V\cap f(N)$. Choose charts $(U,\varphi)$ and $(V,\psi)$ at $p$ and $F(p)$ respectively s.t. $f(U)\subseteq V\cap f(N)$ and $\varphi(U)=(-\varepsilon,\varepsilon)^n, \varphi(p)=0$ as well as $\psi(V)=(-\varepsilon,\varepsilon)^m$ with $\psi(f(p))=0$ and: $$\psi F\varphi ^{-1}:(-\varepsilon,\varepsilon)^n\to(-\varepsilon,\varepsilon)^m,\quad x\mapsto(x,0)$$Then, $$\psi(V\cap F(N))=\{ y\in (-\varepsilon,\varepsilon)^m:y_{n+1}=\dots+y_{m}=0 \}$$
---
> [!lemma] Theorem 2 (Constant Rank Theorem)
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $f\in C^\infty(M,N)$ with constant [[rank]] $k$. 
> 1. For $q\in f(M), f^{-1}(q)$ is a regular submanifold of $M$ of dimension $m-k$.

> [!proof]+
> Let $p\in f^{-1}(q)=\{ x\in M:f(x)=q \}$. By [[Smooth Function|Theorem 4 Corollary]], there are charts $(U,\varphi)$ and $(V,\psi)$ centered at $p$ and $q$ respectively s.t. $\varphi(U)=(-\varepsilon,\varepsilon)^m$ and $\psi(V)=(-\varepsilon,\varepsilon)^n$ with: $$\psi f\varphi ^{-1}(x_{1},\dots,x_{m})=(x_{1},\dots,x_{k},0,\dots,0)$$In particular, $(f|_{U})^{-1}(q)=U\cap f^{-1}(q)$ and $$\varphi(U\cap f^{-1}(q))=(\psi f\varphi ^{-1})^{-1}(\psi(q))=\{ x\in (-\varepsilon,\varepsilon) \}$$
---
##### Examples
> [!h] Example 1
> We have:
> 1. $\text{SL}(n,\mathbb{R})\leq \text{GL}(n,\mathbb{R})$ is a regular $n^2-1$-submanifold of $\text{GL}(n,\mathbb{R})$.
> 2. $\text{O}(n,\mathbb{R})\leq \text{GL}(n,\mathbb{R})$ is a regular $n(n-1) /2$-submanifold of $\text{GL}(n,\mathbb{R})$.
> 3. [[Indefinite Orthogonal Group|$\text{O}(p,q,\mathbb{R})$]] $\leq \text{GL}(p+q,\mathbb{R})$ is a regular $n(n-1) /2$-submanifold of $\text{GL}(n,\mathbb{R})$ where $n:=p+q$.

> [!proof]-
> We have:
> 1. Consider $\det:\text{GL}(n,\mathbb{R})\to \mathbb{R}^\times$, which is smooth. We will show that $\det$ is constant rank. We have for $X\in \text{GL}(n,\mathbb{R})$: $$\begin{align}d_{A}\det(X)&=\left. \frac{d}{dt} \right| _{t=0}\det(A+tX)\\&=\det(A) \left. \frac{d}{dt} \right|_{t=0}\det(I+tA^{-1}X)\\&=\det(A)\cdot d_{I}\det(A^{-1}X) \end{align}$$Since $X\mapsto A^{-1}X$ defines an isomorphism, $\det:\text{GL}(n,\mathbb{R})\to \mathbb{R}^\times$ has a constant rank. Especially, $$\begin{align}d_{I}\det(X)&=\left. \frac{d}{dt} \right|_{t=0}\det(I+tX)\\&= \left. \frac{d}{dt} \right| _{t=0}t^n \det(t^{-1}I+X)\\&= \left. \frac{d}{dt} \right| _{t=0}t^n \det(t^{-1}I-(-X))\\&= \left. \frac{d}{dt} \right| _{t=0}t^n C_{-X}(t^{-1})\\&=\left. \frac{d}{dt} \right| _{t=0}t^n((t ^{-1})^n-(t^{-1})^{n-1}\text{tr}(-X)+(t ^{-1})^{n-2}P(t))\\&=\text{tr}(X)\end{align}$$where $C_{Y}(t):=\det(tI-Y)$ is the characteristic polynomial of $Y$. Therefore, $d_{I}\det(X)$ has rank $1$ and so does $\text{det}$. Using Theorem 1, $\det ^{-1}(1)$ is a regular $n^2-1$-submanifold.
> 2. Consider the smooth map $f:\text{GL}(n,\mathbb{R})\to \text{GL}(n,\mathbb{R}),A\mapsto A^\top A$. Then, $$\begin{align}d_{A}f(X)&=\left. \frac{d}{dt} \right| _{t=0}(A+tX)^\top(A+tX)\\&=\left. \frac{d}{dt} \right| _{t=0}A^\top A+tA^\top X+tX^\top A+t^{2} X^\top X\\&=A^\top X+X^\top A\end{align}$$In particular, $d_{A}f(A^{-\top}X)=X+X^\top=d_{I}f(X)$ which as above shows that $f$ has constant rank. 
>    
>    To compute the rank, note that $d_{I}f:\text{M}_{n,n}(\mathbb{R})\to\text{M}_{n,n}(\mathbb{R})$ has image exactly the subspace of $\text{M}_{n,n}(\mathbb{R})$ consisting of all symmetric matrices. Since a symmetric matrix is determined by its upper triangle, the dimension of this space is $1+2+\dots+n=\frac{n(n+1)}{2}$. As a result, $\text{O}(n,\mathbb{R})$ is a regular submanifold of $\text{GL}(n,\mathbb{R})$ of dimension $n^2-\frac{n(n+1)}{2}=\frac{n(n-1)}{2}$.
> 3. Let $n:=p+q$. Similarly, consider $f:\text{GL}(n,\mathbb{R})\to \text{M}_{n,n}(\mathbb{R}), A\mapsto A^\top\begin{bmatrix}-I_{p}&0\\0&I_{q}\end{bmatrix}A$. Then, $$\begin{align}d_{A}f(X)&= \left. \frac{d}{dt} \right| _{t=0}(A+tX)^\top\begin{bmatrix}-I_{p}&0\\0&I_{q}\end{bmatrix} (A+tX)\\&=A^\top \begin{bmatrix}-I_{p}&0\\0&I_{q}\end{bmatrix} X+X^\top\begin{bmatrix}-I_{p}&0\\0&I_{q}\end{bmatrix}A \end{align}$$In particular, $d_{A}f\left(\begin{bmatrix}-I_{p}&0\\0&I_{q}\end{bmatrix}A^{-\top}\right)=d_{I}f(X)$, we have as above that $f$ has constant rank.
---
