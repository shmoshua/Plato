#Definition #DifferentialGeometry 
> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]], $F:N\to M$ a [[Smooth Function|smooth map]] and $g$ a [[Riemannian metric]] on $M$. Then, the ***pullback of $g$ along $F$***  is: 
> $$(F^{*}g)_{p}(v,w):=g_{F(p)}(d_{p}F(v),d_{p}F(w))$$for $p\in N$, $v,w\in$ [[Tangent Space|$T_{p}N$]].
---
##### Properties


---
 ##### Examples
> [!h] Pullback Smooth Functional
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and a [[Smooth Function|smooth map]] $F:N\to M$. Then, the the [[pullback]] is defined as: $$\begin{array}{cccc} {F ^{*}:}&{C^\infty(M)}&\to&{C^\infty(N)}\\&{g} &\mapsto & {g\circ F^{*}} \end{array}{}$$
---
> [!h] Pullback Differential 1-Form
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and a [[Smooth Function|smooth map]] $F:N\to M$. Then, the the [[pullback]] is defined as: $$\begin{array}{cccc} {F ^{*}:}&{\Omega^1(M)}&\to&{\Omega^1(N)}\\&{\omega} &\mapsto & {p\mapsto \omega_{F(p)}\circ d_{p}F} \end{array}{}$$
---
> [!h] Pullback Differential k-Forms
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $F:N\to M$ a [[Smooth Function|smooth map]]. Then, the [[pullback]] is defined as:$$\begin{array}{cccc} {F^{*}:}&{\Gamma(\Lambda^k(M))}&\to&{\Gamma(\Lambda^k(N))}\\&{\omega} &\mapsto & {F^{*}\omega} \end{array}{}$$where $(F^{*}w)_{x}(v_{1},\dots,v_{k}):=\omega_{F(x)}(d_{x}F(v_{1}),\dots,d_{x}F(v_{k}))$ for all $x\in N$ and $v_{1},\dots,v_{k}\in \text{T}_{x}N$.
---

Example: $M=\mathbb{R}^m$, $F:N\subseteq \mathbb{R}^n\hookrightarrow M=\mathbb{R}^m$ embedding. Then, $F^*g_{\text{Euclidean}}$ is the induced metric.

---
A smooth map $F:(N,k)\mapsto(M,g)$ is a local isometry if it is a local diffeomoroism and $F^{*}g=h$. for all $p\in N$, there existrs an open neighborhood $U$ s.t. $F|_{U}$ is a diffeomorphism

Example: $F:()$