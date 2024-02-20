#Definition #MeasureTheory 
> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]], $F:N\to M$ a smooth map and $g$ a [[Riemannian metric]] on $M$. Then, the ***pullback*** of $g$ along $F$ is : $$(F^{*}g)_{p}(V,W):=g_{F(p)}(d_{p}F(V),d_{p}F(W))$$for $p\in N$, $V,W\in T_{p}N$.
---
##### Properties
> [!lemma] Proposition 1
> If $F$ is an immersion, i.e. $d_{p}F:T_{p}N\to T_{F(p)}M$ is injective for all $p\in N$, then $F^{*}g$ is a [[Riemannian metric]] on $N$. 

> [!proof]- Proof (Incomplete)
> We show that:
> 1. **$(F^{*}g)_{p}$ is bilinear**:
>    For $[\varphi_{1},v]_{p},[\varphi_{2},w]_{p}\in T_{p}N$, $$(F^{*}g)_{p}([\varphi_{1},v]_{p},[\varphi_{2},w]_{p})=g_{F(p)}([\psi_{1},d_{\varphi(p)}(\psi F\varphi ^{-1})(v)]_{F(p)},[\psi_{2},d_{\varphi(p)}(\psi F\varphi ^{-1})(w)]_{F(p)})$$
> 2. 
 
---

Example: $M=\mathbb{R}^m$, $F:N\subseteq \mathbb{R}^n\hookrightarrow M=\mathbb{R}^m$ embedding. Then, $F^*g_{\text{Euclidean}}$ is the induced metric.

---
A smooth map $F:(N,k)\mapsto(M,g)$ is a local isometry if it is a local diffeomoroism and $F^{*}g=h$. for all $p\in N$, there existrs an open neighborhood $U$ s.t. $F|_{U}$ is a diffeomorphism

Example: $F:()$