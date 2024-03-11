#Definition #DifferentialGeometry 
> [!definition]
> A (smooth) ***vector field*** $X$ on a [[smooth manifold]] $M$ is a (smooth) [[Vector Bundle|section]] $X:M\to \text{T}M$ of the [[tangent bundle]], i.e. for all $p\in M$, $X(p)\in \{ p \}\times\text{T}_{p}M$.

---
- **Remark**: A vector field is a section of the tangent bundle and therefore, 
	1. $\Gamma(\text{T}M)$ denotes the space of all smooth vector fields.
- **Remark**: $\Gamma(\text{T}M)$ is also a $C^\infty(M)$-module, where $(fX)(x)=f(x)X(x)$ for all $x\in M$.
- **Related definition**: The local derivation property of a tangent vector can be extended globally: There is an isomorphism between $\Gamma(\text{T}M)\cong \text{Der }C^\infty(M)$ with $X\mapsto (f\mapsto Xf)$ where:$$\begin{array}{cccc} {Xf:}&{M}&\to&{\mathbb{R}}\\&{p} &\mapsto & {X_{p}f=d_{p}f(X_{p})} \end{array}{}$$

- **Related definition**: ***Lie derivative*** of smooth vector fields $V,W$, $\mathcal{L}_{V}W\equiv[V,W]$ is the derivation $f\mapsto VWf-WVf$ where $[V,W]\in \Gamma(TM)$ is the **commutator**.
---
##### Examples
> [!h] Example 1
> 