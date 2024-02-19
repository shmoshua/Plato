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
4. Conversely, given a derivation $D:C^\infty(M)\to C^\infty(M)$, i.e. $D(fg)=fD(g)+gD(f)$, there exists a unique $V\in \Gamma(TM)$ s.t. $D(f)=Vf$