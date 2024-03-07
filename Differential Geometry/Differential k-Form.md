#Definition #DifferentialGeometry 
> [!definition]
> Let $M$ be a [[smooth manifold]]. A ***differential $k$-form on $M$*** is a map $\omega:M\to \Lambda^k(M)$ s.t. $\pi \circ\omega=\text{id}_{M}$ where: $$\Lambda^k(M):=\bigcup_{x\in M}^{}\{ x \}\times\Lambda^k(\text{T}_{x}^{*}M)$$with $\Lambda^k(\text{T}_{x}^{*}M)$ as the vector space of [[Exterior Algebra|alternating multilinear $k$-forms]] on $\text{T}_{x}M$.
- **Related definition**: $\Gamma(\Lambda^k(M))$ is the set of differential $k$-forms on $M$.
- **Related definition**: $\Omega^k(M)$ is the set of smooth $k$-forms on $M$.
- **Remark**: As $d_{\varphi(x)}\varphi ^{-1}:\mathbb{R}^m\to \text{T}_{x}M$ is a homeomorphism, by [[Exterior Algebra|Example 2]], we can define an isomorphism: $$\begin{array}{cccc} {\Lambda^k(d_{\varphi(x)}\varphi ^{-1})^{*}:}&{\Lambda^k(\text{T}_{x}^{*}M)}&\to&{\Lambda^k((\mathbb{R}^m)^{*})}\\&{\omega} &\mapsto & {(v_{1},\dots,v_{k})\mapsto \omega(d_{\varphi(x)}\varphi ^{-1}(v_{1}),\dots,d_{\varphi(x)}\varphi ^{-1}(v_{k}))} \end{array}{}$$Then, $\Lambda^k(M)$ admits the [[initial topology]] and a smooth structure using the bijections: $$\begin{array}{cccc} {}&{\pi ^{-1}(U)}&\to&{\varphi(U)\times\Lambda^k((\mathbb{R}^m)^{*})}\\&{(x,\omega)} &\mapsto & {(\varphi(x),\Lambda^k(d_{\varphi(x)}\varphi ^{-1})^{*}(\omega))} \end{array}{}$$ 
---
> [!lemma] Proposition 1
> $\Gamma$