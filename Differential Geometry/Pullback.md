#Definition #DifferentialGeometry 
> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]], $F:N\to M$ a [[Smooth Function|smooth map]] and $g$ a [[Riemannian metric]] on $M$. Then, the ***pullback of $g$ along $F$***  is: 
> $$(F^{*}g)_{p}(v,w):=g_{F(p)}(d_{p}F(v),d_{p}F(w))$$for $p\in N$, $v,w\in$ [[Tangent Space|$T_{p}N$]].
---
##### Properties
> [!lemma] Proposition 1
> If $F$ is an [[Differential|immersion]], then $F^{*}g$ is a [[Riemannian metric]] on $N$. 

> [!proof]+
> Firstly, as $d_{p}F$ is linear and $g_{F(p)}$ is bilinear, $(F^{*}g)$ is bilinear. Further, from the symmetry of $g_{F(p)}$, $F^{*}g$ is symmetric.
> 
> For the positive definiteness, if $F$ is an immersion, $d_{p}F$ is injective and for every non-zero $v\in T_{p}N$, $d_{p}F(v)\neq 0$ and $$(F^{*}g)_{p}(v,v)=g_{F(p)}(d_{p}F(v),d_{p}F(v))>0$$
> 
> Lastly, for two smooth vector fields $V,W\in \Gamma(TN)$:$$(F^{*}g)_{p}(V(p),W(p))=g_{F(p)}(d_{p}F(V(p)),d_{p}F(W(p)))$$

 
---

Example: $M=\mathbb{R}^m$, $F:N\subseteq \mathbb{R}^n\hookrightarrow M=\mathbb{R}^m$ embedding. Then, $F^*g_{\text{Euclidean}}$ is the induced metric.

---
A smooth map $F:(N,k)\mapsto(M,g)$ is a local isometry if it is a local diffeomoroism and $F^{*}g=h$. for all $p\in N$, there existrs an open neighborhood $U$ s.t. $F|_{U}$ is a diffeomorphism

Example: $F:()$