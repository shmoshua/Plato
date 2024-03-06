#Definition #DifferentialGeometry 
> [!definition]
> Let $M$ be a [[smooth manifold]]. A ***differential 1-form*** on $M$ is a map $\omega:M\to \text{T}^{*}M$ s.t. $\pi \circ \omega=\text{id}_{M}$.
- **Related definition**: $\Omega^1(M)$ denotes the vector space of all smooth differential 1-forms. 
- **Remark**: $\Omega^1(M)$ is a $C^\infty(M)$-module with multiplicative structure given as $(f\omega)_{x}:=f(x)\omega_{x}$.
---
##### Examples
> [!h] Example 1
> Let $M$ be a smooth manifold and $f\in C^\infty(M)$. Then, the differential:
> 1. $df:p\mapsto d_{p}f\in \Omega^1(M)$
> 2. the derivative is a map: $$\begin{array}{cccc} {d:}&{C^\infty(M)}&\to&{\Omega^1(M)}\\&{f} &\mapsto & {df} \end{array}{}$$
---
> [!h] Example 2
> Let $M$ be a smooth manifold and $(U,\varphi)$ a chart. 
> 1. For $\pi_{i}:\mathbb{R}^m\to \mathbb{R}, x\mapsto x_{i}$, $\pi_{i}\in C^\infty(\mathbb{R}^m)$ a