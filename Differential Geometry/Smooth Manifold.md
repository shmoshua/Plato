#Definition #DifferentialGeometry 

> [!definition]
> A ***smooth manifold*** is a [[topological manifold]] $M$ equipped with a ***smooth structure*** $\mathcal{X}$, i.e. a maximal [[smooth atlas]] 
- **Related definition**: A map $f:M\to \mathbb{R}$
---
##### Properties
> [!lemma] Lemma 1
> Let $M$ be a smooth manifold of dimension $m$ and $W\subseteq M$ a non-empty open set. Then, $W$ naturally inherits the smooth structure of a smooth manifold of dimension $m$.

> [!proof]+
> Let $\mathcal{X}=\{ (U_{\alpha},x_{\alpha}) \}_{\alpha}$ be a smooth structure on $M$. Then, $$\{ x_{\alpha}|_{U_{\alpha}\cap W}: U_{\alpha}\cap W\to x_{\alpha}(U_{\alpha}\cap W)\}_{\alpha}$$is a smooth structure on $W$. 
> 
---
##### Examples
> [!h] Example 1
> We have that: 
> 1. $\mathbb{R}^m$ has the smooth structure $\{ \text{id}:\mathbb{R}^m\to \mathbb{R}^m \}$
> 2. Any $m$-dimensional $\mathbb{R}$-vector space $V$ has the smooth structure $\{ \ell:V\to \mathbb{R}^m \}$ where $\ell$ is some linear isomorphism.
---
> [!h] Example 2
> The unit sphere defined as: $$S^m:=\{ p\in \mathbb{R}^{m+1}|\left\| p \right\| =1 \}$$is a compact smooth manifold of dimension $m$.

> [!proof]+
> We give $S^m$ the [[Topological Space|subspace topology]] from $\mathbb{R}^{m+1}$. Therefore, $S^m$ is second-countable Hausdorff. Now, we will construct a smooth atlas for $S^m$. We define:
> 1. $p_{N}:=(0,\dots,0,1)$ the north pole and
> 2. $p_{S}:=(0,\dots,0,-1)$ the south pole.
> 
> Then, we define $U_{N}:=S^m \backslash \{ p_{N} \}$ and $U_{S}:=S^m \backslash\{ p_{S} \}$, which results in $\{ U_{N},U_{S} \}$ being an open cover of $S^m$. We define the charts:
> 1. $x_{N}:U_{N}\to \mathbb{R}^m,x_{N}(u^1,\dots,u^{m+1}):= \frac{1}{1-u^{m+1}}(u^1,\dots,u^{m})$
> 2. $x_{S}:U_{S}\to \mathbb{R}^m,x_{S}(u^1,\dots,u^{m+1}):= \frac{1}{1+u^{m+1}}(u^1,\dots,u^{m})$
>    
> which are the stereographic projection from the north/south pole respectively. Then, the transition maps are given as: $$$$