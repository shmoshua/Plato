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
> 1. for each $p\in M$, there exists charts $(U,\varphi)$ and $(V,\psi)$ at $p$ and $f(p)$ s.t. the coordinate representation $\tilde{f}:=\psi f\varphi ^{-1}$ is linear.
> 2. $f$ has constant rank.

> [!proof]-
> We have:
> 1. (1=>2): since every linear map has constant rank, it follows that the rank of $f$ is constant in a neighborhood of each point, and thus by connectedness it is constant on all of $M$.
> 2. (2=>1): Corollary of Theorem 4.
---
> [!lemma] Theorem 2 (Global Rank Theorem)
> Let $M,N$ be smooth manifolds and $f\in C^\infty(M,N)$ has constant rank. 
> 1. if $f$ is surjective, it is a submersion.
> 2. if $f$ is injective, it is an [[Differential|immersion]].
> 3. if $f$ is bijective, it is a [[diffeomorphism]].

> [!proof]-
> Let $f$ have a constant rank $k$. 
> 1. Assume $f$ is not a submersion. This means that $k<n$. By Theorem 4 Corollary, there exists for each $p\in M$ charts $(U,\varphi)$ and $(V,\psi)$ centered at $p$ and $f(p)$ s.t. $$(\psi f\varphi ^{-1})(x_{1},\dots,x_{m})=(x_{1},\dots,x_{k},0,\dots,0)$$and $\varphi(U)=(-\varepsilon,\varepsilon)^m$ and $\psi(V)=(-\varepsilon ,\varepsilon)^n$. By shrinking $\varepsilon$, we may assume $f(U)\subseteq V$. This implies that $f(\overline{U})$ is a compact subset of the set $\{ y\in V:y_{k+1}=\dots=y_{n}=0 \}$ so it is closed in $N$ and contains no open subset of $N$; hence it is [[Dense Subset|nowhere dense]] in $N$. 
>    
>    Since $M$ is [[Lindelöf Space|Lindelöf]] and every open cover of $M$ has a countable subcover, we can choose countably many such charts $\{ (U_{i},\varphi_{i}) \}_{i}$ covering $M$; with corresponding charts $\{ (V_{i},\psi_{i}) \}_{i}$ covering $f(M)$. Because $f(M)$ is equal to the countable union of the nowhere dense $f(\overline{U}_{i})$, it follows from the [[Baire category theorem]] that $f(M)$ has empty interior in $N$, which means $f$ cannot be surjective.
> 2. Assume that $f$ is not an immersion, so that $k<m$. By the rank theorem, for each $p\in M$, we can choose charts $(U,\varphi)$ and $(V,\psi)$ at $p$ and $f(p)$ s.t. $$(\psi f\varphi ^{-1})(x_{1},\dots,x_{m})=(x_{1},\dots,x_{k},0,\dots,0)$$It follows that $\psi f\varphi ^{-1}(0,\dots,0,r)=0=\psi f\varphi ^{-1}(0,\dots,0)$ for $r<\varepsilon$. Hence, $f$ cannot be injective. 
> 3. If $f$ is bijective, it is a submersion and an immersion and, by [[Local Diffeomorphism|Proposition 3.1]] it is a local diffeomorphism. As $f$ is bijective, by [[Local Diffeomorphism|Proposition 2.6]], $f$ is a diffeomorphism.
---
