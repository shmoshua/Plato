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
> Let $\mathcal{A}$ be a maximal $C^k$-atlas and $(U,\varphi)\in \mathcal{A}$. Then, for any open set $V\subseteq U$, $(V,\varphi|_{V})\in \mathcal{A}$.

> [!proof]-
> We show that $(V,\varphi|_{V})$ is compatible with every chart in $\mathcal{A}$. Clearly, 
> 1. $\varphi \circ(\varphi|_{V})^{-1}:\varphi(V)\to \varphi(V)$ is the identity.
> 2. $\varphi_{\alpha}\circ(\varphi|_{V\cap U_{\alpha}})^{-1}:\varphi(V\cap U_{\alpha})\to\varphi_{\alpha}(V \cap U_{\alpha})$ is in $C^k$.
---
> [!lemma] Lemma 2
> Let $M$ be a [[topological manifold]]. Every $C^k$-atlas $\mathcal{A}$ on $M$ is contained in a unique maximal atlas.

> [!proof]-
> Let $\mathcal{M}\supseteq\mathcal{A}$ be the maximal atlas. Then, by definition, it contains: $$\mathcal{S}:=\{ (U,\varphi):(U,\varphi)\text{ is }C^k\text{-compatible with every chart in }\mathcal{A} \}\supseteq\mathcal{A}$$Conversely, if the above set is an atlas it is maximal among those containing $\mathcal{A}$ and necessarily unique with this property since any other maximal atlas containing $\mathcal{A}$ consists of charts which are (in particular) compatible with all the charts of $\mathcal{A}$ and is thus contained in $\mathcal{S}$. By maximality it then equals $\mathcal{S}$. 
> 
> Therefore it only remains to show that $\mathcal{S}$ is an atlas. Since $\mathcal{A}\subseteq \mathcal{S}$ and $\mathcal{A}$ is an atlas of $M$ we have $$M=\bigcup_{(U,\varphi)\in \mathcal{S}}^{}U$$ As to coordinate transformations, let $(U_{\alpha},\varphi_{\alpha}),(U_{\beta},\varphi_{\beta})\in \mathcal{S}$. We show that the coordinate transformation $\theta_{\beta\alpha}:\varphi_{\alpha}(U_{\alpha}\cap U_{\beta})\to\varphi_{\beta}(U_{\alpha}\cap U_{\beta})$ is $C^k$ on a neighbourhood of every point $\varphi_{\alpha}(x)$ where $x\in U_{\alpha}\cap U_{\beta}$. 
> 
> Since $\mathcal{A}$ is an atlas there is a chart $(V,\psi)\in A$ with $x\in V$. Since further both $(U_{\alpha},\varphi_{\alpha}),(U_{\beta},\varphi_{\beta})$ are compatible with $(V,\psi)$ the coordinate transformations $\theta_{\beta \psi}$ and $\theta _{\psi\alpha}$ are $C^k$ and hence so is $\theta_{\beta\alpha}=\theta_{\beta \psi}\circ\theta_{\psi\alpha}$ on $U_{\alpha}\cap U_{\beta}\cap V$ which contains $x$.
---
> [!lemma] Lemma 3
> Let $M$ be a [[smooth manifold]] with maximal atlas $\mathcal{A}$. If $F:M\to M$ is a [[homeomorphism]], then $$\mathcal{A}':=\{ (F(U),\varphi \circ F^{-1})|(U,\varphi)\in \mathcal{A} \}$$is a maximal smooth atlas as well.

> [!proof]+
> Let $(F(U_{\alpha}),\varphi_{\alpha}\circ F^{-1}),(F(U_{\beta}),\varphi_{\beta}\circ F^{-1})\in \mathcal{A'}$. Then, $$\theta_{\beta\alpha}'=\varphi_{\beta}\circ F^{-1}\circ F\circ \varphi_{\alpha}^{-1}=\varphi_{\beta}\circ\varphi_{\alpha}^{-1} $$on $\varphi_{\alpha}(F^{-1}(F(U_{\alpha})\cap F(U_{\beta})))$ which is an open subset of $\varphi+\a$
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


