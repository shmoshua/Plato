#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]]. A continuous map $f:M\to N$ is:
> 1.  ***smooth***, i.e. $f\in C^\infty(M,N)$ if for every chart $(U,\varphi)$ of $M$ and $(V,\psi)$ of $N$ s.t. $f(U)\subseteq V$, $$\psi f\varphi ^{-1}:\varphi(U)\to \psi(V)\in C^\infty(\mathbb{R}^m,\mathbb{R}^n)$$
- **Related definition**: Let $M,N$ be compact, connected and [[Orientable Manifold|oriented]] with dimension $m$. Then, for a smooth function $F:N\to M$, the ***degree*** of $F$, $\deg(F)\in \mathbb{R}$ is the unique real number s.t. $$\begin{CD}\text{H}_{\text{dR}}^m(M) @>F^{*}>> \text{H}_{\text{dR}}^m(N)\\@VIVV&@VIVV&\\\mathbb{R} @> x\mapsto \text{deg}F\cdot x> > \mathbb{R}\end{CD}$$commutes.
---
##### Properties
> [!lemma] Lemma 1 
> Let $M,N,L$ be smooth manifolds and continuous maps $f:M\to N$ and $g:N\to L$. Then, 
> 1. $f$ is smooth if and only if for any $p\in M$, there exists a chart $(U,\varphi)$ in $M$ and $(V,\psi)$ in $N$ with $f(U)\subseteq V$ s.t. $\psi f\varphi ^{-1}$ is smooth.
> 2. if $f,g$ are smooth, $g\circ f:M\to L$ is smooth.

> [!proof]-
> We have:
> 1. Let $(V,\psi)$ be an atlas of $N$ s.t. $f(p)\in V$. Then, by continuity, $f^{-1}(V)$ is open in $M$. Hence, by maximality, there exists a chart $(U,\varphi)$ s.t. $p\in U\subseteq f^{-1}(V)$. Therefore,$f(U)\subseteq V$ and by the assumption, $\psi f\varphi ^{-1}$ is smooth.
>    
>    Let $(U,\varphi)$ and $(V,\psi)$ be charts at $M$ and $N$ respectively s.t. $f(U)\subseteq V$. For $p\in M$, let $(U_{p},\varphi_{p})$ and $(V_{p},\psi_{p})$ be the charts given by the assumption. Then, we will show that $\psi f\varphi ^{-1}$ is smooth. we see that $(U\cap U_{\alpha})$ forms a covering of $U$ where $U\cap U_{\alpha}$ are open in $M$. Therefore, $(\varphi(U\cap U_{\alpha}))_{\alpha}$ is an open covering of $\varphi(U)$. Therefore, $$\psi f\varphi ^{-1}|_{\varphi(U\cap U_{\alpha})}=\underbrace{ \psi\psi_{\alpha}^{-1} }_{ \in C^\infty }\underbrace{ \psi_{\alpha}f\varphi_{\alpha}^{-1} }_{ \in C^\infty } \underbrace{ \varphi_{\alpha} \varphi ^{-1}|_{\varphi(U\cap U_{\alpha})} }_{ \in C^\infty }$$This proves the statement.
> 2. Let $p\in M$. Pick a chart $(W,\chi)$ of $L$ containing $gf(p)$ and by maximality, we have a chart $(V,\psi)$ of $N$ with $g(V)\subseteq W$ and $(U,\varphi)$ of $M$ with $f(U)\subseteq V$. Then, $$\chi gf\varphi ^{-1}=\underbrace{ \chi g\psi ^{-1} }_{ \in C^\infty }\underbrace{ \psi f\varphi ^{-1} }_{ \in C^\infty }$$Hence, by 1, we have that $g\circ f$ is smooth.
---
> [!lemma] Lemma 2
> Let $M,N$ be compact [[Smooth Manifold|smooth manifolds]] of dimension $m$ and $F:M\to N$ a smooth map. Further, let $q\in F(M)$ be [[Rank|regular]]. Then, 
> 1. $F^{-1}(q)$ is finite.
> 2. There exists an open connected set $V_{q}\subseteq N$ containing $q$ and for each $p\in F^{-1}(q)$ an open connected set $U_{p}\subseteq M$ containing $p$ s.t. $$F|_{U_{p}}:U_{p}\to V_{q}$$is a [[diffeomorphism]].

> [!proof]-
> Since $q$ is regular, for all $p\in F^{-1}(q)$, the differential $d_{p}F$ has full rank and is an isomorphism in this case. Therefore, by the inverse function theorem, there exist open neighborhoods $U'_{p}$ and $V'_{q}$ s.t. $F|_{U'_{p}}:U'_{p}\to V'_{q}$ is a diffeomorphism.
> 
> In particular, $U'_{p}\cap F^{-1}(q)=\{ p \}$. Therefore, $F^{-1}(q)$ is discrete in $M$ and finite by compactness of $M$. Now let $V_{q}$ to be the connected component of $\bigcap_{p\in F^{-1}(q)}^{}V'_{q}$ and $U_{p}:=(f|_{U'_{p}})^{-1}(V_{q})$.
---
##### Smooth Functions in Rn
> [!lemma] Theorem 1 (Hadamard's Lemma)
> Let $U\subseteq \mathbb{R}^n$ be open and [[Convex Set|convex]]. For $f\in C^\infty(U)$ and $a\in U$, we have that for all $x\in U$, $$f(x)=f(a)+\sum_{i=1}^{n}(x_{i}-a_{i})\int_{0}^{1}  \left. \frac{ \partial f }{ \partial x_{i} }  \right| _{a+t(x-a)}\, dt $$

> [!proof]-
> Let $x\in U$. Then, define $h:[0,1]\to \mathbb{R}$: $$h(t):=f(a+t(x-a))$$Then, $$h'(t)=\sum_{i=1}^{n}\left. \frac{ \partial f }{ \partial x_{i} }  \right| _{a+t(x-a)}(x_{i}-a_{i})$$Therefore, $$\begin{align}h(1)-h(0)&=\int_{0}^{1} h'(t) \, dt\\&=\int_{0}^{1} \sum_{i=1}^{n}\left. \frac{ \partial f }{ \partial x_{i} }  \right| _{a+t(x-a)}(x_{i}-a_{i}) \, dt\\&=\sum_{i=1}^{n}(x_{i}-a_{i})\int_{0}^{1}  \left. \frac{ \partial f }{ \partial x_{i} }  \right| _{a+t(x-a)}\, dt  \end{align}$$However, $$h(1)-h(0)=f(x)-f(a)$$This proves the statement.
---
> [!lemma] Corollary 2
> Let $U\subseteq \mathbb{R}^n$ be open and [[Convex Set|convex]]. For $f\in C^\infty(U)$ and $a\in U$, we have that for all $x\in U$, $$f(x)=f(a)+\sum_{i=1}^{n}(x_{i}-a_{i}) \left. \frac{ \partial f }{ \partial x_{i} }  \right| _{a} +\sum_{i,j=1}^{n}(x_{i}-a_{i})(x_{j}-a_{j})\int_{0}^{1} \left. \frac{ \partial^{2} f }{ \partial x_{i} \partial x_{j}}  \right| _{a+t(x-a)} \, dt $$

> [!proof]-
> Let $$g_{i}(x):=\int_{0}^{1}\left.  \frac{ \partial f }{ \partial x_{i} }  \right| _{a+t(x-a)} \, dt $$Then, $g_{i}\in C^\infty(U)$ and by Hadamard's Lemma, $$\begin{align}g_{i}(x)&=g_{i}(a)+\sum_{j=1}^{n}(x_{j}-a_{j})\int_{0}^{1} \left. \frac{ \partial^{2} f }{ \partial x_{i} \partial x_{j}}  \right| _{a+t(x-a)} \, dt\\&= \left. \frac{ \partial f }{ \partial x_{i} }  \right| _{a} +\sum_{j=1}^{n}(x_{j}-a_{j})\int_{0}^{1} \left.\frac{ \partial^{2} f }{ \partial x_{i} \partial x_{j}}  \right| _{a+t(x-a)} \, dt\end{align} $$
> Therefore, $$\begin{align}f(x)&=f(a)+\sum_{i=1}^{n}(x_{i}-a_{i})\int_{0}^{1}  \left. \frac{ \partial f }{ \partial x_{i} }  \right| _{a+t(x-a)}\, dt\\&=f(a)+\sum_{i=1}^{n}(x_{i}-a_{i})\left( \left. \frac{ \partial f }{ \partial x_{i} }  \right| _{a} +\sum_{j=1}^{n}(x_{j}-a_{j})\int_{0}^{1} \left. \frac{ \partial^{2} f }{ \partial x_{i} \partial x_{j}}  \right| _{a+t(x-a)} \, dt \right) \\&=f(a)+\sum_{i=1}^{n}(x_{i}-a_{i}) \left. \frac{ \partial f }{ \partial x_{i} }  \right| _{a} +\sum_{i,j=1}^{n}(x_{i}-a_{i})(x_{j}-a_{j})\int_{0}^{1} \left. \frac{ \partial^{2} f }{ \partial x_{i} \partial x_{j}}  \right| _{a+t(x-a)} \, dt \end{align}$$
---
> [!lemma] Theorem 3 (Inverse Function Theorem)
> Let $U\subseteq \mathbb{R}^n$ be open and $f:U\to \mathbb{R}^n$ be $C^r$ for $r\geq 1$. If the [[Jacobian matrix]] $$D_{x}f:=\left\{  \frac{ \partial f_{i} }{ \partial x^j }   \right\}_{i,j=1,\dots,m}$$is invertible at $x_{0}\in U$. Then, there exist open neighborhoods $x_{0}\in V\subseteq U$ and $f(x_{0})\in W$ s.t.
> 1. $f|_{V}:V\to W$ is a $C^r$-diffeomorphism.
---
> [!lemma] Theorem 4 (Rank Theorem)
> Let $A_{0}\subseteq \mathbb{R}^m$ and $B_{0}\subseteq \mathbb{R}^n$ be open and $f:A_{0}\to B_{0}$ be a $C^r$-map. If $f$ has constant [[rank]] $k$ on $A_{0}$, for any $a_{0}\in A_{0}$,
> 1. there exists $a_{0}\in A\subseteq A_{0}$, $f(a_{0})\in B\subseteq B_{0},U\subseteq \mathbb{R}^m,V\subseteq \mathbb{R}^n$ open and
> 2. there exists $C^r$-diffeomorphisms $\psi:A\to U$ and $\varphi:B\to V$ s.t. $\psi(a_{0})=0$ and $\varphi(f(a_{0}))=0$ with:$$(\varphi \circ f\circ \psi ^{-1})(x_{1},\dots,x_{m})=(x_{1},\dots,x_{k},0,\dots,0)$$

^374b28

> [!proof]-
> Modulo altering $\varphi,\psi$ with translations, we may assume that $a_{0}=0$ and $f(a_{0})=0$ without loss of generality. Modulo permuting coordinates in $\mathbb{R}^n$ and $\mathbb{R}^m$ we may assume that the first principal $k\times k$-minor of $d_{0}f$ has non-zero determinant, that is: $$\det \left[ \frac{ \partial f_{j} }{ \partial x^i }  \right]_{i,j\in [k]}\neq 0 $$Define $\psi(x):=(f_{1}(x),\dots,f_{k}(x),x_{k+1},\dots,x_{m})$ where $f(x)=(f_{1}(x),\dots,f_{n}(x))$. Then, for $x\in A_{0}$, $$d_{x}\psi =\begin{bmatrix}\left[ \frac{ \partial f_{j} }{ \partial x^i }  \right]_{i,j\in [k]}&*\\0&I_{m-k}\end{bmatrix}$$Therefore, $\det d_{x}\psi=\det \left[ \frac{ \partial f_{j} }{ \partial x^i }  \right]_{i,j\in [k]}\neq 0$. By applying inverse function theorem on $\psi$, we get open neighborhoods $A_{1}\subseteq A_{0}$ and $U_{1}\subseteq \mathbb{R}^m$ of $0$ respectively, s.t. $\psi|_{A_{1}}:A_{1}\to U_{1}$ is a $C^r$-diffeomorphism. Then, consider $f\circ\psi ^{-1}$ on $U_{1}$. Let $y\in U_{1}$ for $y=\psi(x)$ with $x\in A_{1}$. Then, $$\begin{align}f\circ \psi ^{-1}(y)&=(f\circ \psi ^{-1})(f_{1}(x),\dots,f_{k}(x),x_{k+1},\dots,x_{m})\\&=(f_{1}(x),\dots,f_{n}(x))\\&=(y_{1},\dots,y_{k},F_{k+1}(y),\dots,F_{n}(y))\end{align}$$where $F_{\ell}(y)=f_{\ell}(x)$. Then, $f\circ\psi ^{-1}$ has constant rank $k$ as well. As we have $d_{y}(f\circ\psi ^{-1})=d_{x}f\circ d_{y}\psi ^{-1}$Therefore, $$\left[ \frac{ \partial F_{i} }{ \partial y_{j} }  \right]_{{k+1\leq i,j\leq n}} $$vanishes. Modulo replacing $U_{1}$ with a smaller connected $\varepsilon$-ball we may thus assume that the functions $F_{k+1},..,F_{n}$ only depend on $y_{1},\dots,y_{k}$. Thus $$f\circ \psi ^{-1}(y_{1},\dots,y_{n})=(y_{1},\dots,y_{k},F_{k+1}(y_{1},\dots,y_{k}),\dots,F_{n}(y_{1},\dots,y_{k}))$$ Now define $T(z):=(z_{1},\dots,z_{k},z_{k+1}+F_{k+1}(z_{1},\dots,z_{k}),\dots,z_{n}+F_{n}(z_{1},\dots,z_{k}))$ for $z\in \mathbb{R}^n$ with $(z_{1},\dots,z_{k})\in \text{pr}^k(U_{1})$, the projection onto the first $k$ coordinates. Then, $T(0)=0$ and: $$d_{z}T=\begin{bmatrix}\text{Id}_{k}&0\\ *&\text{Id}_{n-k}\end{bmatrix}$$is invertible. By the inverse function theorem, there exists $B_{1}\subseteq \mathbb{R}^n$ containing $0$ s.t. $T:B_{1}\to T(B_{1})$ is a $C^r$-diffeomorphism. Furthermore, $$T(z_{1},\dots,z_{k},0,\dots,0)=f\circ \psi ^{-1}(z_{1},\dots,z_{k},0,\dots,0)$$Therefore, by setting $\varphi=T^{-1}$, we have that $(\varphi f\psi ^{-1})(y_{1},\dots,y_{n})=(y_{1},\dots,y_{k},0,\dots,0)$

^c35ca3

- **Corollary**: For smooth manifolds $M,N$ with $f\in C^\infty(M,N)$ with constant rank $k$. For $p\in M$, there exists $(U,\varphi)$ centered at $p$ and $(V,\psi)$ centered at $F(p)$ s.t. $\varphi(U)=(-\varepsilon,\varepsilon)^m$ and $\psi(V)=(-\varepsilon,\varepsilon)^n$ with: $\psi f\varphi ^{-1}(x_{1},\dots,x_{n})=(x_{1},\dots,x_{k},0,\dots,0)$ for some $\varepsilon>0$. ^a2f39f
---
##### Examples
> [!h] Example 1
> Let $M$ be a smooth manifold and $W\subseteq M$ be an open set. Then, the inclusion $\iota:W\hookrightarrow M$ is smooth.
---
