#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[topological manifold]]. A collection of [[Topological Manifold|charts]] $\mathcal{A}:=\{ (U_{\alpha},\varphi_{\alpha}) \}_{\alpha\in A}$ is a:
> 1. ***$C^0$-atlas*** if $\bigcup_{\alpha\in A}^{}U_{\alpha}=M$.
> 2. **$C^k$-atlas** if it is a $C^0$-atlas and all [[Topological Manifold|coordinate transformations]] between charts are $C^k$.
> 3. **$C^\infty$-atlas/smooth atlas** if $\mathcal{A}$ is a $C^k$-atlas for all $k\geq 0$.
- **Remark**: In a $C^k$-atlas, all coordinate transformations are [[Diffeomorphism|$C^k$-diffeomorphisms]].
- **Related definition**: A $C^k$-atlas $\mathcal{A}$ is ***maximal***, if any chart $(U,\varphi)$ on $M$ that is [[Topological Manifold|compatible]] with every chart in $\mathcal{A}$ is in $\mathcal{A}$.
---
##### Properties
> [!lemma] Lemma 1
> Let $M$ be a smooth manifold with maximal 
---
##### Examples
> [!h] Example 1
> For $M\subseteq \mathbb{R}^n$ an open subset, $\mathcal{A}:=\{ (M,\text{id}) \}$ is a smooth atlas.
---
> [!h] Example 2
> Let $M\subseteq S^n\subseteq \mathbb{R}^{n+1}$ with the subspace topology. If $n\geq 1$, then the atlas needs at least two charts as $M$ is compact. As: $$S^n:=\left\{  x=(x_{1},\dots,x_{n+1})\in \mathbb{R}^{n+1}:\sum_{i=1}^{n+1}x_{i}^{2}=1  \right\}$$we can define the north and south pole 
> 1. $p_{N}:=(0,\dots,0,1)$ and
> 2. $p_{S}:=(0,\dots,0,-1)$ and
>
>Then, for $U_{N}:= S^n \backslash\{ p_{N} \},U_{S}:= S^n \backslash\{ p_{S} \}$, we have: $$\begin{array}{cccc} {\varphi_{N,S}:}&{U_{N,S}}&\to&{\mathbb{R}^n}\\&{x} &\mapsto & {\frac{(x_{1},\dots,x_{n})}{1\mp x_{n+1}}} \end{array}$$given by the stereographic projection form an atlas $\mathcal{A}:=\{ (U_{N},\varphi_{N}), (U_{S},\varphi_{S}) \}$. Then, the coordinate transformation is: $$\begin{array}{cccc} {\theta_{SN}:}&{\mathbb{R}^n \backslash\{ 0 \}}&\to&{\mathbb{R}^n \backslash\{ 0 \}}\\&{y} &\mapsto & {y / \left\| y \right\| ^{2}} \end{array}{}$$which exchanges the inside and outside of the unit sphere.
---


