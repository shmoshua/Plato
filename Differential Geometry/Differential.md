#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $F:M\to N$ be a [[Smooth Function|smooth map]]. Then, the ***differential*** is defined as: $$\begin{array}{cccc} {d_{p}F:}&{T_{p}M}&\to&{T_{F(p)}N}\\&{[x,v]_{p}} &\mapsto & {[y,d_{x(p)}(y\circ F\circ x^{-1})(v)]_{F(p)}} \end{array}{}$$
- **Remark**: given $f\in C^\infty(M)$, the differential at $p$ is defined as $$\begin{array}{cccc} {d_{p}f:}&{T_{p}M}&\to&{\mathbb{R}}\\&{[x,e_{i}]_{p}} &\mapsto & {[x,e_{i}]_{p}f} \end{array}{}$$
- **Related definition**: $F$ is an ***immersion***, if $d_{p}F$ is injective for all $p\in M$.
---
