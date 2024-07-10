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
- **Related definition**:  A regular submanifold $M\subseteq N$ is ***proper*** if $i:M\hookrightarrow N$ is [[Proper Map|proper]]:
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
> 1. $f$ is a homeomorphism onto $f(N)$ and $f$ is an [[Immersion|immersion]].
> 2. $f$ is an embedding, i.e. $f:N\to f(N)$ is a diffeomorphism and $f(N)$ is a regular submanifold.

^77709c

> [!proof]-
> We have:
> 1. (1=>2): Assume $f$ is a homeomorphism onto $f(N)$ and $f$ is an immersion. By [[Immersion|Corollary 2]], for any $p\in M$, there exists open $U\ni p$ with $f|_{U}:U\to f(U)$ is an embedding of $N$.  Hence, $f|_{U}$ is a diffeomorphism and $f(U)$ is open in $f(N)$ as $f$ is a homeomorphism. This shows that $f$ is a bijective local diffeomorphism, which by [[Local Diffeomorphism|Proposition 2]] is a diffeomorphism.
>    
>    To show that $f(N)$ is a regular submanifold, let $p\in N$ and as $f$ is an immersion by [[Immersion|local immersion theorem]] there exists charts $(U,\varphi)$ at $p$ and $(V,\psi)$ at $f(p)$ s.t. $$\psi f\varphi ^{-1}(x^1,\dots,x^n)=(x^1,\dots,x^n,0,\dots,0)$$Since $f$ is a homeomorphism onto its image, $f(U)$ is open in $f(N)$. therefore, there exists an open set $W\subseteq M$ s.t. $f(U)=W\cap f(N)$. Consider $(V\cap W,\psi|_{V\cap W})$. We have that $\psi(f(p))=0$, $$\psi(V\cap W\cap f(N))=\psi(V\cap f(U))=\psi(V)\cap \psi(f(U))\subseteq \psi(V)\cap (\mathbb{R}^n\times \{ 0 \})$$Modulo taking a smaller set, we get that $f(N)$ is a regular submanifold.
> 2. (2=>1): As $f$ is a diffeomorphism it is a homeomorphism. Further, $f$ is an immersion as $d_{p}f$ is always injective.

^ff863e

---
> [!lemma] Proposition 3 (Properness and Embedding)
> Let $f\in C^\infty(M,N)$ be an embedding. Then, TFAE:
>  1. $f$ is [[Proper Map|proper]].
>  2. $f(M)$ is closed in $N$.

> [!proof]-
> We have: 
> 1. (1=>2): If $g$ is proper, then $g$ is closed by [[Proper Map|Proposition 1]] and $f(M)$ is closed in $N$.
> 2. (2=>1): assume that $f(M)$ is closed in $N$ and let $K\subseteq N$ compact. Then, $K\cap f(M)$ is compact and $$f^{-1}(K\cap f(M))=f^{-1}(K)$$is compact as $f^{-1}$ is continuous. 
---
> [!lemma] Theorem 4 (Whitney's Embedding Theorem)
> Let $M$ be a [[smooth manifold]]. Then, 
> 1. $M$ embeds into $\mathbb{R}^{2m}$.
> 2. if $M$ is compact then $M$ embeds into $\mathbb{R}^{(m+1)k}$ for some $k>0$. 

> [!proof]-
> For each $p\in M$, we define $U_{p},V_{p}$ open sets s.t. $\overline{U_{p}}$ is compact and $\overline{U_{p}}\subseteq V_{p}$ and there exists a diffeomorphism $\varphi_{p}$ on $V_{p}$. Then, by compactness, we have a finite $(U_{i},V_{i},\varphi_{i})$ for $i\in [k]$ s.t. $(U_{i})_{i}$ is an open cover.
> 
> By [[Smooth Manifold|smooth Urysohn's lemma]], there exists a $\rho_{i}\in C^\infty(M,[0,1])$ s.t. $\rho_{i}|_{\overline{U_{i}}}=1$ and $\text{supp }\rho_{i}\subseteq V_{i}$. Further, using the diffeomorphism $\varphi_{p}$, we can also acquire a bump function $h_{i}\in C^\infty(M)$ s.t. $h_{i}|_{U_{i}}>0$ and $h_{i}|_{M \backslash U_{i}}=0$. Therefore, we can define $g_{i}\in C^\infty(M,\mathbb{R}^m)$ given as: $$g_{i}(x):=\begin{cases}\rho_{i}(x)\varphi_{i}(x)&x\in V_{i}\\0&\text{otherwise}\end{cases}$$
> 
> Now, we construct an embedding as follows: $$f:M\to \mathbb{R}^{(m+1)k},\quad x\mapsto(g_{1}(x),h_{1}(x),\dots,g_{k}(x),h_{k}(x))$$which is a smooth function. We now only have to show per [[Immersion|Proposition 3]] that $f$ is an injective immersion as $M$ is compact.
> 1. **Showing $f$ is injective**:
>    Let $p,q\in M$ s.t. $f(p)=f(q)$. Fix $i$ s.t. $p\in U_{i}$. Then, $h_{i}(p)=h_{i}(q)>0$ and $q\in U_{i}$. Therefore, from $g_{i}(p)=g_{i}(q)$, we have $\varphi_{i}(p)=\varphi_{i}(q)$. Then, $p=q$ from the injectivity of $\varphi_{i}$.
> 2. **Showing $f$ is an immersion**.
>    Fix $p\in M$ and $i$ s.t. $p\in U_i$. Now, we have that: $$d_{p}g_{i}=d_{p}(\rho_{i}\varphi_{i})=\underbrace{ d_{p}\rho_{i} }_{ =0 }\cdot \varphi_{i}(p)+\underbrace{ \rho_{i}(p) }_{ =1 }\cdot d_{p}\varphi_{i}=d_{p}\varphi_{i}$$Where $d_{p}\varphi_{i}$ is a bijection as $\varphi_{i}$ is a diffeomorphism. Therefore, $$d_{p}f=(d_{p}g_{1},d_{p}h_{1},\dots,d_{p}g_{k},d_{p}h_{k})$$is an injection and $f$ is an immersion.
> 
> 
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