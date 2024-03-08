#Definition #DifferentialGeometry 
> [!definition]
> Let $M$ be a [[smooth manifold]]. A ***differential $k$-form on $M$*** is a map $\omega:M\to \Lambda^k(M)$ s.t. $\pi \circ\omega=\text{id}_{M}$ where: $$\Lambda^k(M):=\bigcup_{x\in M}^{}\{ x \}\times\Lambda^k(\text{T}_{x}^{*}M)$$with $\Lambda^k(\text{T}_{x}^{*}M)$ as the vector space of [[Exterior Algebra|alternating multilinear $k$-forms]] on $\text{T}_{x}M$.
- **Related definition**: $\Gamma(\Lambda^k(M))$ is the set of differential $k$-forms on $M$.
- **Related definition**: $\Omega^k(M)$ is the set of smooth $k$-forms on $M$.
- **Remark**: As $d_{\varphi(x)}\varphi ^{-1}:\mathbb{R}^m\to \text{T}_{x}M$ is a homeomorphism, by [[Exterior Algebra|Example 2]], we can define an isomorphism: $$\begin{array}{cccc} {\Lambda^k(d_{\varphi(x)}\varphi ^{-1})^{*}:}&{\Lambda^k(\text{T}_{x}^{*}M)}&\to&{\Lambda^k((\mathbb{R}^m)^{*})}\\&{\omega} &\mapsto & {(v_{1},\dots,v_{k})\mapsto \omega(d_{\varphi(x)}\varphi ^{-1}(v_{1}),\dots,d_{\varphi(x)}\varphi ^{-1}(v_{k}))} \end{array}{}$$Then, $\Lambda^k(M)$ admits the [[initial topology]] and a smooth structure using the bijections: $$\begin{array}{cccc} {}&{\pi ^{-1}(U)}&\to&{\varphi(U)\times\Lambda^k((\mathbb{R}^m)^{*})}\\&{(x,\omega)} &\mapsto & {(\varphi(x),\Lambda^k(d_{\varphi(x)}\varphi ^{-1})^{*}(\omega))} \end{array}{}$$ 
- **Remark**: For chart $(U,\varphi)$, $\omega\in \Gamma(\Lambda ^{k}(M))$ and $p\in U$, we can uniquely write: $$\omega_{p}=\sum_{1\leq i_{1}<\dots<i_{k}\leq m}^{}a_{i_{1}\dots i_{k}}(p)(dx_{i_{1}})_{p}\land\dots \land(dx_{i_{k}})_{p}$$where $dx_{i}:=\varphi ^{*}(d\pi_{i})$, as they form a basis per [[Exterior Algebra|Proposition 3]]. Using multi-index $I$, we can write: $$\omega|_{U}=\sum_{I}^{}a_{I}dx_{I}$$
---
##### Properties
> [!lemma] Proposition 1
> For $\Gamma(\Lambda^k(M))$, we have: 
> 1. $\Gamma(\Lambda^k(M))$ is a vector space.
> 2. $\Gamma(\Lambda^k(M))$ is a module.
> 3. $\Gamma(\Lambda^*(M)):=\bigoplus_{k\geq 0}\Gamma(\Lambda^k(M))$ is an associative graded-commutative algebra.

> [!proof]-
> We have:
> 1. For $\alpha,\beta\in \Gamma(\Lambda^k(M))$ and $\mu,\lambda\in \mathbb{R}$, we have that $\mu\alpha+\lambda\beta\in \Gamma(\Lambda^k(M))$ where: $$(\mu\alpha+\lambda\beta)_{x}:=\mu \alpha_{x}+\lambda\beta_{x}$$
> 2. For a function $f:M\to \mathbb{R}$ and $\alpha\in \Gamma(\Lambda^k(M))$, we have $f\alpha\in \Gamma(\Lambda^k(M))$ where: $$(f\alpha)_{x}:=f(x)\alpha_{x}$$
> 3. For $\alpha\in \Gamma(\Lambda^p(M)),\beta\in \Gamma(\Lambda^q(M))$, we extend the [[Exterior Algebra|exterior product]] $\alpha \land\beta\in \Gamma(\Lambda^{p+q}(M))$ where: $$(\alpha \land\beta)_{x}:=\alpha_{x}\land\beta_{x}$$Therefore, by [[Exterior Algebra|Proposition 2]], $\Gamma(\Lambda ^{*}(M))$ is an associative graded-commutative algebra.
---
> [!lemma] Lemma 2
> For [[Smooth Manifold|smooth manifolds]] $M,N$ and $P$ with [[Smooth Function|smooth maps]] $F:N\to M$ and $G:M\to P$, it holds that: 
> 1. the [[pullback]] $F^{*}:\Gamma(\Lambda^k(M))\to\Gamma(\Lambda^k(N))$ is $\mathbb{R}$-linear.
> 2. for $\omega_{1}\in \Gamma(\Lambda^p(M)),\omega_{2}\in \Gamma(\Lambda^q(M))$, $$F^{*}(\omega_{1}\land \omega_{2})=F^{*}(\omega_{1})\land F^{*}(\omega_{2})$$
> 3. for smooth $h:M\to \mathbb{R}$ and $\omega\in\Gamma(\Lambda^k(M))$: $$F^{*}(h\omega)=(h\circ F)F^{*}(\omega)$$
> 4. We have: $$(G\circ F)^{*}(\omega)=F^{*} (G^{*}(\omega))$$

> [!proof]-
> We have: 
> 1. Let $\omega_{1},\omega_{2}\in \Gamma(\Lambda^k(M))$ and $\lambda\in \mathbb{R}$. Then, $$\begin{align}F^{*}(\lambda\omega_{1}+\omega_{2})_{x}(v_{1},\dots,v_{k})&=(\lambda\omega_{1}+\omega_{2})_{F(x)}(d_{x}F(v_{1}),\dots,d_{x}F(v_{k}))\end{align}$$
> 2. Let $x\in N$ and $v_{1},\dots,v_{{p+q}}\in \text{T}_{x}N$. Then, $$\begin{align}&F^{*}(\omega_{1}\land \omega_{2})_{x}(v_{1},\dots,v_{p+q})\\&=(\omega_{1}\land\omega_{2})_{F(x)}(d_{x}F(v_{1}),\dots,d_{x}F(v_{p+q}))\\&=(\omega_{1,F(x)}\land\omega_{2,F(x)})(d_{x}F(v_{1}),\dots,d_{x}F(v_{p+q}))\\&=\frac{1}{p!q!}\sum_{\sigma\in S_{p+q}}^{}\text{sgn}(\sigma)\omega_{1,F(x)}(d_{x}F(v_{\sigma(1)}),\dots,d_{x}F(v_{\sigma(p)}))\omega_{2,F(x)}(d_{x}F(v_{\sigma(p+1)}),\dots,d_{x}F(v_{\sigma(p+q)}))\\&=\frac{1}{p!q!}\sum_{\sigma\in S_{p+q}}^{}\text{sgn}(\sigma)(F^{*}\omega_{1})_{x}(v_{\sigma(1)},\dots,v_{\sigma(p)})(F^{*}\omega_{2})_{x}(v_{\sigma(p+1)},\dots,v_{\sigma(p+q)})\\&=((F^{*}\omega_{1})_{x}\land(F^{*}\omega_{2})_{x})(v_{1},\dots,v_{p+q})\\&=(F^{*}\omega_{1}\land F^{*}\omega_{2})_{x}(v_{1},\dots,v_{p+q})\end{align}$$
> 3. We have: $$\begin{align}F^{*}(h\omega)_{x}(v_{1},\dots,v_{k})&=h(F(x))\omega_{F(x)}(d_{x}F(v_{1}),\dots,d_{x}F(v_{k}))=(h(F(x)))F^{*}\omega_{x}(v_{1},\dots,v_{k})\end{align}$$
> 4. For $\omega\in \Gamma(\Lambda^k(P))$, $$\begin{align}(G\circ F)^{*}(\omega)_{x}(v_{1},\dots,v_{k})&=\omega_{G(F(x))}(d_{x}(G\circ F)(v_{1}),\dots,d_{x}(G\circ F)(v_{k}))\\&=\omega_{G(F(x))}(d_{F(x)}Gd_{x}(F)(v_{1}),\dots,d_{F(x)}Gd_{x}(F)(v_{k}))\\&=G^{*}\omega_{F(x)}(d_{x}F(v_{1}),\dots,d_{x}F(v_{k}))\\&=F^{*}(G^{*}(\omega))_{x}(v_{1},\dots,v_{k})\end{align}$$
---
> [!lemma] Lemma 3
> Let $M$ be a [[smooth manifold]] and $\omega\in \Gamma(\Lambda^k(M))$. Then, the following are equivalent.
> 1. $\omega$ is smooth, i.e. $\omega\in \Omega^k(M)$
> 2. for every $(U,\varphi)$, the coordinates $a_{I}:U\to \mathbb{R}$ are smooth w.r.t. $(U,\varphi)$.

> [!proof]-
> We have: 
> 1. Let $\omega\in \Gamma(\Lambda^k(M))$ be smooth and $(U,\varphi)$ a chart on $M$. Further, let $I:=i_{1}\dots i_{k}$ a multi-index where $1\leq i_{1}<\dots<i_{k}\leq m$. Let $(V,\psi)$ be another chart on $M$ s.t. $U\subseteq V$. We further define, $$v_{i_{k}}:=d_{\psi \circ \varphi ^{-1}(v)}$$
>    
>    Then, $(\pi ^{-1}(V),\Psi)$ is a chart on $\Lambda^k(M)$ where:
>    $$\begin{array}{cccc} {\Psi:}&{\pi ^{-1}(V)}&\to&{\psi(V)\times\Lambda^k((\mathbb{R}^m)^{*})}\\&{(x,\omega_{x})} &\mapsto & {(\psi(x),\Lambda^k(d_{\psi(x)}\psi ^{-1})^{*}(\omega_{x}))} \end{array}{}$$Therefore, from $\omega|_{U}$ being smooth, $\Psi \circ\omega \circ \varphi ^{-1}:\varphi(U)\to \psi(V)\times\Lambda^k((\mathbb{R}^m)^{*})$ is smooth where: $$\begin{align}(\Psi \circ \omega \circ \varphi ^{-1})(v)&=\Psi(\varphi ^{-1}(v),\omega_{\varphi ^{-1}(v)})\\&=((\psi \circ \varphi ^{-1})(v),\Lambda^k(d_{\psi \circ \varphi ^{-1}(v)}\psi ^{-1})^{*}(\omega_{\varphi ^{-1}(v)}))\end{align}$$We now define now a function $F:U\to \mathbb{R}^m\times\dots \times\mathbb{R}^m$ where:$$F(v)=(d_{v}(\psi \circ \varphi ^{-1})e_{i_{1}},\dots,d_{v}(\psi \circ \varphi ^{-1})e_{i_{k}})$$which is smooth. Then, $$\begin{array}{ccccc}U&\to&U\times \mathbb{R}^m\times\dots \times \mathbb{R}^m&\to&\mathbb{R}\\v&\mapsto&(v,F(v))&\mapsto&\Lambda^k(d_{\psi \circ \varphi ^{-1}(v)}\psi ^{-1})^{*}(\omega_{\varphi ^{-1}(v)})(F(v))\end{array}$$ is smooth.
>    
>    Indeed, we have: $$\begin{align}\Lambda^k(d_{\psi \circ \varphi ^{-1}(v)}\psi ^{-1})^{*}(\omega_{\varphi ^{-1}(v)})(F(v))&=\omega_{\varphi ^{-1}(v)}(d_{\psi \circ \varphi ^{-1}(v)}\psi ^{-1}d_{v}(\psi \circ \varphi ^{-1})e_{i_{1}},\dots,d_{\psi \circ \varphi ^{-1}(v)}\psi ^{-1}d_{v}(\psi \circ \varphi ^{-1})e_{i_{k}})\\&=\omega_{\varphi ^{-1}(v)}(d_{v}\varphi ^{-1}e_{i_{1}},\dots,d_{v}\varphi ^{-1}e_{i_{k}})\\&=\sum_{J}^{}a_{J}(\varphi ^{-1}(v))(dx_{J})_{\varphi ^{-1}(v)}(d_{v}\varphi ^{-1}e_{i_{1}},\dots,d_{v}\varphi ^{-1}e_{i_{k}})\\&=\sum_{J}^{}a_{J}(\varphi ^{-1}(v))\det[(dx_{j_{p}})_{\varphi ^{-1}(v)}(d_{v}\varphi ^{-1}e_{i_{q}})]_{p,q=1}^k\\&=\sum_{J}^{}(a_{J}\circ \varphi ^{-1})(v)\det[(\varphi ^{*}(d\pi_{j_{p}}))_{\varphi ^{-1}(v)}(d_{v}\varphi ^{-1}e_{i_{q}})]_{p,q=1}^k\\&=\sum_{J}^{}(a_{J}\circ \varphi ^{-1})(v)\det[(d\pi_{j_{p}})_{v}e_{i_{q}}]_{p,q=1}^k\\&=\sum_{J}^{}(a_{J}\circ \varphi ^{-1})(v)\det[\delta_{j_{p}i_{q}}]_{p,q=1}^k\\&=(a_{I}\circ \varphi ^{-1})(v)\end{align}$$
>    
>    Therefore, $a_{I}$ is smooth.
>  2. Assume that the coordinates $a_{I}$ are smooth for every $(U,\varphi)$. Then, let $(U,\varphi)$ and $(\pi ^{-1}(V),\Psi)$ be charts on $M$ and $\Lambda^k(M)$ respectively s.t. $\omega(U)\subseteq \pi ^{-1}(V)$. Then, $U=\pi(\omega(U))\subseteq V$. We now have to show that $\Psi \circ\omega \circ\varphi ^{-1}:\mathbb{R}^m\supseteq\varphi(U)\to \psi(V)\times\Lambda^k((\mathbb{R}^m)^{*})$ is smooth. It suffices to show that $v\mapsto \Lambda^k(d_{\psi \circ \varphi ^{-1}(v)}\psi ^{-1})^{*}(\omega_{\varphi ^{-1}(v)})$ is smooth. 
>     
>     For any $v_{1},\dots,v_{k}\in \mathbb{R}^m$, we have: $$\begin{align}&\Lambda^k(d_{\psi \circ \varphi ^{-1}(v)}\psi ^{-1})^{*}(\omega_{\varphi ^{-1}(v)})(v_{1},\dots,v_{k})\\&=\sum_{I}^{}(a_{I}\circ \varphi ^{-1})(v)\det[(dx_{i_{p}})_{\varphi ^{-1}(v)}(d_{\psi \circ \varphi ^{-1}(v)}\psi ^{-1}v_{q})]_{pq}\\&=\sum_{I}^{}(a_{I}\circ \varphi ^{-1})(v)\det[(\varphi ^{*}(d\pi_{i_{p}}))_{\varphi ^{-1}(v)}(d_{\psi \circ \varphi ^{-1}(v)}\psi ^{-1}v_{q})]_{pq}\\&=\sum_{I}^{}(a_{I}\circ \varphi ^{-1})(v)\det[(d\pi_{i_{p}})_{v}(d_{\psi \circ \varphi ^{-1}(v)}(\varphi \circ \psi ^{-1})v_{q})]_{pq}\\&=\sum_{I}^{}(a_{I}\circ \varphi ^{-1})(v)\underbrace{ \det[\pi_{i_{p}}(d_{\psi \circ \varphi ^{-1}(v)}(\varphi \circ \psi ^{-1})v_{q})]_{pq} }_{ =:c_{I}(v) }\end{align}$$Therefore, $v\mapsto \Lambda^k(d_{\psi \circ \varphi ^{-1}(v)}\psi ^{-1})^{*}(\omega_{\varphi ^{-1}(v)})(v_{1},\dots,v_{k})$ is smooth for all  $v_{1},\dots,v_{k}\in \mathbb{R}^m$ and: $$\omega|_{U}\in \Omega^k(U)$$by [[Differentiable Function|Lemma 1]], $\omega$ is smooth.
---
> [!lemma] Proposition 4
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $F:N\to M$ a smooth map. Then, 
> 1. for $\alpha\in \Omega^p(M),\beta\in \Omega^q(M)$, $\alpha\land\beta\in\Omega^{p+q}(M)$.
> 2. for $\omega\in \Omega^k(M)$, $F^{*}\omega\in \Omega^k(N)$.

> [!proof]+
> We have: 
> 1. Let $(U,\varphi)$ be a chart on $M$. Then, we can write $\alpha|_{U}=\sum_{I}^{}a_{I}dx_{I}$ and $\beta|_{U}=\sum_{I}^{}b_{I}dx_{I}$, where $a_{I},b_{J}:U\to \mathbb{R}$ are smooth. Therefore, $$\alpha \land\beta=\sum_{I,J}^{}a_{I}b_{J}dx_{I}\land dx_{J}=\sum_{I\cap J= \varnothing}^{}a_{I}b_{J}(\pm{1})dx_{Q}$$where $Q$ is the ordered multi-index of $I\cup J$. As the coordinates $v\mapsto a_{I}(v)b_{J}(v)$ are smooth, $\alpha \land\beta\in \Omega^{p+q}(M)$.
> 2. Let $\omega\in \Omega^k(M)$ and let $(U,\varphi)$ and $(V,\psi)$ be charts on $M$ and $N$ respectively s.t. $F(V)\subseteq U$. Then, in $(U,\varphi)$-local coordinates: $$\omega|_{U}=\sum_{I}^{}a_{I}dx_{I}=\sum_{1\leq i_{1}<\dots<i_{k}\leq m}^{}a_{i_{1}\dots i_{k}}dx_{i_{1}}\land\dots \land dx_{i_{k}}$$Therefore, $$F^{*}\omega|_{U}=\sum_{1\leq i_{1}<\dots<i_{k}\leq m}^{}(a_{i_{1}\dots i_{k}}\circ F)F^{*}(dx_{i_{1}})\land\dots \land F^{*}(dx_{i_{k}})$$Since $F^{*}(dx_{i_{p}})\in \Omega^1(N)$, $F^{*}\omega\in \Omega^k(N)$.
> 
---
##### Examples
> [!h] Example 1
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $F:N\to M$ a [[Smooth Function|smooth map]]. Then, the [[pullback]] is defined as:$$\begin{array}{cccc} {F^{*}:}&{\Gamma(\Lambda^k(M))}&\to&{\Gamma(\Lambda^k(N))}\\&{\omega} &\mapsto & {F^{*}\omega} \end{array}{}$$where $(F^{*}\omega)_{x}(v_{1},\dots,v_{k}):=\omega_{F(x)}(d_{x}F(v_{1}),\dots,d_{x}F(v_{k}))$ for all $x\in N$ and $v_{1},\dots,v_{k}\in \text{T}_{x}N$.
---