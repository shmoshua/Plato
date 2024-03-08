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

> [!proof]-
> Let $(F(U_{\alpha}),\varphi_{\alpha}\circ F^{-1}),(F(U_{\beta}),\varphi_{\beta}\circ F^{-1})\in \mathcal{A'}$. Then, $$\theta_{\beta\alpha}'=\varphi_{\beta}\circ F^{-1}\circ F\circ \varphi_{\alpha}^{-1}=\varphi_{\beta}\circ\varphi_{\alpha}^{-1} $$on $\varphi_{\alpha}(F^{-1}(F(U_{\alpha})\cap F(U_{\beta})))$ which is an open subset of $\varphi_{\alpha}(U_{\alpha}\cap U_{\beta})$. Therefore,  $\theta_{\beta\alpha}$ is smooth.
> 
> The maximality of $\mathcal{A}'$ then follows from the maximality of $\mathcal{A}$.
---
> [!lemma] Lemma 4
> Let $M$ be a [[topological manifold]] with a maximal atlas. Further, let $\{ V_{\alpha} \}_{\alpha\in A}$ be an open cover of $M$. Then, there is at most countable family of charts $(U_{i},\varphi_{i})_{i}$ where:
> 1. $\{ U_{i} \}_{i}$ is a locally finite cover of $M$ refining $\{ V_{\alpha} \}_{\alpha}$.
> 2. $\varphi_{i}(U_{i})\subseteq C_{3\varepsilon}^m(0)$
> 3. $\bigcup_{i}^{}V_{i}=M$ where $V_{i}:=\varphi_{i}^{-1}(C_{\varepsilon}^m(0))$
> 
> If further $M$ is a [[smooth manifold]] with atlas the then the charts can be chosen to be [[Diffeomorphism|diffeomorphisms]].

> [!proof]-
> We may assume that $M$ is connected and non-compact. 
> 
> As $M$ is locally compact Hausdorff, for a basis $\mathcal{B}=\{ B_{i}: i\in \mathbb{N} \}$, every $B_{i}$ is a union of open sets with compact closure. However, any open set with compact closure lies in $\mathcal{B}_{c}:=\{ B\in \mathcal{B}:\overline{B}\text{ is compact} \}$. Therefore, there exists a countable basis of open sets $\{ P_{i}: i\in \mathbb{N} \}$ s.t. $\overline{P}_{i}$ is compact for every $i\in \mathbb{N}$. 
> 
> Let $K_{1}:=\overline{P_{1}}$. By compactness and the fact that $\{ P_{i} \}_{i}$ is a basis, there exists $j\in \mathbb{N}$ s.t. $$\overline{P_{1}}=K_{1}\subseteq P_{1}\cup\dots \cup P_{j}$$where $j\geq 2$ as $M$ is connected and non-compact. Let $r_{1}:=\min\{ j:\overline{P_{1}}\subseteq P_{1}\cup\dots \cup P_{j} \}\geq 2$ and set $$K_{2}:=\overline{P_{1}}\cup\dots \cup \overline{P}_{r_{1}}$$Iterate this process s.t.
> 1. $K_{j}:=\overline{P}_{1}\cup\dots \cup \overline{P}_{r_{j-1}}$ and 
> 2. $K_{j-1}\subseteq P_{1}\cup\dots \cup P_{r_{j-1}}$ and $K_{j-1}\nsubseteq P_{1}\cup\dots \cup P_{\ell}$ for any $\ell<r_{j-1}$.
> 
> Now, observe that $K_{j-1}\subseteq P_{1}\cup\dots \cup P_{j-1}\subseteq K_{j}^\circ$. Therefore, $K_{i+2}^\circ \backslash K_{i-1}$ is an open set and $K_{i+1} \backslash K_{i}^\circ$ compact s.t. $K_{i+1} \backslash K_{i}^\circ\subseteq K_{i+2}^\circ \backslash K_{i-1}$.
> 
> Consider $K_{i+2}^\circ \backslash K_{i-1}\cap V_{\alpha}$. For every $p\in K_{i+2}^\circ \backslash K_{i-1}\cap V_{\alpha}$, let $(U^i_{p},\varphi^i_{p})$ be a chart at $p$ contained in $K_{i+2}^\circ \backslash K_{i-1}\cap V_{\alpha}$ and s.t. $\varphi^i_{p}(U^i_{p})\subseteq C_{3\varepsilon}^m(0)$. Further define $V^i_{p}:=(\varphi^i_{p})^{-1}(C_{\varepsilon}^m(0))$. 
> 
> For fixed $i\in \mathbb{N}$, consider the set of all charts $(U^i_{p},\varphi^i_{p})$ obtained this way by varying $\alpha$. Since $V_{\alpha}$ covers $M$, $\{ V^i_{p} \}_{p}$ is an open cover of $K^\circ_{i+2}  \backslash K_{i-1}$. By compactness we therefore have a finite set $S_{i}$ s.t. $$K_{i+1} \backslash K_{i}^\circ\subseteq K^\circ_{i+2}  \backslash K_{i-1}\subseteq\bigcup_{p\in S_{i}}^{}V^i_{p}$$Now consider the collection $\mathcal{A}:=\{ (U^i_{p},\varphi^i_{p}): i\in \mathbb{N}, p\in S_{i} \}$.
> 1. $\mathcal{A}$ is a countable refinement of $\{ V_{\alpha} \}_{\alpha}$ by construction.
> 2. $\bigcup_{i,p}^{}V^i_{p}=M$ by construction.
> 3. Let $p\in M$ and $i\in \mathbb{N}$ s.t. $p\in K^\circ_{i-1}$. Then, $K^\circ_{j+2} \backslash K_{j-1}\cap K ^\circ_{i-1}=\varnothing$ for all $j\geq i$. Therefore, only finitely many domains of $\{ U^i_{p} \}$ intersects $K_{i-1}^\circ$.
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


