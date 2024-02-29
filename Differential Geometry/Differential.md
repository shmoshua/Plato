#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $F:M\to N$ be a [[differentiable function|smooth function]]. Then, the ***differential*** is defined as follows: for a chart $(U,\varphi)$ at $p$ and $(V,\psi)$ at $F(p)$ s.t. $F(U)\subseteq V$: $$\begin{array}{cccc} {d_{p}F:}&{\text{T}_{p}M}&\to&{\text{T}_{F(p)}N}\\&{[U,\varphi,v]_{p}} &\mapsto & {[V,\psi,d_{\varphi(p)}(\psi F\varphi ^{-1})v]_{F(p)}} \end{array}{}$$
- **Remark**: given $f\in C^\infty(M)$, the differential at $p$ is defined as $$\begin{array}{cccc} {d_{p}f:}&{T_{p}M}&\to&{\mathbb{R}}\\&{[x,e_{i}]_{p}} &\mapsto & {[x,e_{i}]_{p}f} \end{array}{}$$
- **Related definition**: $F$ is an ***immersion***, if $d_{p}F$ is injective for all $p\in M$.
---
##### Properties
> [!lemma] Lemma 1
> For the differential, 
> 1. $d_{p}F$ is well-defined.
> 2. the [[rank]] of $F$ at $p$ is $\text{dim }d_{p}F(\text{T}_{p}M)$.

> [!proof]+
> We have:
> 1. Let $v\in \text{T}_{p}M$ represented by $[U_{1},\varphi_{1},v_{1}]$ and $[U_{2},\varphi_{2},v_{2}]$ and let $(V_{1},\psi_{1}),(V_{2},\psi_{2})$ be two charts at $F(p)$ where $F(U_{1})\subseteq V_{1},F(U_{2})\subseteq V_{2}$. Therefore, $$d_{\psi_{1}(F(p))}(\psi_{2}\psi_{1}^{-1})d_{\varphi(p)}(\psi F)$$

> [!lemma] Proposition 1
> Let $M,N$ be a [[smooth manifold]] and $F:N\to M$ be a [[Smooth Function|smooth map]]. Then, for a [[smooth vector field]] $V\in \Gamma(TM)$, $$\begin{array}{cccc} {F_{*}V:}&{N}&\to&{TN}\\&{p} &\mapsto & {d_{p}F(V(p))} \end{array}{}$$