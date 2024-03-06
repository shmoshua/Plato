#Definition #DifferentialGeometry 
> [!definition]
> A ***smooth vector field*** $V$ on a [[smooth manifold]] $M$ is a map $X:M\to \text{T}M$ s.t. $\pi \circ X=\text{id}_{M}$, where $\pi:\text{T}M\to M$ is the natural projection from the [[tangent bundle]], i.e. for all $p\in M$, $X(p)\in \{ p \}\times\text{T}_{p}M$.

---
- **Related definition**: $\Gamma(TM)$ denotes the space of all smooth vector fields.
- **Related definition**: $V\in \Gamma(TM)$ defines a ***derivation*** on $C^\infty(M)$, $f\mapsto Vf$ where: $$\begin{array}{cccc} {Vf:}&{M}&\to&{\mathbb{R}}\\&{p} &\mapsto & {V(p)(f)} \end{array}{}$$
	i.e. $Vf$ is the [[Tangent Space|directional derivative]] of $f$ at each point $p$ according to the tangent vector $V(p)$.
- **Remark**: Given a derivation $D:C^\infty(M)\to C^\infty(M)$ with $D(fg)=fD(g)+gD(f)$, there exists a unique $V\in \Gamma(TM)$ s.t. $D(f)=Vf$.
- **Related definition**: ***Lie derivative*** of smooth vector fields $V,W$, $\mathcal{L}_{V}W\equiv[V,W]$ is the derivation $f\mapsto VWf-WVf$ where $[V,W]\in \Gamma(TM)$ is the **commutator**.
---