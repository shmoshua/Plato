#Definition #DifferentialGeometry 

> [!definition]
> Let $(M,g)$ be a [[Riemannian Manifold|Riemannian manifold]]. Then, for $p\in M$, the ***musical isomorphisms*** are the following isomorphisms:$$\begin{array}{cccc} {\flat:}&{\text{T}M}&\to&{\text{T}^{*}M}\\&{(p,v)} &\mapsto & {v^\flat_{p}:=g_{p}(v,\cdot )} \end{array}{}$$and $\sharp:=\flat ^{-1}$.
- **Remark**: With $(U,\varphi)$ on $M$, in local coordinates, the Riemannian metric is $g=g_{ij}dx^i\otimes dx^j$ and for $v\in \text{T}M$, $v=v^i \frac{ \partial  }{ \partial x^i }$. Further, let $g^{ij}:=g_{ij}^{-1}$ and $\xi\in \text{T}^{*}M$, $\xi=\xi_{i}dx^i$. Then, 
	- $v^\flat=g_{ij}v^idx^j=v_{j}dx^j$ where $v_{j}:=\sum_{i=1}^{m}g_{ij}v^i$.
	- $\xi^\sharp=g^{ij}\xi_{i}\frac{ \partial  }{ \partial x^j }=\xi^j\frac{ \partial  }{ \partial x^j }$ where $\xi^j:=\sum_{i=1}^{m}g^{ij}\xi_{i}$
---
##### Properties
> [!lemma] Proposition
> For every $p\in M$, $\flat$ defines a vector space isomorphism.

> [!proof]-
> As $\flat$ is linear, we just have to check that $\flat$ is a bijection. The injectivity follows from the fact that $g_{p}$ defines an inner product. The surjectivity follows from 
---
