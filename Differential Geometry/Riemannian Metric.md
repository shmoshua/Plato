#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. A ***Riemannian metric*** $g$ on $M$ is a smooth family of [[Inner Product Space|inner products]] on the [[Tangent Space|tangent spaces]] of $M$. Namely, 
> 1. $g$ associates to each $p\in M$ a symmetric positive definite bilinear form $g_{p}:T_{p}M\times T_{p}M\to \mathbb{R}$ 
> 2. for all [[Smooth Vector Field|smooth vector fields]] $V,W\in \Gamma(TM)$, $$\begin{array}{cccc} &{M}&\to&{\mathbb{R}}\\&{p} &\mapsto & {g_{p}(V(p),W(p))} \end{array}{}$$is smooth.
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
> [!lemma] Lemma 2
> A Riemannian metric $g$ on $M$ defines an element of $\Gamma(T_{(0,2)}M)=\Gamma(T^{*}M\otimes T^{*}M)$. 
> Conversely, every $g\in \Gamma(T_{(0,2)}M)$ s.t. $$g_{p}\in (T_{(0,2)}M)_{p}=T^{*}_{p}M\otimes T^{*}_{p}M$$is a symmetric, positive definite bilinear form on $T_{p}M$. (smoothness in $p$ is encoded in $\Gamma(T_{(0,2)}M)$).
> 
> Further, $\{ d_{p}\varphi^i\otimes d_{p}\varphi^j ,1\leq i,j\leq m\}$ forms a basis of $T^{*}_{p}M\otimes T^{*}_{p}M$.
---
##### Examples
> [!lemma] Example 1
> Let $M=\mathbb{R}^m$ and $(x^1,\dots,x^m)$ be standard coordinates. Then, $$g:=\sum_{i=1}^{m}dx^i\otimes dx^i$$is the Euclidean metric. 
---
> [!lemma] Example 2
> Let $M=(0,\infty)\times(0,2\pi)$ with coordinates $r,\varphi$. Then, $$g=dr^{2}+r^{2}d\varphi$$is the Euclidean metric in polar coordinates.
---