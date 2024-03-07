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
> 3. For another smooth manifold $N$ and a smooth map $\psi:M\to N$, the [[pullback]] $\psi ^{*}$ is defined as: $$\begin{array}{cccc} {\psi ^{*}:}&{\Omega^1(N)}&\to&{\Omega^1(M)}\\&{\omega} &\mapsto & {p\mapsto \omega_{\psi(p)}\circ d_{p}\psi} \end{array}{}$$
>    Further, the following diagram commutes:
>    $$\begin{CD}C^\infty(N) @> d^N>> \Omega^1(N)\\@V\psi ^{*}VV & @VV\psi ^{*}V\\C^\infty(M) @> d^M> > \Omega^1(M)\end{CD}$$

---
> [!h] Example 2
> Let $M$ be a smooth manifold and $(U,\varphi)$ a chart. 
> 1. For $\pi_{i}:\mathbb{R}^m\to \mathbb{R}, x\mapsto x_{i}$, $\pi_{i}\in C^\infty(\mathbb{R}^m)$ and $d\pi_{i}\in \Omega^1(\mathbb{R}^m)$ where: $$(d\pi_{i})_{x}v =\pi_{i}(v)=v_{i}$$
> 2. The pullback $dx_{i}:=\varphi ^{*}(d\pi_{i})\in\Omega^1(U)$ and at every $p\in M$, $\{ dx_{i} \}_{i}$ form a basis of $\text{T}_{p}M^{*}$ at every $p\in U$.
> 3. For every $\omega\in \Omega(M)$, we can write: $$\omega_{x}=\sum_{i=1}^{n}a_{i}(x)(dx_{i})_{x}$$where $a_{i}:U\to \mathbb{R}$ are smooth. Further, $\omega=\sum_{i=1}^{n}a_{i}dx_{i}$ in $\Omega^1(U)$. 
---

