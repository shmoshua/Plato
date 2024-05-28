#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[topological manifold]] of dimension $m$. A ***smooth atlas*** on $M$ is a collection: $$\mathcal{X}:=\{ x_{\alpha}:U_{\alpha}\to x_{\alpha}(U_{\alpha})\subseteq \mathbb{R}^m \}_{\alpha}$$where $U_{\alpha}$ is open, $x_{\alpha}$ is a [[homeomorphism]] s.t.
> 1. $M=\bigcup_{\alpha\in A}^{}U_{\alpha}$ and
> 2. $x_{\beta}\circ x_{\alpha}^{-1}: x_{\alpha}(U_{\alpha}\cap U_{\beta})\to x_{\beta}(U_{\alpha}\cap U_{\beta})$ is a [[diffeomorphism]] for all $\alpha,\beta\in A$

- **Related definition**: the maps $x_{\alpha}$ are called ***charts***, the maps $x_{\beta}\circ x_{\alpha}^{-1}$ are called ***transition maps***.
- **Related definition**: two smooth atlases $\mathcal{X},\mathcal{Y}$ are ***equivalent***, if their union is also a smooth atlas.
---
##### Properties
> [!lemma] Proposition 1
> Let $M$ be a [[smooth manifold]] and 
> 1. for $y^1,\dots,y^m\in C^\infty(M)$ s.t. $\{ d_{p}y^i \}\subseteq \text{T}^{*}_{p}M$ are linearly independent, there exists a chart on a neighborhood of $p$ with $y^1,\dots,y^m$ as coordinate functions.
> 2. for $y^1,\dots,y^\ell\in C^\infty(M)$ with $\ell<m$ s.t. $\{ d_{p}y^i \}\subseteq \text{T}^{*}_{p}M$ are linearly independent, there exists a chart on a neighborhood of $p$ with $y^1,\dots,y^\ell$ as part of coordinate functions.
> 3. let $N$ be another smooth manifold and $F\in C^\infty(M,N)$. If $d_{p}F$ is surjective and $x^1,\dots,x^\ell$ are part of coordinate functions on a neighborhood of $F(p)$, then $x^1\circ F,\dots,x^\ell \circ F$ are a part of coordinate functions on a neighborhood of $p$.

> [!proof]-
> We have:
> 1. Suppose $y^i$ are defined on an open neighborhood $U\ni p$. Then, define $\varphi :M\to \mathbb{R}^m$: $$\varphi(p):=(y^1(p),\dots,y^m(p))$$Then, $\varphi\in C^\infty(M,\mathbb{R}^m)$. Therefore, $\delta\varphi:(\mathbb{R}_{\varphi(p)}^m)^{*}\to \text{T}^{*}_{p}M$ is an isomorphism as: $$\delta\varphi(d_{\varphi(p)}\pi^i)=d_{\varphi(p)}\pi^i\circ d_{p}\varphi=d_{p}(\pi^i\circ \varphi)=d_{p}y^i$$and $\delta\varphi$ maps the basis to the basis. Consequently, its dual $d_{p}\varphi$ is an isomorphism. By [[Differential|Inverse Function Theorem]], $\varphi$ is a diffeomorphism on $V\subseteq U$ and $(V,\varphi)$ is a chart.
> 2. Let $(U,\varphi)$ be a chart at $p$ with coordinates $x^1,\dots,x^m$. Then, there exists $x^{n_1},\dots,x^{n_{m-\ell}}$ s.t. $$\{ d_{p}y^1,\dots,d_{p}y^\ell, d_{p}x^{n_{1}},\dots,d_{p}x^{n_{m-\ell}} \}$$is linearly independent. Now, apply 1.
> 3. As $d_{p}F$ is surjective, $\delta_{F(p)} F$ is injective. Therefore, 
>    $$d_{p}(x^i\circ F)=d_{F(p)}x^i\circ d_{p}F=\delta_{F(p)}F(d_{F(p)}x^i)$$and $\{ d_{p}(x^i\circ F) \}$ are linearly independent. Now, apply 2.
>    
---
