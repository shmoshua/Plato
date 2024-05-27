#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]]. A map $f:M\to N$ is 
> 1. $C^k$ or ***$k$-times continuously differentiable***, if for any chart $(U,\varphi)$ in $M$ and $(V,\psi)$ in $N$, $$\psi f\varphi ^{-1}:\varphi(U)\to \psi(V)\in C^k(\mathbb{R}^m,\mathbb{R}^n)$$
> 2. $C^\infty$ or ***smooth***, if $f\in C^k$ for all $k\geq 1$.
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
##### Examples
> [!h] Example 1
> Let $M$ be a smooth manifold and $W\subseteq M$ be an open set. Then, the inclusion $\iota:W\hookrightarrow M$ is smooth.
---
