#Definition #DifferentialGeometry 

> [!definition]
> A ***section*** $s$ of a [[vector bundle]] $(E,\pi,M)$ is a smooth map $s:M\to E$ s.t. $s(p)\in E_{p}$ for all $p\in M$. (In other words, $\pi \circ s=\text{id}$)

- **Related definition**: $\Gamma(E):=\{ s: M\to E\text{ section} \}$ is equal to the set of all smooth vector fields on $M$
---
##### Properties
> [!lemma] Lemma 1
> Every $T\in \Gamma(T_{r,s}M)$ defines a $C^\infty(M)$-multilinear map: $$\begin{array}{cccc} {}&{(\Gamma(T^{*}M))^r \times(\Gamma(TM))^s}&\to&{C^\infty(M)}\\&{(w_{1},\dots,w_{r},v_{1},\dots,v_{s})} &\mapsto & {p\mapsto T_{p}(w_{1}(p),\dots,w_{r}(p),v_{1}(p),\dots,v_{s}(p))} \end{array}{}$$
> Conversely, every such $C^\infty(M)$-multilinear map determines a unique element of $\Gamma(T_{(r,s)}M)$