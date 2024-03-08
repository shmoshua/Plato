#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. 
> 1. An [[atlas]] $\mathcal{A}$ on $M$ is ***oriented*** if for any two overlapping charts $(U_{\alpha},\varphi_{\alpha}),(U_{\beta},\varphi_{\beta})$ in $\mathcal{A}$, the coordinate transformation $\theta_{\beta\alpha}:\varphi_{\alpha}(U_{\alpha}\cap U_{\beta})\to\varphi_{\beta}(U_{\alpha}\cap U_{\beta})$ has the property that: $$\det d_{x}\theta_{\beta\alpha}>0,\quad \forall x\in\varphi_{\alpha}(U_{\alpha}\cap U_{\beta})$$
> 2. $M$ is ***orientable*** if it admits an oriented atlas.
- **Remark**: In an orientable manifold, $d_{p}\varphi:\text{T}_{p}M\to \mathbb{R}^m$ is orientation-preserving.
---
##### Properties
> [!lemma] Proposition 1
> Let $M$ be a [[smooth manifold]]. The following are equivalent:
> 1. $M$ is orientable.
> 2. $M$ admits a [[volume form]].

> [!proof]+
> Suppose that $M$ admits a volume form $\omega\in \Omega^m(M)$. Let $\mathcal{A}$ be an atlas on $M$. We will modify $\mathcal{A}$ into a new oriented atlas $\mathcal{A'}$. First of all, wlog we may assume that every chart domain $U_{\alpha}$ of $\mathcal{A}$ is connected.
> 
> GIven $(U,\varphi)\in \mathcal{A}$, consider 
> $$(\varphi ^{-1})^{*}(\omega|_{U})=ad\pi_{1}\land\dots \land d\pi_{m}$$
> where $a:\varphi(U)\to \mathbb{R}$ is a nowhere vanishing smooth function. By connectedness of $U$, $\text{sgn}\circ a$ is constant. 
> 1. If it is positive, let $(U,\varphi)\in \mathcal{A'}$. 
> 2. If it is negative, let $(U,s_{1}\circ\varphi)\in \mathcal{A'}$ where $s_{1}:\mathbb{R}^m\to \mathbb{R}^m$ with: $$s(x_{1},\dots,x_{m})=(-x_{1},x_{2},\dots,x_{m})$$
>Then, for $\varphi':=s_{1}\circ\varphi$: $$\begin{align}(\varphi ^{-1})^{*}(\omega)&=(\varphi ^{-1}s_{1}^{-1})^{*}(\omega)\\&=(s_{1}^{-1})^{*}(\varphi ^{-1})^{*}(\omega)\\&=(s_{1}^{-1})^{*}(ad\pi_{1}\land\dots \land d\pi_{m})\\&=(a\circ s_{1}^{-1} )(s_{1}^{-1})^{*}(d\pi_{1}\land\dots \land d\pi_{m})\\&=-a(-y_{1},\dots,y_{m})dy_{1}\land\dots \land dy_{m}\\&=bdy_{1}\land\dots \land dy_{m}\end{align}$$on $s_{1}(\varphi(U))$ where $\text{sgn}\circ b$ is positive. 
>
>Now we claim that $\mathcal{A}'$ is oriented. Let $(U,\varphi),(V,\psi)\in \mathcal{A'}$ s.t. $U\cap V\neq \varnothing$. Then, 
>- $(\varphi ^{-1})^{*}(\omega|_{U\cap V})=ad\pi_{1}\land\dots \land d\pi_{m}$ and 
>- $(\psi ^{-1})^{*}(\omega|_{U\cap V})=bd\pi_{1}\land\dots \land d\pi_{m}$
>
>where $a,b$ are smooth strictly positive functions on $\varphi(U\cap V)$ and $\psi(U\cap V)$ respectively. Then, we have: $$\begin{align}(\varphi \circ \psi ^{-1})^{*}(a d\pi_{1}\land\dots \land d\pi_{m})&=(\varphi \circ \psi ^{-1})^{*}(\varphi^{-1})^{*}(\omega|_{U\cap V})\\&=(\psi ^{-1})^{*}(\omega|_{U\cap V})\\&=bd\pi_{1}\land\dots \land d\pi_{m}\end{align}$$Therefore, $$\begin{align}&(\varphi \circ \psi ^{-1})^{*}(ad\pi_{1}\land\dots \land d\pi _{m})_{p}(e_{1},\dots,e_{m})\\&=(a\circ \varphi \circ \psi ^{-1})(p)(\varphi \circ \psi ^{-1})^{*}(d\pi_{1}\land\dots \land d\pi _{m})_{p}(e_{1},\dots,e_{m})\\&=(a\circ \varphi \circ \psi ^{-1})(p)(d\pi_{1}\land\dots \land d\pi _{m})_{\varphi \circ \psi ^{-1}(p)}(d_{p}(\varphi \circ \psi ^{-1})e_{1},\dots,d_{p}(\varphi \circ \psi ^{-1})e_{m})\\&=(a\circ \varphi \circ \psi ^{-1})(p)\det [(d\pi_{i})_{\varphi \circ \psi ^{-1}(p)}(d_{p}(\varphi \circ \psi ^{-1})e_{j})]_{ij}\\&=(a\circ \varphi \circ \psi ^{-1})(p)\det [\pi_{i}(d_{p}(\varphi \circ \psi ^{-1})e_{j})]_{ij}\\&=(a\circ \varphi \circ \psi ^{-1})(p)\det d_{p}(\varphi \circ \psi ^{-1})\end{align}$$In follows that $b(p)=(a\circ \varphi \circ \psi ^{-1})(p)\det d_{p}(\varphi \circ \psi ^{-1})$ for all $p\in \psi(U\cap V)$. However, as $a,b$ are positive, $\det d_{p}(\varphi \circ\psi ^{-1})$ is positive for all $p$. Therefore, $\mathcal{A}'$ is oriented.
>
>
> 