#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. For $p\in M$, a ***tangent vector*** at $p$ is a linear form $v\in C^\infty_{p}(M)^{*}$ that satisfies the Leibniz rule, i.e. $$v(fg)=f(p)v(g)+v(f)g(p),\quad \forall f,g\in C^\infty_{p}(M)$$where $C^\infty_{p}(M)$ is the [[ring of germs]] at $p$. Then, the ***tangent space*** $\text{T}_{p}M$ denotes the space of tangent vectors.
- **Remark**: $\text{T}_{p}M$ is a $\mathbb{R}$-vector space.
---
##### Properties

> [!lemma] Proposition 1
> Let $M$ be a smooth manifold. Then, 
> 1. $\text{T}_{p}M\cong (C_{p}^\infty(M)_{0} / C_{p}^\infty(M)_{0}^{2})^{*}$
> 2. $\text{dim} \ C_{p}^\infty(M)_{0} / C_{p}^\infty(M)_{0}^{2}=m$
> 3. $\text{dim T}_{p}M=m$.

> [!proof]+
> We have: 
> 1. Let $v\in \text{T}_{p}M$. Then, $v\in (C_{p}^\infty(M)_{0})^{*}$. Consider $f,g\in C_{p}^\infty(M)_{0}$. Then, $$v(fg)=f(p)v(g)+v(f)g(p)=0$$Therefore, $C_{p}^\infty(M)_{0}^{2}\subseteq \text{ker }v$ and we can consider $v\in(C_{p}^\infty(M)_{0} / C_{p}^\infty(M)_{0}^{2})^{*}$.
>    
>    Conversely, let $\ell\in(C_{p}^\infty(M)_{0} / C_{p}^\infty(M)_{0}^{2})^{*}$. We define $v\in \text{T}_{p}M$ s.t. $$v(f):=\ell(\pi(f-f(p))),\forall f\in C^\infty_{p}(M)$$where $\pi$ is the canonical projection. Then, $v$ is clearly linear and: $$\begin{align}v(fg)&=\ell(\pi(fg-f(p)g(p)))\\&=\ell(\pi((f-f(p))(g-g(p))+f(p)(g-g(p))+g(p)(f-f(p))))\\&=\ell(\pi((f-f(p))(g-g(p))))+f(p)\ell(\pi(g-g(p)))+g(p)\ell(\pi(f-f(p)))\\&=f(p)v(g)+g(p)v(f)\end{align}$$
>  2. 
---
> [!lemma] Proposition 1
> Let $M$ be a [[smooth manifold]]. Then, $$\begin{array}{cccc} {}&{\mathbb{R}^m}&\to&{\text{T}_{p}M}\\&{v} &\mapsto & {[U,\varphi,v]_{p}} \end{array}{}$$is a bijection. The resulting vector space structure on $\text{T}_{p}M$ is independent of the choice of the chart $(U,\varphi)$.

> [!proof]-
> We have:
> 1. **The map is injective**: Let $v_{1},v_{2}\in \mathbb{R}^m$ and suppose $[U,\varphi,v_{1}]\sim[U,\varphi ,v_{2}]$. Then, $$v_{1}=d_{\varphi(p)}(\varphi \circ \varphi ^{-1})v_{1}=v_{2}$$
> 2. **The map is surjective**: Let $[V,\psi,w]_{p}\in \text{T}_{p}M$. Then, $$d_{\varphi(p)}(\psi \circ \varphi ^{-1})d_{\psi(p)}(\varphi \circ \psi ^{-1})w=d_{\psi(p)}(\psi \circ \psi ^{-1})w=w$$Therefore, $[U,\varphi,d_{\psi(p)}(\varphi \circ \psi ^{-1})w]_{p}=[V,\psi,w]_{p}$.
> 3. **The vector space structure is independent**: Let $v_{1},v_{2}\in \text{T}_{p}M$, where 
> 	- $v_{1}$ is represented by $(U,\varphi,u_{1}),(W,\psi,w_{1})$ 
> 	- $v_{2}$ is represented by $(U,\varphi,u_{2}),(W,\psi,w_{2})$ 
> 	
> 	We need to show that $(U,\varphi,u_{1}+u_{2})\sim(W,\psi,w_{1}+w_{2})$. Indeed, $$d_{\varphi(p)}(\psi \circ \varphi ^{-1})(u_{1}+u_{2})=w_{1}+w_{2}$$and for $\lambda\in \mathbb{R}$, $$d_{\varphi(p)}(\psi \circ \varphi ^{-1})(\lambda u_{1})=\lambda w_{1}$$
---
##### Examples
> [!h] Example 1
> Let $U\subseteq \mathbb{R}^m$ be an open subset. Then, with the atlas $\{ (U,\text{id}) \}$, $\text{T}_{p}U=\mathbb{R}^m$ for any $p\in U$.
---

