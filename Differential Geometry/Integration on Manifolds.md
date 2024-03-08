#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]] with an [[Orientable Manifold|oriented atlas]] $\mathcal{A}$. Further, let $\Omega^p_{c}(M)\subseteq \Omega^p(M)$ be the set of smooth $p$-forms with compact support and $(U,\varphi)\in \mathcal{A}$. Then, the ***integral*** is a linear form:
> $$\begin{array}{cccc} {I_{(U,\varphi )}:}&{\Omega^m_{c}(U)}&\to&{\mathbb{R}}\\&{\omega} &\mapsto & {\int_{\mathbb{R}^m}a  \, d\mu} \end{array}{}$$where $a d\pi_{1}\land\dots \land d\pi_{m}=(\varphi ^{-1})^{*}(\omega)\in \Omega^m_{c}(\varphi(U))$ with $a\in C^\infty_{c}(\mathbb{R}^m)$ with $\text{supp }a\subseteq\varphi(U)$. To extend the integral on the whole manifold, let $(U_{i},\varphi_{i},f_{i})_{i\in \mathbb{N}}$ where $(U_{i},\varphi_{i})\in \mathcal{A}$ thats forms a locally finite covering and $(f_{i})_{i\in \mathbb{N}}$ is a [[partition of unity]] subordinate to $(U_{i})_{i\in \mathbb{N}}$. Then, for $\omega\in \Omega_{c}^m(M)$: $$\int_{M}^{} \omega :=\sum_{i\in \mathbb{N}}^{}I_{(U_{i},\varphi_{i})}(f_{i}\omega) $$
---
##### Properties
> [!lemma] Lemma 1
> Let $M$ be a [[smooth manifold]] with an [[Orientable Manifold|oriented atlas]] $\mathcal{A}$. Further, let $(U,\varphi),(V,\psi)$ be charts and $\omega\in \Omega^m_{c}(U\cap V)$. Then, $$I_{(U,\varphi)}(\omega)=I_{(V,\psi)}(\omega)$$

> [!proof]-
> Write $(\varphi ^{-1})^{*}(\omega)=ad\pi_{1}\land\dots \land d\pi_{m}$ and $(\psi ^{-1})^{*}(\omega)=bd\pi_{1}\land\dots \land d\pi_{m}$. Then, we have: $$b(x)=a(\varphi \circ \psi ^{-1}(x))\det d_{x}(\varphi \circ \psi ^{-1})$$Therefore, $$I_{(V,\psi)}(\omega)=\int_{\mathbb{R}^m}b(x) \, d\mu(x)=\int_{\mathbb{R}^m}^{} a(\varphi \circ \psi ^{-1}(x))\det d_{x}(\varphi \circ \psi ^{-1}) \, d\mu(x)=\int_{\mathbb{R}^m}^{} a(y) \, d\mu(y)=I_{(U,\varphi)}(\omega)  $$as $\det d_{x}(\varphi \circ\psi ^{-1})>0$.
---
> [!lemma] Proposition 2
> The integral $\int_{M}^{} :\Omega^m_{c}(M)\to \mathbb{R}$ is well-defined. 

> [!proof]-
> Firstly, $\text{supp }f_{i}\omega \subseteq U_{i}$ and $f_{i}\omega\in \Omega^m_{c}(U_{i})$. Further, as only finitely many $U_{i}$ intersect $\text{supp }\omega$, therefore, the integral is a finite sum.
> 
> Now we show that the integral is independent of the choice of $(U_{i},\varphi_{i},f_{i})_{i}$. If $(V_{j},\psi_{j},g_{j})_{j\in \mathbb{N}}$ is another choice, then $f_{i}\omega=\sum_{j\in \mathbb{N}}^{}g_{j}f_{i}\omega$ and therefore, $$I_{(U_{i},\varphi_{i})}(f_{i}\omega)=\sum_{j\in \mathbb{N}}^{}I_{(U_{i},\varphi_{i})}(g_{j}f_{i}\omega)=\sum_{j\in \mathbb{N}}^{}I_{(V_{j},\psi_{j})}(g_{j}f_{i}\omega)$$as $\text{supp }g_{j}f_{i}\omega \subseteq U_{i}\cap V_{j}$. Consequently, $$\begin{align}\sum_{i\in \mathbb{N}}^{}I_{(U_{i},\varphi_{i})}(f_{i}\omega)=\sum_{i\in \mathbb{N}}^{}\sum_{j\in \mathbb{N}}^{}I_{(V_{j},\psi_{j})}(g_{j}f_{i}\omega)=\sum_{j\in \mathbb{N}}^{}I_{(V_{j},\psi_{j})}\left(\sum_{i\in \mathbb{N}}^{}g_{j}f_{i}\omega\right)=\sum_{j\in \mathbb{N}}^{}I_{(V_{j},\psi_{j})}(g_{j}\omega)\end{align}$$
---
