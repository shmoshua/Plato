> [!definition]
> A ***Riemannian manifold*** is a pair $(M,g)$ where $M$ is a [[smooth manifold]] and $g$ is a [[Riemannian metric]].
---
Local coordinate description: For a chart $\varphi$, we have the local coordinates $(\varphi^1,\dots,\varphi^m)$ on $U$. Then, $$g_{ij}(p):=g_{p}\left( \frac{ \partial  }{ \partial \varphi^i } |_{p},\frac{ \partial  }{ \partial \varphi^j } |_{p} \right) $$ $g_{ij}(p)$ is smooth in $p$ as long as $p\in U$ and are called metric coefficients s.t.
	- Symmetry: $g_{ij}=g_{ji}$
	- Positive definite: $g_{ij}(p)v^iv^j>0$ for all $v\in \mathbb{R}^m \backslash \{ 0 \}$.
	- Conversely, we can write: $$g_{p}:=\sum_{i,j=1}^{m}g_{ij}(p)d_{p}\varphi^i \otimes  d_{p}\varphi^j$$Here, $\xi,\eta\in T^{*}_{p}M$, then $\xi \otimes \eta:T_{p}M\times T_{p}M\to \mathbb{R}, (v,w)\mapsto \xi(v)\eta(w)$ is a bilinear form on $T_{p}M$.
4. Notation: $d_{p}\varphi^id_{p}\varphi^j= \frac{1}{2}\left(  d_{p}\varphi^i \otimes  d_{p}\varphi^j+d_{p}\varphi^j \otimes  d_{p}\varphi^i \right)$ with $g=g_{ij}d\varphi^id\varphi^j$
5. $\left| V \right|_{g}^{2}=g_{p}(V,V)$ for $V\in T_{p}M$.