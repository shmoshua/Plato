#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]]. A map $\varphi:M\to N$ is $C^k$ or ***$k$-times continuously differentiable***, if for any chart $(U,x)$ in $M$ and $(V,y)$ in $N$, $$y\circ \varphi \circ x^{-1}:x(U)\to y(V)\in C^k(\mathbb{R}^m,\mathbb{R}^n)$$If $\varphi\in C^k$ for all $k\geq 1$, $\varphi$ is ***smooth***, i.e. $\varphi\in C^\infty$.
- **Related definition**: Let $M,N$ be compact, connected and [[Orientable Manifold|oriented]] with dimension $m$. Then, for a smooth function $F:N\to M$, the ***degree*** of $F$, $\deg(F)\in \mathbb{R}$ is the unique real number s.t. $$\begin{CD}\text{H}_{\text{dR}}^m(M) @>F^{*}>> \text{H}_{\text{dR}}^m(N)\\@VIVV&@VIVV&\\\mathbb{R} @> x\mapsto \text{deg}F\cdot x> > \mathbb{R}\end{CD}$$commutes.
---
##### Properties
> [!lemma] Lemma 1
> Let $M,N,L$ be smooth manifolds and $\varphi:M\to N$ and $\psi:N\to L$ be smooth maps. Then, $$\psi \circ \varphi:M\to L$$ is smooth.

> [!proof]-
> Let $p\in M$ and $(U,x)$ a chart on $M$ containing $p$. Further, let $(V,y)$ be a chart on $N$ containing $\varphi(p)$ and $(W,z)$ a chart on $L$ containing $\psi(\varphi(p))$.  Then, $$z\circ (\psi \circ \varphi)\circ x^{-1}=(z\circ \psi \circ y^{-1})\circ (y\circ \varphi \circ x^{-1})$$which is a composition of two smooth functions in Euclidean space, which is smooth.
---
> [!lemma] Lemma 2
> Let $M,N$ be compact [[Smooth Manifold|smooth manifolds]] of dimension $m$ and $F:M\to N$ a smooth map. Further, let $q\in F(M)$ be [[Rank|regular]]. Then, 
> 1. $F^{-1}(q)$ is finite.
> 2. There exists an open connected set $V_{q}\subseteq N$ containing $q$ and for each $p\in F^{-1}(q)$ an open connected set $U_{p}\subseteq M$ containing $p$ s.t. $$F|_{U_{p}}:U_{p}\to V_{q}$$is a [[diffeomorphism]].

> [!proof]+
> Since $q$ is regular, for all $p\in F^{-1}(q)$, the differential $d_{p}F$ has full rank and is an isomorphism in this case. Therefore, by the inverse function theorem, there exist open neighborhoods $U'_{p}$ and $V'_{q}$ s.t. $F|_{U'_{p}}:U'_{p}\to V'_{q}$ is a diffeomorphism.
> 
> In particular, $U'_{p}\cap F^{-1}(q)=\{ p \}$. Therefore, $F^{-1}(q)$ is discrete in $M$ and finite by compactness of $M$. Now let $V_{q}$ to be the connected component of $\bigcap_{p\in F^{-1}(q)}^{}V'_{q}$ and $U_{p}:=(f|_{U'_{p}})^{-1}(V_{q})$.
---
##### Examples
> [!h] Example 1
> Let $M$ be a smooth manifold and $W\subseteq M$ be an open set. Then, the inclusion $\iota:W\hookrightarrow M$ is smooth.
---
