#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. A ***Riemannian metric*** $g$ on $M$ assigns to each $p\in M$, a SPD bilinear form $g_{p}:T_{p}M\times T_{p}M\to \mathbb{R}$ s.t. for all $V,W\in \Gamma(TM)$, $$\begin{array}{cccc} &{M}&\to&{\mathbb{R}}\\&{p} &\mapsto & {g_{p}(V(p),W(p))} \end{array}{}$$is smooth.
- **Related definition**: For a chart $(\varphi,U)$, we have the local coordinates $(x^1,\dots,x^m)$ on $U$. Then, $$g_{ij}(p):=g_{p}\left( \left. \frac{ \partial  }{ \partial x^i }   \right|_{p},\left. \frac{ \partial  }{ \partial x^j }   \right|_{p} \right) $$are called ***metric coefficients***. Then, they're:
	1. **symmetric**: $g_{ij}=g_{ji}$.
	2. **positive definite**: $\sum_{i,j=1}^{m}g_{ij}v^iv^j=g(V,V)\geq 0$ where $V=\sum_{i=1}^{m}v^i \left. \frac{ \partial  }{ \partial x^i } \right|_{p}$.
	3. **smoothness**: $g_{ij}(p)$ is smooth in $p$.
- **Remark**: One can also write the Riemannian metric from the metric coefficients as follows: $$g_{p}:=\sum_{i,j=1}^{m}g_{ij}(p)\cdot d_{p}x^i \otimes  d_{p}x^j$$where $\xi \otimes \eta:T_{p}M\times T_{p}M\to \mathbb{R}, (v,w)\mapsto \xi(v)\eta(w)$ for $\xi,\eta\in T^{*}_{p}M$ is a bilinear form on $T_{p}M$.
---
