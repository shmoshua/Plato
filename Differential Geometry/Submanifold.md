 #Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be a [[smooth manifold]] and $\varphi\in C^\infty(N,M)$ an [[Differential|immersion]].
> 1. $\varphi(N)$ is an ***immersed submanifold*** of $M$, if $\varphi$ is injective.
> 3. $N\subseteq M$ is a ***regular $n$-submanifold*** of $M$, if for any $p\in N$, there is a chart $(U,\varphi)$ at $p$ s.t. 
> 	1. $\varphi(p)=0$, 
> 	2. $\varphi(U)=(-\varepsilon,\varepsilon)^m$ and
> 	3. $\varphi(U\cap N)=\{ x\in (-\varepsilon,\varepsilon)^m: x_{n+1}=\dots=x_{m}=0 \}$
- **Related definition**: $\varphi:N\to M$ is an ***embedding*** of $M$, if $\varphi(N)$ is a regular submanifold and $\varphi$ a [[diffeomorphism]].
- **Remark**: For the atlas $\{ (U_{\alpha},\varphi_{\alpha}) \}$ on $M$ and a regular submanifold $N\subseteq M$, $\{ (U_{\alpha}\cap N,\varphi_{\alpha}|_{U_{\alpha}\cap N}) \}_{\alpha}$ defines an atlas on $N$.
---
##### Properties
> [!lemma] Theorem 1 (Constant Rank Theorem)
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $f\in C^\infty(M,N)$ with constant [[rank]] $k$. 
> 1. For $q\in f(M), L:=f^{-1}(q)$ is a regular submanifold of $M$ of dimension $m-k$.
> 2. $\text{T}_{p}L\cong\text{ker }d_{p}f$ for any $p\in f^{-1}(q)$.

> [!proof]-
> We have:
> 1. Let $p\in f^{-1}(q)=\{ x\in M:f(x)=q \}$. By [[Smooth Function|Theorem 4 Corollary]], there are charts $(U,\varphi)$ and $(V,\psi)$ centered at $p$ and $q$ respectively s.t. $\varphi(U)=(-\varepsilon,\varepsilon)^m$ and $\psi(V)=(-\varepsilon,\varepsilon)^n$ with: $$\psi f\varphi ^{-1}(x_{1},\dots,x_{m})=(x_{1},\dots,x_{k},0,\dots,0)$$In particular, $(f|_{U})^{-1}(q)=U\cap f^{-1}(q)$ and $$\varphi(U\cap f^{-1}(q))=(\psi f\varphi ^{-1})^{-1}(0)=\{ x\in (-\varepsilon,\varepsilon)^n: x_{1}=\dots=x_{k}=0 \}$$This proves the statement.
> 2. As $L$ is a regular submanifold of $M$, we may consider $\text{T}_{p}L$ as a subset of $\text{T}_{p}M$. Let $v\in \text{T}_{p}L$ and $\gamma:(-\varepsilon,\varepsilon)\to L$ be a smooth curve s.t. $\gamma(0)=p$ and $\gamma'(0)=v$. Then, $f(\gamma(t))=q$ and we have: $$d_{p}f(v)=d_{\gamma(0)}f(\gamma'(0))=\left. \frac{d}{dt} \right| _{t=0}f\circ \gamma(t)=0$$Therefore, $v\in \text{ker }d_{p}f$. Further, notice that $$\text{dim }\text{ker }d_{p}f=m-k=\text{dim }L=\text{dim }\text{T}_{p}L$$
---
> [!lemma] Proposition 2 (Embedding <=> Homeomorphism, Immersion)
> Let $M,N$ be smooth manifolds and $f\in C^\infty(N,M)$. TFAE:
> 1. $f$ is a homeomorphism onto $f(N)$ and $f$ is an [[Immersion and Submersion|immersion]].
> 2. $f:N\to f(N)$ is a diffeomorphism and $f(N)$ is a regular submanifold, i.e. $f$ is an embedding.

> [!proof]+
> We have:
> 1. (1=>2): Assume $f$ is a homeomorphism onto $f(N)$ and $f$ is an immersion. By [[Immersion and Submersion|Corollary 2]], for any $p\in M$, there exists open $U\ni p$ with $f|_{U}:U\to f(U)$ is an embedding of $N$.  Hence, $f|_{U}$ is a diffeomorphism and $f(U)$ is open as $f$ is a homeomorphism. This shows that $f$ is a bijective local diffeomorphism, which by [[Local Diffeomorphism|Proposition 2]] is a diffeomorphism.
>    
>    To show that $f(N)$ is a regular submanifold, 
---
> [!lemma] Proposition 2 (Embedded submanifold => Regular submanifold)
> Let $M,N$ be smooth manifolds and $f\in C^\infty(N,M)$ a diffeomorphism. If $f(N)$ is an embedded submanifold of $M$, then $f(N)$ is a regular $n$-submanifold.

> [!proof]-
> Since $f$ is an homeomorphism onto its image, for any open $V\subseteq N$, there exists $W\subseteq M$ with $f(V)\subseteq W\cap f(N)$. Then, as $f$ is constant rank, by [[Smooth Function|Corollary of Theorem 4]], we can choose charts $(V,\varphi)$ and $(W,\psi)$ centered at $p$ and $f(p)$ respectively s.t. $f(V)\subseteq W\cap f(N)$ and $\varphi(V)=(-\varepsilon,\varepsilon)^n$ and $\psi(W)=(-\varepsilon,\varepsilon)^m$ with: $$\psi f\varphi^{-1}:(-\varepsilon,\varepsilon)^n\to(-\varepsilon,\varepsilon)^m,\quad x\mapsto(x,0)$$Therefore, $\psi(W\cap f(N))=\{ y\in (-\varepsilon,\varepsilon)^m:y_{n+1}=\dots=y_{m}=0 \}$ and $f(N)$ is a regular $n$-submanifold.
- **Corollary**: A subset $N\subseteq M$ is a regular $n$-submanifold if and only if $N$ is an embedded submanifold of dimension $n$ w.r.t. inclusion $i:N\to M$.

---
##### Examples
> [!h] Example 1
> Let $M$ be a smooth manifold:
> 1. Any open subset $U\subseteq M$ is a regular submanifold.
> 2. [[Surface|Smooth surfaces]] in $\mathbb{R}^3$ are regular submanifolds.
> 3. $S^n\subseteq \mathbb{R}^{n+1}$ are regular $n$-submanifolds.
> 4. $S^{n-1}\subseteq S^n$ are regular $(n-1)$-submanifolds.
---
> [!h] Example 2
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
##### Non-Examples
> [!h] Non-Example 1
> We have that:
> 1. A curve that meets itself in an injective way is an injective immersion, but its image is not a regular submanifold.
> 2. $\gamma:\mathbb{R}\to \mathbb{R}^2,t\mapsto(t^{2},t^{3})$ is injective but not a immersion as $\dot{\gamma}(0)=(0,0)$, which is not injective.
> 3. The Klein bottle is immersed in $\mathbb{R}^3$, but not embedded in $\mathbb{R}^3$. However, by taking it to the new axis, it is embedded in $\mathbb{R}^4$.