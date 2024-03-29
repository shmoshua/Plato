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

> [!proof]-
> Let $(U_{i},\varphi_{i})_{i\in I}$ be a countable, locally finite covering of $M$ taken from $\mathcal{A}$ and according to the definition of the regular domain whenever $U_{i}\cap \partial D\neq \varnothing$. Furthermore, let $\{ f_{i} \}_{i\in I}$ be a partition of unity subordinate to $\{ U_{i} \}_{i\in I}$.
> 
> 
>    We will first show that for all $j\in I$: $$\int_{D\cap U_{j}}^{} d(f_{j}\omega)=\int_{\widetilde{\partial D\cap U_{j}}}i^{*}(f_{j}\omega) $$Consider $\varphi_{j}:U_{j}\to C_{\varepsilon}^m(0)$. Then, $$(\varphi_{j}^{-1})^{*}(f_{j}\omega)=\sum_{\ell=1}^{m}g_{\ell}dx_{1}\land\dots \land\widehat{ dx_{\ell}}\land\dots \land dx_{m}$$for some $g_{\ell}:\mathbb{R}^m\to \mathbb{R}$ smooth with compact support as $(\varphi_{j}^{-1})^{*}(f_{j}\omega)\in\Omega^{m-1}(C^m_{\varepsilon}(0))$. Therefore, we have: $$\begin{align}(\varphi_{j}^{-1})^{*}(d(f_{j}\omega))&=d((\varphi _{j}^{-1})^{*}f_{j}\omega)\\&=\sum_{\ell=1}^{m}dg_{\ell}\land dx_{1}\land\dots\widehat{ dx_{\ell}}\land\dots \land dx_{m}\\&=\sum_{\ell=1}^{m}\sum_{s=1}^{m}\frac{ \partial g_{\ell} }{ \partial x_{s} } dx_{s}\land dx_{1}\land\dots \land\widehat{ dx_{\ell}}\land\dots \land dx_{m}\\&=\sum_{\ell=1}^{m}\frac{ \partial g_{\ell} }{ \partial x_{\ell} } dx_{\ell}\land dx_{1}\land\dots \land\widehat{ dx_{\ell}}\land\dots \land dx_{m}\\&=\sum_{\ell=1}^{m}(-1)^{\ell-1}\frac{ \partial g_{\ell} }{ \partial x_{\ell} } dx_{1}\land\dots \land dx_{m}\end{align}$$Therefore, $$\begin{align}\int_{D\cap U_{j}}   d(f_{j}\omega)&= \int_{\varphi(D\cap U_{j})} \sum_{\ell=1}^{m}(-1)^{\ell-1}\frac{ \partial g_{\ell} }{ \partial x_{\ell} } \, dx_{1}\dots dx_{m}\\&= \left( \int_{x_{m}\geq 0}^{}  \, dx_{m} \right)\cdot  \int_{\mathbb{R}^{m-1} }\sum_{\ell=1}^{m}(-1)^{\ell-1}\frac{ \partial g_{\ell} }{ \partial x_{\ell} } \, dx_{1}\dots dx_{m-1}\end{align} $$where if $\ell=m$: $$(-1)^{m-1}\underbrace{ \int_{x_{m}\geq 0}\frac{ \partial g_{m} }{ \partial x_{m} } dx_{m} }_{ =-g_{m}(x_{1},\dots,x_{m-1},0) }\int_{\mathbb{R}^{m-1}}^{}  \, dx_{1}\dots dx_{{m-1}}=(-1)^m \int_{\mathbb{R}^{m-1}}^{} g_{m}(x_{1},\dots,x_{m-1},0) \, dx_{1}\dots dx_{m-1}   $$and if $\ell\neq m$:
>    $$\begin{align}&\left( \int_{x_{m}\geq 0}^{} dx_{m} \right)\int_{\mathbb{R}^{m-1}}(-1)^{\ell-1}\frac{ \partial g_{\ell} }{ \partial x_{\ell} } dx_{1}\dots dx_{m-1}\\&=\left( \int_{x_{m}\geq 0}^{} dx_{m} \right)\underbrace{ \left( \int_{\mathbb{R}}^{} \frac{ \partial g_{\ell} }{ \partial x_{\ell} }  \, dx_{\ell}  \right) }_{ =0 } \int_{\mathbb{R}^{m-2}}(-1)^{\ell-1} dx_{1}\dots \widehat{dx_{\ell}}\dots dx_{m-1}\\&=0\end{align}$$Overall, we have: $$\int_{D\cap U_{j}}d(f_{j}\omega) =(-1)^m \int_{\mathbb{R}^{m-1}}^{} g_{m}(x_{1},\dots,x_{m-1},0) \, dx_{1}\dots dx_{m-1}    $$Now let us compute $\int_{\widetilde{\partial D\cap U_{j}}}i^{*}(f_{j}\omega)$. Consider: $$\begin{CD}U_{j}@>\varphi_{j}>>C^m_{\varepsilon}(0)\\ @AiAA&@AAIA\\\partial D\cap U_{j}@>p_{m}\circ \varphi_{j}>>C_{\varepsilon}^{m-1}(0)\end{CD}$$where:
>    - $p_{m}(x_{1},\dots,x_{m}):=(x_{1},\dots,x_{m-1})$ and
>    - $I(x_{1},\dots,x_{m-1}):=(x_{1},\dots,x_{m-1},0)$
>   
> Then, $$\begin{align}((p_{m}\circ \varphi_{j})^{-1})^{*}(i^{*}(f_{j}\omega))&=I^{*}(\varphi_{j}^{-1})^{*}(f_{j}\omega)\\&=I^{*}\left( \sum_{\ell=1}^{m}g_{\ell}dx_{1}\land\dots \land\widehat{dx_{\ell}}\land\dots \land dx_{m}\right)\\&=g_{m}(\dots,0)dx_{1}\land\dots  \land dx_{m-1}\end{align}$$
> 	 
> Therefore, $$\int_{\widetilde{\partial D\cap U_{j}}}i^{*}(f_{j}\omega)=(-1)^m\int_{\mathbb{R}^{m-1}}^{} g_{m}(x_{1},\dots,x_{m-1},0) \, dx_{1}\dots dx_{m-1}  $$
---
> [!lemma] Corollary 3
> Let $M$ be an orientable manifold with $m\geq 2$ and $D\subseteq M$ a compact regular domain. Further, let $\Omega \supseteq D$ be open. Then, there is no smooth map $f:\Omega\to \partial D$ s.t. $f|_{\partial D}=\text{id}$.

> [!proof]-
> Assume that we have such a function $f$. Pick a volume form $\omega\in \Omega^{m-1}(\partial D)$ on $\partial D$. Then, $\int_{\partial D}^{} \omega \neq 0$. On the other hand, $$d^\Omega(f^{*}\omega)=f^{*}(d\omega)=0$$As $d\omega$ is a $m$-form on $\partial D$. This leads to a contradiction as: $$0=\int_{D}^{} d(f^{*}\omega) \, dx =\int_{\widetilde{\partial D}}(f\circ i)^{*}\omega=\int_{\widetilde{\partial D}}\omega\neq 0 $$
---
> [!lemma] Corollary 4 (Brouwer's Fixed Point Theorem)
> Let $m\geq 2$ and $B:=B_{\leq 1}(0)\subseteq \mathbb{R}^m$. Then, any continuous map $f:B\to B$ has a fixed point.

> [!proof]-
> We first show the statement in smooth setting. Let $\delta>0$ and a smooth map $G:B_{<1+\delta}(0)\to B$. Assume that $G(x)\neq x$ for all $x\in B_{<1+\delta}(0)$ Then, consider the ray $G(x)+t(x-G(x))$ for $t\geq0$ and denote the intersection of the ray with $S^{m-1}$ as $f(x)$ for each $x\in B_{<1+\delta}(0)$. Then, $f$ is smooth and $f|_{\partial B}=\text{id}$. This is a contradiction to Corollary 3.
> 
> Assume that now we have a continuous function $F:B\to B$. If $F(x)\neq x$ for all $x\in B$, then there is $\varepsilon>0$ s.t. $0<2\varepsilon<\min_{x\in B}\left\| F(x)-x \right\|$. Further, by Weierstrass approximation, there is a polynomial $P:\mathbb{R}^m\to \mathbb{R}^m$ s.t. $\left\| F(x)-P(x) \right\|<\varepsilon$ for all $x\in B$. As $\|F(x)\|\leq 1$, we have that $\max_{x\in B}\|P(x)\|<1+\varepsilon$. 
> 
> Now define $G:\mathbb{R}^m\to \mathbb{R}^m, G(x)=P(x) / (1+\varepsilon)$. Then, $\max_{x\in B}\|G(x)\|<1$. Hence there is $\delta>0$ s.t. $G(B_{<1+\delta}(0))\subseteq B$. 
> - If $x\in B_{<1+\delta}(0 ) \backslash B$, then as $G(x)\in B$, $G(x)\neq x$.
> - If $x\in B$, then: $$\left\| G(x)-F(x) \right\| \leq \left\| G(x)-P(x) \right\| +\left\| P(x)-F(x) \right\| <2\varepsilon$$Therefore, $$\left\| G(x)-x \right\| > \left\| F(x)-x \right\|-2\varepsilon>0 $$
>   
> Therefore, $G(x)\neq x$ and this is a contradiction to part 1. 
---
##### Examples
> [!h] Example 1
> $D:=\{ x\in \mathbb{R}^m:\|x\|\leq 1 \}$ is a regular domain in $\mathbb{R}^m$.

> [!proof]-
> It is obvious that $D$ is closed and $D^\circ$ is non-empty. Now, for any $p\in \partial D$, 
---
