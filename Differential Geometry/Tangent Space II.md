#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. For $p\in M$, a ***tangent vector*** at $p$ is a linear form $v\in C^\infty_{p}(M)^{*}$ that satisfies the Leibniz rule, i.e. $$v(fg)=f(p)v(g)+v(f)g(p),\quad \forall f,g\in C^\infty_{p}(M)$$where $C^\infty_{p}(M)$ is the [[ring of germs]] at $p$. Then, the ***tangent space*** $\text{T}_{p}M$ denotes the space of tangent vectors.
- **Remark**: $\text{T}_{p}M$ is a $\mathbb{R}$-vector space.
- **Related notation**: For $C^\infty_{p}(M)$, we denote the ideal $I_{p}:=\{f\in C_{p}^\infty(M):f(p)=0  \}$.
---
##### Properties

> [!lemma] Proposition 1
> Let $M$ be a smooth manifold. Then, 
> 1. $\text{T}_{p}M\cong (I_{p}/ I_{p}^{2})^{*}$
> 2. $\text{dim} \ I_{p}/ I_{p}^{2}=m$
> 3. $\text{dim T}_{p}M=m$.

> [!proof]+
> We have: 
> 1. Let $v\in \text{T}_{p}M$. Then, $v\in I_{p}^{*}$. Consider $f,g\in I_{p}$. Then, $$v(fg)=f(p)v(g)+v(f)g(p)=0$$Therefore, $I_{p}^{2}\subseteq \text{ker }v$ and we can consider $v\in (I_{p}/ I_{p}^{2})^{*}$.
>    
>    Conversely, let $\ell\in(I_{p}/ I_{p}^{2})^{*}$. We define $v\in \text{T}_{p}M$ s.t. $$v(f):=\ell(\pi(f-f(p))),\quad \forall f\in C^\infty_{p}(M)$$where $\pi$ is the canonical projection. Then, $v$ is clearly linear and: $$\begin{align}v(fg)&=\ell(\pi(fg-f(p)g(p)))\\&=\ell(\pi((f-f(p))(g-g(p))+f(p)(g-g(p))+g(p)(f-f(p))))\\&=\ell(\pi((f-f(p))(g-g(p))))+f(p)\ell(\pi(g-g(p)))+g(p)\ell(\pi(f-f(p)))\\&=f(p)v(g)+g(p)v(f)\end{align}$$
>  2. Let $(U,\varphi)$ be a chart at $p$ with coordinate functions $\varphi_{1},\dots,\varphi_{m}$. For $f\in I_{p}$, $f\circ\varphi ^{-1}\in C^\infty(\varphi(U))$ and by [[Smooth Function|Corollary of Hadamard's Lemma]]: $$f\circ \varphi ^{-1}(x)=\sum_{i=1}^{m}(x_{i}-\varphi_{i}(p)) \left. \frac{ \partial f\circ \varphi ^{-1} }{ \partial x_{i} }  \right| _{\varphi(p)} +\sum_{i,j=1}^{m}(x_{i}-\varphi_{i}(p))(x_{j}-\varphi_{j}(p))h(x)$$Therefore, for all $q\in U$, $$f(q)=\sum_{i=1}^{m}(\varphi_{i}(q)-\varphi_{i}(p)) \left. \frac{ \partial f\circ \varphi ^{-1} }{ \partial x_{i} }  \right| _{\varphi(p)} +\sum_{i,j=1}^{m}(\varphi_{i}(q)-\varphi_{i}(p))(\varphi_{j}(q)-\varphi_{j}(p))h(q)$$where $h\in C^\infty(U)$. Therefore, $$\pi(f)=\sum_{i=1}^{m}\left. \frac{ \partial f\circ \varphi ^{-1} }{ \partial x_{i} }  \right| _{\varphi(p)}(\varphi_{i}-\varphi_{i}(p))+I_{p}^{2}$$It follows that $\{ \varphi_{i}-\varphi_{i}(p)+I^{2}_{p}: i\in [m] \}$ spans $I_{p} / I_{p}^{2}$. Consequently, $\text{dim }I_{p} / I_{p}^{2}\leq m$. 
>     
>     Now we show that they are linearly independent. Suppose that $\sum_{i=1}^{m}a_{i}(\varphi_{i}-\varphi_{i}(p))\in I_{x}^{2}$. Then, $$\sum_{i=1}^{m}a_{i}(\varphi_{i}-\varphi_{i}(p))\circ \varphi ^{-1}=\sum_{i=1}^{m}a_{i}()$$
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

