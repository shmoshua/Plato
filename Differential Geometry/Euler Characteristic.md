#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a compact Riemannian manifold. Then, the ***Euler characteristic*** is given by: $$\chi(M):=v-e+f$$where $v,e,f$ are the number of vertices, edges and triangles of a triangularization of $M$ respectively.
- **Remark**: The Euler characteristic $\chi(M)$ is independent of the triangularization. 
---
##### Properties
> [!lemma] Theorem 1
> $\chi(M)=2-2\cdot\text{genus}(M)$
---
> [!lemma] Theorem 2 (Gauss-Bonnet)
> Let $(M,g)$ be a compact [[Riemannian Manifold|Riemannian $2$-manifold]]. Then: $$\int_{M}^{} K_{M} \, dA=2\pi \chi(M) $$
---
> [!lemma] Theorem 3 (Uniformization Theorem)
> Let $M$ be a compact surface. Then, $M$ possesses a metric $g$ of constant curvature, given by:
> 1. $K_{M}\equiv 1$ if and only if $\chi(M)>0$,
> 2. $K_{M}\equiv 0$ if and only if $\chi(M)=0$, and 
> 3. $K_{M}\equiv -1$ if and only if $\chi(M)<0$.