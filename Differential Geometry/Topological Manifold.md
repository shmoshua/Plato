#Definition #DifferentialGeometry 

> [!definition]
> A ***topological manifold $M$ of dimension $m$*** is a 2nd-countable [[Hausdorff space]] s.t. for all $p\in M$, there exists an open neighborhood $U_{p}\subseteq M$ s.t. $\phi:U\to \phi(U)\subseteq \mathbb{R}^m$ is a homeomorphism.

1. $(\phi,U), (\psi,V)$ are ***compatible***, if $\phi \circ\psi ^{-1}$ with $\psi(U\cap V)\to \phi(U\cap V)$ is a smooth diffeomorphism.
2. A ***smooth manifold*** is a pair $(M)$ where
	- $M$ is a topological manifold equipped with a smooth structure = maximal atlas = maximal system of charts $(\phi_{\alpha},U_{\alpha})$ s.t. $\phi_{\alpha},\phi_{\beta}$ are compatible for all $\alpha,\beta$.
3. For $p\in M$, the ***tangent space*** is defined as: $$T_{p}M=\{ [\varphi_{i}v]:\varphi \text{ chart around }p, v\in \mathbb{R}^m \}_{/\sim}$$where $[\varphi,v]\sim[\psi,w]\iff w=d_{\varphi(p)}(\psi \circ\varphi ^{-1})v$
4. $T_{p}M$ is an $m$-dimensional vector space.
5. Let $F:M\to N$ be a smooth map between manifolds, i.e. $\psi F\varphi ^{-1}$ is a $C^\infty$-map between open subsets of $\mathbb{R}^m$ and $\mathbb{R}^n$. 
6. The ***differential*** is defined as: $$\begin{array}{cccc} {d_{p}F:}&{T_{p}M}&\to&{T_{F(p)}N}\\&{[\varphi,v]_{p}} &\mapsto & {[\psi,d_{\varphi(p)}(\psi F\varphi ^{-1})(v)]_{F(p)}} \end{array}{}$$
##### Interpretation of Tangent vectors
1. Tangent vectors of $C^\infty$-curves $\gamma:(-1,1)\to M$, $\gamma(0)=p$, $$\left[ \varphi, \frac{d}{dt}\varphi(\gamma(t))|_{t=0} \right]_{p}=\gamma'(0)\in T_{p}M$$
2. Directional derivatives. $f:M\xrightarrow{C^\infty} \mathbb{R}$, $V\in T_{p}M$, $$Vf= \frac{d}{dt}(f\circ \varphi ^{-1})(\varphi(p)+tv)|_{t=0}$$
3. Notation: $\frac{ \partial  }{ \partial \varphi^i }|_{p}=[\varphi,e_{i}]_{p}$,
4. $V=V^i \frac{ \partial  }{ \partial \varphi^i }|_{p}=\sum_{i=1}^{m}V^i\frac{ \partial  }{ \partial \varphi^i }|_{p}$
##### Vector fields
1. A smooth vector field $V$ on $C^\infty$-$M$ is a map $$\begin{array}{cccc} {V:}&{M}&\to&{TM:=\bigsqcup_{p\in M}^{}T_{p}M}\\&{p} &\mapsto & {[\varphi,v(p)]_{p}} \end{array}{}$$where $v:U\to \mathbb{R}^m$ is smooth.
2. $\Gamma(TM)$ is the space of all vector fields.
3. $V\in \Gamma(TM)$ defines a derivation on $C^\infty(M)$ by $(Vf)(p)=V(p)(f)$
4. Conversely, given a derivation $D:C^\infty(M)\to C^\infty(M)$, i.e. $D(fg)=fD(g)+gD(f)$, there exists a unique $V\in \Gamma(TM)$ s.t. $D(f)=Vf$.
5. Lie derivative of a vector fields $V,W$, $\mathcal{L}_{V}W\equiv[V,W]$ is the derivation $f\mapsto VWf-WVf$.where $[V,W]\in \Gamma(TM)$ is the **commutator**.
---
##### Cotangent Space
The **cotangent space** $T^*_{p}M$ is the linear dual space $\{ \xi:T_{p}M\to \mathbb{R} \}$. 

Given a chart $\varphi$, a basis of $T_{p}^{*}M$ is given by: $$\begin{array}{cccc} {d_{p}\varphi^i:}&{T_{p}M}&\to&{\mathbb{R}}\\&{\frac{ \partial  }{ \partial \varphi^j } |_{p}} &\mapsto & {\delta^i_{j}} \end{array}{}$$
Given a smooth function $f\in C^\infty(M)$, set $d_{p}f\in T_{p}^{*}M$, $d_{p}f(V):=Vf$.

---
##### Riemannian Metrics
$M$ is a $C^\infty$-manifold.
1. A ***Riemannian metric*** $g$ on $M$ assigns to each $p\in M$, a symmetric, linear, positive definite form: $$\begin{array}{cccc} {g_{p}:}&{T_{p}M\times T_{p}M}&\to&{\mathbb{R}}\\&{} &\mapsto & {} \end{array}{}$$s.t. for all $V,W\in \Gamma(TM)$, $p\in M\mapsto g_{p}(V(p),W(p))\in \mathbb{R}$ is smooth.
2. A ***Riemannian manifold*** is a pair $(M,g)$.
3. Local coordinate description: For a chart $\varphi$, we have the local coordinates $(\varphi^1,\dots,\varphi^m)$ on $U$. Then, $$g_{ij}(p):=g_{p}\left( \frac{ \partial  }{ \partial \varphi^i } |_{p},\frac{ \partial  }{ \partial \varphi^j } |_{p} \right) $$ $g_{ij}(p)$ is smooth in $p$ as long as $p\in U$ and are called metric coefficients s.t.
	- Symmetry: $g_{ij}=g_{ji}$
	- Positive definite: $g_{ij}(p)v^iv^j>0$ for all $v\in \mathbb{R}^m \backslash \{ 0 \}$.
	- Conversely, we can write: $$g_{p}:=\sum_{i,j=1}^{m}g_{ij}(p)d_{p}\varphi^i \otimes  d_{p}\varphi^j$$Here, $\xi,\eta\in T^{*}_{p}M$, then $\xi \otimes \eta:T_{p}M\times T_{p}M\to \mathbb{R}, (v,w)\mapsto \xi(v)\eta(w)$ is a bilinear form on $T_{p}M$.
4. Notation: $d_{p}\varphi^id_{p}\varphi^j= \frac{1}{2}\left(  d_{p}\varphi^i \otimes  d_{p}\varphi^j+d_{p}\varphi^j \otimes  d_{p}\varphi^i \right)$ with $g=g_{ij}d\varphi^id\varphi^j$
5. $\left| V \right|_{g}^{2}=g_{p}(V,V)$ for $V\in T_{p}M$.
---
##### Examples
1. $M=\mathbb{R}^m$, chart $x^1,\dots,x^m$ standard coordinates. Then, $$g:=\sum_{i=1}^{m}dx^i\otimes dx^i$$is the Euclidean metric. Identify $\frac{ \partial  }{ \partial x^i }$ with $e_{i}\in \mathbb{R}^m$. Then, $g\left( \frac{ \partial  }{ \partial x^j },\frac{ \partial  }{ \partial x^k } \right)=\delta_{jk}=\braket{ e_{j} , e_{k} }$
2. $M=(0,\infty)\times(0,2\pi)$, with coordinates $r,\varphi$. $$g=dr^{2}+r^{2}d\varphi^{2}$$is the Euclidean coordinates in polar coordinates.
3. Let $M$ be a smooth manifold. Then there exists a Riemannian metric on $M$. 

Let $F:N\to M$ be a smooth map, $g$ a Riemmanian metric on $M$. Then, pullback of $g$ along $F$ is: $$(F^{*}g)_{p}(V,W)=g_{F(p)}(d_{p}F(V),d_{p}F(W))$$for $p\in N$, $V,W\in T_{p}N$

If $F$ is an immersion (i,e $d_{p}F is injective for all $p$$), then $F^{*}g$ is a Riemannian metric on $N$.