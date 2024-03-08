#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. A ***regular domain*** in $M$ is a subset $D\subseteq M$ s.t. 
> 1. $D$ is closed,
> 2. $D^\circ$ is not-empty, and
> 3. for every $p\in \partial D$, there is a chart $(U,\varphi)$ at $p$ s.t. $\varphi(U)=C^m_{\varepsilon}(0)$, $\varphi(p)=0$ and $$\varphi(U\cap D)=\{ x\in C_{\varepsilon}^m(0): x_{m}\geq 0 \}$$
---
##### Properties
> [!lemma] Theorem 1
> Let $M$ be an [[orientable manifold]] where $m\geq 2$ and $D\subseteq M$ a regular domain. Then, 
> 1. $\partial D$ is orientable and
> 2. the orientation of $M$ canonically determines an orientation on $\partial D$.

> [!proof]+
> Let $\mathcal{A}$ be the set of all charts according to the definition of the regular domain. Similar to the proof in [[Orientable Manifold|Proposition 1]], using a volume form $\omega$ on $M$ (which exists), we can turn $\mathcal{A}$ into an oriented atlas. 
> 
> Now, let $p\in\partial D$ and $(U,\varphi),(V,\psi)\in \mathcal{A}$ at $p$. Then, $$(\psi \circ \varphi ^{-1})(\{ x\in\varphi(U\cap V)|x_{m}\geq 0 \})=\{ y\in\psi(U\cap V)|y_{m}\geq 0 \}$$and$$(\psi \circ \varphi ^{-1})(\{ x\in\varphi(U\cap V)|x_{m}= 0 \})=\{ y\in\psi(U\cap V)|y_{m}= 0 \}$$In particular, $d_{0}(\psi \circ\varphi ^{-1})(\mathbb{R}^{m-1}\times \{ 0 \})=\mathbb{R}^{m-1}\times \{ 0 \}$. Writing $\psi \circ\varphi ^{-1}(x)=(F_{1}(x),\dots,F_{m}(x))$ we have: $$d_{0}(\psi \circ \varphi ^{-1})=\begin{bmatrix}\frac{ \partial F_{1} }{ \partial x_{1} } (0)&\dots&\frac{ \partial F_{1} }{ \partial x_{m-1} } (0)&\frac{ \partial F_{1} }{ \partial x_{m} } (0)\\ \vdots&&\vdots&\vdots\\\frac{ \partial F_{m-1} }{ \partial x_{1} } (0)&\dots&\frac{ \partial F_{m-1} }{ \partial x_{m-1} } (0)&\frac{ \partial F_{m-1} }{ \partial x_{m} } (0)\\0&&0&\frac{ \partial F_{m} }{ \partial x_{m} } (0)\end{bmatrix}=\begin{bmatrix}M_{m-1}&*\\0&\frac{ \partial F_{m} }{ \partial x_{m} } (0)\end{bmatrix}$$Since $\mathcal{A}$ is oriented, $\det M_{m-1}\cdot \frac{ \partial F_{m} }{ \partial x_{m} }(0)>0$. From the fact that $$(\psi \circ \varphi ^{-1})(\{ x\in\varphi(U\cap V)|x_{m}> 0 \})=\{ y\in\psi(U\cap V)|y_{m}> 0 \}$$we deduce that $\frac{ \partial F_{m} }{ \partial x_{m} }(0)>0$. Then, $\det M_{m-1}>0$. 
> 
> Now for every $(U,\varphi)\in \mathcal{A}$, define $\tilde{\varphi}:=\varphi|_{U\cap}$
---
##### Examples
> [!h] Example 1
> $D:=\{ x\in \mathbb{R}^m:\|x\|\leq 1 \}$ is a regular domain in $\mathbb{R}^m$.

> [!proof]-
> It is obvious that $D$ is closed and $D^\circ$ is non-empty. Now, for any $p\in \partial D$, 
---
