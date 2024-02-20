#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. A ***Riemannian metric*** $g$ on $M$ assigns to each $p\in M$ a SPD bilinear form $g_{p}:T_{p}M\times T_{p}M\to \mathbb{R}$ s.t. for all $V,W\in \Gamma(TM)$, $$\begin{array}{cccc} &{M}&\to&{\mathbb{R}}\\&{p} &\mapsto & {g_{p}(V(p),W(p))} \end{array}{}$$is smooth.
- **Related definition**: For a chart $(\varphi,U)$, we have the local coordinates $(x^1,\dots,x^m)$ on $U$. Then, $$g_{ij}(p):=g_{p}\left( \left. \frac{ \partial  }{ \partial x^i }   \right|_{p},\left. \frac{ \partial  }{ \partial x^j }   \right|_{p} \right) $$are called ***metric coefficients***. Then, they're:
	1. **symmetric**: $g_{ij}=g_{ji}$.
	2. **positive definite**: $\sum_{i,j=1}^{m}g_{ij}v^iv^j=g(V,V)\geq 0$ where $V=\sum_{i=1}^{m}v^i \left. \frac{ \partial  }{ \partial x^i } \right|_{p}$.
	3. **smoothness**: $g_{ij}(p)$ is smooth in $p$.
- **Remark**: One can also write the Riemannian metric from the metric coefficients as follows: $$g_{p}:=\sum_{i,j=1}^{m}g_{ij}(p)\cdot d_{p}x^i \otimes  d_{p}x^j$$where $\xi \otimes \eta:T_{p}M\times T_{p}M\to \mathbb{R}, (V,W)\mapsto \xi(V)\eta(W)$ for $\xi,\eta\in T^{*}_{p}M$ is a bilinear form on $T_{p}M$.
---
##### Properties
> [!lemma] Proposition 1
> Let $M$ be a smooth manifold. Then, there exists a Riemannian metric $g$ on $M$.
---
##### Examples
> [!lemma] Example 1
> Let $M=\mathbb{R}^m$ and $(x^1,\dots,x^m)$ be standard coordinates. Then, $$g:=\sum_{i=1}^{m}dx^i\otimes dx^i$$is the Euclidean metric. 
---
> [!lemma] Example 2
> Let $M=(0,\infty)\times(0,2\pi)$ with coordinates $r,\varphi$. Then, $$g=dr^{2}+r^{2}d\varphi$$is the Euclidean metric in polar coordinates.
---