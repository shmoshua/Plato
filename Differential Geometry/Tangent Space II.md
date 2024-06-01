#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. For $p\in M$, a ***tangent vector*** at $p$ is a linear form $v\in C^\infty_{p}(M)^{*}$ that satisfies the Leibniz rule, i.e. $$v(fg)=f(p)v(g)+v(f)g(p),\quad \forall f,g\in C^\infty_{p}(M)$$where $C^\infty_{p}(M)$ is the [[ring of germs]] at $p$. Then, the ***tangent space*** $\text{T}_{p}M$ denotes the space of tangent vectors.
- **Remark**: $\text{T}_{p}M$ is a $\mathbb{R}$-vector space.
- **Related notation**: For $C^\infty_{p}(M)$, we denote the ideal $I_{p}:=\{f\in C_{p}^\infty(M):f(p)=0  \}$.
- **Related definition**: For a chart $(U,\varphi)$ on $M$ with coordinate functions $x^1,\dots,x^m$, we have: $(\partial/\partial x^i)|_{p}\in \text{T}_{p}M$ defined as: $$\left( \left. \frac{ \partial  }{ \partial x^i } \right| _{p} \right)(f):=\left. \frac{ \partial f  }{ \partial x^i } \right|_{p}:=\left. \frac{ \partial f\circ \varphi ^{-1}  }{ \partial \pi^i }  \right|_{\varphi(p)}  $$
---
##### Properties
> [!lemma] Lemma 1
> For any germ of a constant function $c\in C_{p}^\infty(M)$ and $v\in \text{T}_{p}M$, $v(c)=0$.

> [!proof]-
> We have that: $$v(1)=v(1\cdot 1)=v(1)+v(1)=2v(1)$$Therefore, $v(1)=0$ and hence $v(c)=c\cdot v(1)=0$.
---
> [!lemma] Proposition 2
> Let $M$ be a smooth manifold. Then, 
> 1. $\text{T}_{p}M\cong (I_{p}/ I_{p}^{2})^{*}$
> 2. $\text{dim T}_{p}M=m$.
> 3. $\left\{  \left. \frac{ \partial  }{ \partial x^i } \right|_{p}: i\in[m]  \right\}$ forms the basis of $\text{T}_{p}M$. For any $v\in \text{T}_{p}M$: $$v=\sum_{i=1}^{m}v(x^i)\left. \frac{ \partial  }{ \partial x^i }  \right| _{p}$$

> [!proof]-
> We have: 
> 1. Let $v\in \text{T}_{p}M$. Then, $v\in I_{p}^{*}$. Consider $f,g\in I_{p}$. Then, $$v(fg)=f(p)v(g)+v(f)g(p)=0$$Therefore, $I_{p}^{2}\subseteq \text{ker }v$ and we can consider $v\in (I_{p}/ I_{p}^{2})^{*}$.
>    
>    Conversely, let $\ell\in(I_{p}/ I_{p}^{2})^{*}$. We define $v\in \text{T}_{p}M$ s.t. $$v(f):=\ell(\pi(f-f(p))),\quad \forall f\in C^\infty_{p}(M)$$where $\pi$ is the canonical projection. Then, $v$ is clearly linear and: $$\begin{align}v(fg)&=\ell(\pi(fg-f(p)g(p)))\\&=\ell(\pi((f-f(p))(g-g(p))+f(p)(g-g(p))+g(p)(f-f(p))))\\&=\ell(\pi((f-f(p))(g-g(p))))+f(p)\ell(\pi(g-g(p)))+g(p)\ell(\pi(f-f(p)))\\&=f(p)v(g)+g(p)v(f)\end{align}$$
>  2. Let $(U,\varphi)$ be a chart at $p$ with coordinate functions $\varphi_{1},\dots,\varphi_{m}$. For $f\in I_{p}$, $f\circ\varphi ^{-1}\in C^\infty(\varphi(U))$ and by [[Smooth Function|Corollary of Hadamard's Lemma]]: $$f\circ \varphi ^{-1}(x)=\sum_{i=1}^{m}(x_{i}-\varphi_{i}(p)) \left. \frac{ \partial f\circ \varphi ^{-1} }{ \partial x_{i} }  \right| _{\varphi(p)} +\sum_{i,j=1}^{m}(x_{i}-\varphi_{i}(p))(x_{j}-\varphi_{j}(p))h(x)$$Therefore, for all $q\in U$, $$f(q)=\sum_{i=1}^{m}(\varphi_{i}(q)-\varphi_{i}(p)) \left. \frac{ \partial f\circ \varphi ^{-1} }{ \partial x_{i} }  \right| _{\varphi(p)} +\sum_{i,j=1}^{m}(\varphi_{i}(q)-\varphi_{i}(p))(\varphi_{j}(q)-\varphi_{j}(p))h(q)$$where $h\in C^\infty(U)$. Therefore, $$\pi(f)=\sum_{i=1}^{m}\left. \frac{ \partial f\circ \varphi ^{-1} }{ \partial x_{i} }  \right| _{\varphi(p)}(\varphi_{i}-\varphi_{i}(p))+I_{p}^{2}$$It follows that $\{ \varphi_{i}-\varphi_{i}(p)+I^{2}_{p}: i\in [m] \}$ spans $I_{p} / I_{p}^{2}$. Consequently, $\text{dim }I_{p} / I_{p}^{2}\leq m$. 
>     
>     Now we show that they are linearly independent. Suppose that $\sum_{i=1}^{m}a_{i}(\varphi_{i}-\varphi_{i}(p))\in I_{p}^{2}$. Then, $$\sum_{i=1}^{m}a_{i}(\varphi_{i}-\varphi_{i}(p))\circ \varphi ^{-1}=\sum_{i=1}^{m}a_{i}(\pi_{i}-\pi_{i}(\varphi(p)))$$Therefore, $\sum_{i=1}^{m}a_{i}(\pi_{i}-\pi_{i}(\varphi(p)))\in I_{\varphi(p)}^{2}\subseteq C^\infty_{\varphi(p)}(\mathbb{R}^m)$. However, this implies that: $$\left. \frac{ \partial  }{ \partial \pi_{j} } \right|_{\varphi(p)} \left( \sum_{i=1}^{m}a_{i}(\pi_{i}-\pi_{i}(\varphi(p))) \right) =0 $$which means that $a_{j}=0$ for all $j\in [m]$. Therefore, $\text{dim }\text{T}_{p}M=\text{dim }I_{p} / I_{p}^{2}=m$.
>  4. As $\{ \varphi_{i}-\varphi_{i}(p)+I_{p}^{2} \}_{i}$ forms a basis of $I_{p} / I_{p}^{2}$, we have: $$\left. \frac{ \partial  }{ \partial x^i }  \right| _{p}(x^j-x^j(p))=\delta_{ij}$$Therefore, $\left\{  \left. \frac{ \partial  }{ \partial x^i } \right|_{p}  \right\}_{i}$ forms a basis of $\text{T}_{p}M$. Further, $$v(x^j-x^j(p))=v(x^j)=\sum_{i=1}^{m}v(x^i)\delta_{ij}=\sum_{i=1}^{m}v(x^i)\left. \frac{ \partial  }{ \partial x^i }  \right|_{p}(x^j-x^j(p)) $$This proves the statement.
- **Remark**: For another chart $(V,\psi)$ with $y_{1},\dots,y_{m}$ as coordinate functions, $$\left. \frac{ \partial  }{ \partial y^j }  \right|_{p}=\sum_{i=1}^{m}\left. \frac{ \partial x^i }{ \partial y^j } \right| _{p}\left. \frac{ \partial  }{ \partial x^i }  \right|_{p}   $$i.e. $(\partial / \partial x^i)|_{p}$ depends on the whole chart $\varphi$ and not just $x^i$.
---
> [!lemma] Proposition 3
> Let $M$ be a smooth manifold and $p\in M$. Let further $(U,\varphi)$ be a chart centered at $p$.  Then, $$\mathbb{R}^m\to \text{T}_{p}M,\quad v\mapsto\left( f\mapsto d_{0}(f\circ \varphi ^{-1})(v)=\left. \frac{d}{dt} \right| _{t=0}(f\circ \varphi ^{-1})(tv)\right)$$is a vector space isomorphism.

> [!proof]-
> As $d_{0}(f\circ\varphi ^{-1}):\mathbb{R}^n\to \mathbb{R}$ is a linear map, we have that the map is linear. 
> 
> For injectivity, consider $d_{0}(f\circ\varphi ^{-1})(v)=0$ for any $f\in C^\infty_{p}(M)$. Then, by considering $f=p_{i}\circ\varphi$, $$0=d_{0}p_{i}(v)=\left. \frac{d}{dt} \right| _{t=0}p_{i}(tv)=p_{i}(v)$$Therefore, $v=0$ and the map is injective.
> 
> For surjectivity, let $w\in \text{T}_{p}M$. Then, we have that: $$w=w(x^i)\left. \frac{ \partial  }{ \partial x^i } \right| _{p} $$Let $v:=(w(x^1),\dots,w(x^m))$. Then, $$d_{0}(f\circ \varphi ^{-1})(v)=d_{0}(f\circ \varphi ^{-1})\left( w(x^i)e_{i}\right)=w(x^i)d_{0}(f\circ \varphi ^{-1})(e_{i})=w(x^i)\left( \left. \frac{ \partial  }{ \partial x^i } \right| _{p}  \right)(f) =w(f)$$
---
##### Examples
> [!h] Example 1
> Let $U\subseteq \mathbb{R}^m$ be an open subset. Then, with the atlas $\{ (U,\text{id}) \}$, $\text{T}_{p}U=\mathbb{R}^m$ for any $p\in U$.
---

