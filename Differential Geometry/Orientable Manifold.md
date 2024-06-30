#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. 
> 1. An ***orientation*** of $M$ is a map $o:M\to \text{O}M$ with $o(p)\in \text{O}_{p}M$ for all $p\in M$, s.t. for all $p\in M$ there exists an open $U\ni p$ with a [[Local Frame|smooth local frame]] $V_{1},\dots,V_{m}$ with: $$o(p)=[(V_{1}(p),\dots,V_{m}(p))]_{\sim},\quad \forall p\in U$$
>    where $\text{O}M$ is the [[orientable double cover]].
> 1. An [[atlas]] $\mathcal{A}$ on $M$ is ***oriented*** if for any two overlapping charts $(U_{\alpha},\varphi_{\alpha}),(U_{\beta},\varphi_{\beta})$ in $\mathcal{A}$, the coordinate transformation $\theta_{\beta\alpha}:\varphi_{\alpha}(U_{\alpha}\cap U_{\beta})\to\varphi_{\beta}(U_{\alpha}\cap U_{\beta})$ has the property that: $$\det d_{x}\theta_{\beta\alpha}>0,\quad \forall x\in\varphi_{\alpha}(U_{\alpha}\cap U_{\beta})$$
> 2. $M$ is ***orientable*** if it admits an oriented atlas.
- **Remark**: In an orientable manifold, $d_{p}\varphi:\text{T}_{p}M\to \mathbb{R}^m$ is orientation-preserving.
---
##### Properties
> [!lemma] Proposition 1
> Let $M$ be a [[smooth manifold]]. The following are equivalent:
> 1. $M$ is orientable.
> 2. $M$ admits a [[volume form]].

> [!proof]-
> Suppose that $M$ admits a volume form $\omega\in \Omega^m(M)$. Let $\mathcal{A}$ be an atlas on $M$. We will modify $\mathcal{A}$ into a new oriented atlas $\mathcal{A'}$. First of all, wlog we may assume that every chart domain $U_{\alpha}$ of $\mathcal{A}$ is connected.
> 
> Given $(U,\varphi)\in \mathcal{A}$, consider 
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
>Conversely, supposed that $\mathcal{A}$ is an oriented atlas on $M$. Let $(U_{i},\varphi_{i})_{i}$ be a locally finite refinement of $\mathcal{A}$ and let $\{ f_{i} \}_{i}$ be the [[partition of unity]] subordinate to it. For every $i\in I$, define $\omega_{i}\in \Omega^m(M)$ by: $$(\omega_{i})_{p}:=\begin{cases}f_{i}(p) (dx_{1}\land\dots \land dx_{m})_{p}&p\in U_{i}\\0&p\notin U_{i}\end{cases}$$Now, define $\omega:=\sum_{i\in I}^{}\omega_{i}\in \Omega^m(M)$. We will show that $\omega$ is a volume form. Given $p\in M$, let $k\in I$ s.t. $p\in U_{k}$. Then, $$\begin{align}\omega_{p}&=\sum_{p\in U_{i}\cap U_{k}}^{}(\omega_{i})_{p}\\&=\sum_{p\in U_{i}\cap U_{k}}^{}f_{i}(p)(dx_{1}\land\dots \land dx_{m})_{p}\\&=\sum_{p\in U_{i}\cap U_{k}}^{}f_{i}(p)(\varphi_{i})^{*}(d\pi_{1}\land\dots \land d\pi_{m})_{p}\\&=\sum_{p\in U_{i}\cap U_{k}}^{}f_{i}(p)(\varphi_{k})^{*}(\varphi_{i} \varphi_{k}^{-1})^{*}(d\pi_{1}\land\dots \land d\pi_{m})_{p}\\&=\sum_{p\in U_{i}\cap U_{k}}^{}f_{i}(p)(\varphi_{k})^{*}(\det d_{p}(\varphi_{i}\varphi_{k}^{-1})(d\pi_{1}\land\dots \land d\pi_{m})_{p})\\&=\sum_{p\in U_{i}\cap U_{k}}^{}f_{i}(p)\det d_{\varphi_{k}(p)}(\varphi_{i}\varphi_{k}^{-1})(\varphi_{k}^{*}(d\pi_{1}\land\dots \land d\pi_{m}))_{p}\end{align}$$If $\omega_{p}=0$, then $$\sum_{p\in U_{i}\cap U_{k}}^{}f_{i}(p)\det d_{\varphi_{k}(p)}(\varphi_{i}\varphi_{k}^{-1})\geq \min_{{p\in U_{i}\cap U_{k}}}\det d_{\varphi_{k}(p)}(\varphi_{i}\varphi_{k}^{-1})\cdot \sum_{p\in U_{i}\cap U_{k}}^{}f_{i}(p)=\min_{{p\in U_{i}\cap U_{k}}}\det d_{\varphi_{k}(p)}(\varphi_{i}\varphi_{k}^{-1})=0$$which is a contradiction as $\mathcal{A}$ is oriented.
---
