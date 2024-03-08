#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]] with an [[Orientable Manifold|oriented atlas]] $\mathcal{A}$. Further let $\Omega^p_{c}(M)\subseteq \Omega^p(M)$ be the set of smooth $p$-forms with compact support and $(U,\varphi)\in \mathcal{A}$. Then, the ***integration*** is a linear form:
> $$\begin{array}{cccc} {I_{(U,\varphi )}:}&{\Omega^m_{c}(U)}&\to&{\mathbb{R}}\\&{\omega} &\mapsto & {\int_{\mathbb{R}^m}a  \, d\mu} \end{array}{}$$where $a d\pi_{1}\land\dots \land d\pi_{m}=(\varphi ^{-1})^{*}(\omega)\in \Omega^m_{c}(\varphi(U))$ with $a\in C^\infty_{c}(\mathbb{R}^m)$ with $\text{supp }a\subseteq\varphi(U)$. 
---
##### Properties
> [!lemma] Lemma 1
> Let $M$ be a [[smooth manifold]] with an [[Orientable Manifold|oriented atlas]] $\mathcal{A}$. Further, let $(U,\varphi),(V,\psi)$ be charts and $\omega\in \Omega^m_{c}(U\cap V)$. Then, $$I_{(U,\varphi)}(\omega)=I_{(V,\psi)}(\omega)$$

> [!proof]-
> Write $(\varphi ^{-1})^{*}(\omega)=ad\pi_{1}\land\dots \land d\pi_{m}$ and $(\psi ^{-1})^{*}(\omega)=bd\pi_{1}\land\dots \land d\pi_{m}$. Then, we have: $$b(x)=a(\varphi \circ \psi ^{-1}(x))\det d_{x}(\varphi \circ \psi ^{-1})$$Therefore, $$I_{(V,\psi)}(\omega)=\int_{\mathbb{R}^m}b(x) \, d\mu(x)=\int_{\mathbb{R}^m}^{} a(\varphi \circ \psi ^{-1}(x))\det d_{x}(\varphi \circ \psi ^{-1}) \, d\mu(x)=\int_{\mathbb{R}^m}^{} a(y) \, d\mu(y)=I_{(U,\varphi)}(\omega)  $$as $\det d_{x}(\varphi \circ\psi ^{-1})>0$.
