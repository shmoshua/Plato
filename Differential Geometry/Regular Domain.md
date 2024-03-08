#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. A ***regular domain*** in $M$ is a subset $D\subseteq M$ s.t. 
> 1. $D$ is closed,
> 2. $D^\circ$ is not-empty, and
> 3. for every $p\in \partial D$, there is a chart $(U,\varphi)$ at $p$ s.t. $\varphi(U)=C^m_{\varepsilon}(0)$, $\varphi(p)=0$ and $$\varphi(U\cap D)=\{ x\in C_{\varepsilon}^m(0): x_{m}\geq 0 \}$$
- **Remark**: Given $p\in \partial D$ and $(U,\varphi)\in \mathcal{A}$, $\text{T}_{p}M_{>0}:=\{ v\in \text{T}_{p}M:d_{p}\varphi (v)_{m}>0\}$
- **Remark**: Given $p\in \partial D$, a basis $(f_{1},\dots,f_{m-1})$ of $\text{T}_{p}\partial D$ is positively oriented if for all $v\in \text{T}_{p}M_{>0}$ the basis $(f_{1},\dots,f_{m-1},v)$ of $\text{T}_{p}M$ is positively oriented.
---
##### Properties
> [!lemma] Theorem 1
> Let $M$ be an [[orientable manifold]] where $m\geq 2$ and $D\subseteq M$ a regular domain. Then, 
> 1. $\partial D$ is orientable and
> 2. the orientation of $M$ canonically determines an orientation on $\partial D$.

> [!proof]-
> Let $\mathcal{A}$ be the set of all charts according to the definition of the regular domain. Similar to the proof in [[Orientable Manifold|Proposition 1]], using a volume form $\omega$ on $M$ (which exists), we can turn $\mathcal{A}$ into an oriented atlas. 
> 
> Now, let $p\in\partial D$ and $(U,\varphi),(V,\psi)\in \mathcal{A}$ at $p$. Then, $$(\psi \circ \varphi ^{-1})(\{ x\in\varphi(U\cap V)|x_{m}\geq 0 \})=\{ y\in\psi(U\cap V)|y_{m}\geq 0 \}$$and$$(\psi \circ \varphi ^{-1})(\{ x\in\varphi(U\cap V)|x_{m}= 0 \})=\{ y\in\psi(U\cap V)|y_{m}= 0 \}$$In particular, $d_{0}(\psi \circ\varphi ^{-1})(\mathbb{R}^{m-1}\times \{ 0 \})=\mathbb{R}^{m-1}\times \{ 0 \}$. Writing $\psi \circ\varphi ^{-1}(x)=(F_{1}(x),\dots,F_{m}(x))$ we have: $$d_{0}(\psi \circ \varphi ^{-1})=\begin{bmatrix}\frac{ \partial F_{1} }{ \partial x_{1} } (0)&\dots&\frac{ \partial F_{1} }{ \partial x_{m-1} } (0)&\frac{ \partial F_{1} }{ \partial x_{m} } (0)\\ \vdots&&\vdots&\vdots\\\frac{ \partial F_{m-1} }{ \partial x_{1} } (0)&\dots&\frac{ \partial F_{m-1} }{ \partial x_{m-1} } (0)&\frac{ \partial F_{m-1} }{ \partial x_{m} } (0)\\0&&0&\frac{ \partial F_{m} }{ \partial x_{m} } (0)\end{bmatrix}=\begin{bmatrix}M_{m-1}&*\\0&\frac{ \partial F_{m} }{ \partial x_{m} } (0)\end{bmatrix}$$Since $\mathcal{A}$ is oriented, $\det M_{m-1}\cdot \frac{ \partial F_{m} }{ \partial x_{m} }(0)>0$. From the fact that $$(\psi \circ \varphi ^{-1})(\{ x\in\varphi(U\cap V)|x_{m}> 0 \})=\{ y\in\psi(U\cap V)|y_{m}> 0 \}$$we deduce that $\frac{ \partial F_{m} }{ \partial x_{m} }(0)>0$. Then, $\det M_{m-1}>0$. 
> 
> Now for every $(U,\varphi)\in \mathcal{A}$, define $\tilde{\varphi}:=\varphi|_{U\cap \partial D}$. Since $M_{m-1}=d_{0}(\tilde{\psi}\circ\tilde{\varphi}^{-1})$, we conclude that $\{ (U\cap \partial D,\tilde{\varphi}):(U,\varphi)\in \mathcal{A} \}$ is an oriented atlas of $\partial D$.
---
> [!lemma] Theorem 2 (Stoke)
> Let $M$ be an [[orientable manifold]] with oriented atlas $\mathcal{A}$ and let $D\subseteq M$ be a regular domain. Further, let $\omega\in \Omega^{m-1}(M)$. If $D$ is compact or $\omega$ has compact support then: 
> $$\int_{D}^{}  \, d\omega=\int_{\widetilde{\partial D}}i^{*}\omega $$where $i:\partial D\hookrightarrow M$ the inclusion and $\widetilde{\partial D}$ denotes the boundary of $D$ with the induced orientation if $m$ is even and the opposite of the induced orientation if $m$ is odd.

> [!proof]+
> Let $(U_{i},\varphi_{i})_{i\in I}$ be a countable, locally finite covering of $M$ taken from $\mathcal{A}$ and according to the definition of the regular domain whenever $U_{i}\cap \partial D\neq \varnothing$. Furthermore, let $\{ f_{i} \}_{i\in I}$ be a partition of unity subordinate to $\{ U_{i} \}_{i\in I}$.
> 
> 1. **Case 1: $\omega$ has compact support**:
>    We will first show that for all $j\in I$: $$\int_{D\cap U_{j}}^{} d(f_{j}\omega)=\int_{\widetilde{\partial D\cap U_{j}}}i^{*}(f_{j}\omega) $$
---
##### Examples
> [!h] Example 1
> $D:=\{ x\in \mathbb{R}^m:\|x\|\leq 1 \}$ is a regular domain in $\mathbb{R}^m$.

> [!proof]-
> It is obvious that $D$ is closed and $D^\circ$ is non-empty. Now, for any $p\in \partial D$, 
---
