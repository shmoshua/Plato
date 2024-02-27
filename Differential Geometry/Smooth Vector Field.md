#Definition #DifferentialGeometry 
> [!definition]
> A ***smooth vector field*** $V$ on a [[smooth manifold]] $M$ is a map $V:M\to TM$ s.t. 
> 1.  $V(p)\in T_{p}M$
> 2. for all charts $(U,x)$ on $M$, there exists a [[smooth function]] $v:U\to \mathbb{R}^m$ s.t. for all $p\in U$:$$V(p)=[x,v(p)]_{p}$$
>    
>   Then, $\Gamma(TM)$ denotes the space of all vector fields.
- **Related definition**: $V\in \Gamma(TM)$ defines a ***derivation*** on $C^\infty(M)$, $f\mapsto Vf$ where: $$\begin{array}{cccc} {Vf:}&{M}&\to&{\mathbb{R}}\\&{p} &\mapsto & {V(p)(f)} \end{array}{}$$
	
- $f\mapsto Vf$ where $(Vf)(p)=V(p)(f)$.
- **Remark**: Given a derivation $D:C^\infty(M)\to C^\infty(M)$ with $D(fg)=fD(g)+gD(f)$, there exists a unique $V\in \Gamma(TM)$ s.t. $D(f)=Vf$.
- **Related definition**: ***Lie derivative*** of smooth vector fields $V,W$, $\mathcal{L}_{V}W\equiv[V,W]$ is the derivation $f\mapsto VWf-WVf$ where $[V,W]\in \Gamma(TM)$ is the **commutator**.
---