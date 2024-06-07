#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $F\in C^\infty(M,N)$ be a [[differentiable function|smooth function]]. 
> 1. The ***differential of $F$ at $p$*** is:$$\begin{array}{cccc} {d_{p}F:}&{\text{T}_{p}M}&\to&{\text{T}_{F(p)}N}\\&{v} &\mapsto & {(g\mapsto v(g\circ F))} \end{array}{}$$
> 2. The ***differential of $F$*** is then: $$dF:\text{T}M\to \text{T}N,\quad (p,v)\mapsto d_{p}F(v)$$

- **Remark**: given $f\in C^\infty(M)$, the differential at $p$ is defined as $$\begin{array}{cccc} {d_{p}f:}&{\text{T}_{p}M}&\to&{\mathbb{R}}\\&{v} &\mapsto & {v(f)\left. \frac{d}{dt} \right| _{f(p)}} \end{array}{}$$
- **Related definition**: $F$ is an ***immersion***, if $d_{p}F$ is injective for all $p\in M$.
- **Related definition**: For $(U,x^j)$ and $(V,y^i)$ charts at $p$ and $F(p)$ respectively, by [[Tangent Space II|Proposition 2.3]]$$d_{p}F\left( \left. \frac{ \partial  }{ \partial x^j }  \right|_{p}  \right) =\sum_{i=1}^{n}\left. \frac{ \partial (y^i\circ F) }{ \partial x^j } \right| _{p}\left. \frac{ \partial  }{ \partial y^i }  \right|_{F(p)}  $$Then, $\{ \partial(y_{i}\circ F) / \partial x^j \}$ is called the ***Jacobian*** of $F$.
- **Related definition**: For $F\in C^\infty(M,N)$, the ***dual map*** is defined as: $$\begin{array}{cccc} {\delta f:}&{\text{T}^{*}_{F(p)}N}&\to&{\text{T}^{*}_{p}M}\\&{\omega} &\mapsto & {\omega \circ d_{p}f} \end{array}{}$$
---
##### Properties
> [!lemma] Lemma 1
> Let $M,N,R$ be [[Smooth Manifold|smooth manifolds]] and $F\in C^\infty(M,N)$ and $G\in C^\infty(N,R)$ [[Differentiable Function|smooth maps]] 
> 1. $d_{p}F$ is a well-defined linear map.
> 2. $d_{p}(G\circ F)=d_{F(p)}G\circ d_{p}F$
> 3. if $R=\mathbb{R}$, $\delta F(d_{F(p)}G)=d_{p}(G\circ F)$
> 4. $dF$ is smooth.

> [!proof]-
> We have:
> 1. For $v,w\in \text{T}_{p}M$, we have: $$d_{p}F(v)(f+g)=v((f+g)\circ F)=v(f\circ F+g\circ F)=v(f\circ F)+v(g\circ F)=d_{p}F(v)(f)+d_{p}F(v)(g)$$Further, $$\begin{align}d_{p}F(v)(fg)&=v((fg)\circ F)=v((f\circ F)(g\circ F))=f(F(p))v(g\circ F)+v(f\circ F)g(F(p))\\&=f(F(p))d_{p}F(v)(g)+d_{p}F(v)(f)g(F(p))\end{align}$$Therefore, $d_{p}F$ is well-defined. Also, one can naturally see that $d_{p}F$ is linear.
> 2. For $v\in \text{T}_{p}M$, we have that: $$d_{p}(G\circ F)(v)(g)=v(g\circ G\circ F)=d_{p}F(v)(g\circ G)=d_{F(p)}G(d_{p}F(v))(g)$$
> 3. This is an application of the definition of dual and chain rule.
---
> [!lemma] Theorem 2
> Let $M,N$ be smooth manifolds where $M$ is connected. Further, let $F\in C^\infty(M,N)$. 
> 1. if $d_{p}F=0$ for all $p\in M$, then $F$ is constant.

> [!proof]-
> Let $q\in F(M)$. Then, $F^{-1}(q)$ is closed. It suffices to show that $F^{-1}(q)$ is open. Let $p\in F^{-1}(q)$ and choose charts $(U,x^i)$ and $(V,y^j)$ at $p$ and $q$ respectively s.t. $F(U)\subseteq V$. Then, on $U$, $$0=d_{p}F\left( \left. \frac{ \partial  }{ \partial x^j }  \right|_{p}  \right) =\sum_{i=1}^{n} \left. \frac{ \partial (y^i\circ F) }{ \partial x^j }  \right| _{p} \left. \frac{ \partial  }{ \partial y^i }  \right| _{F(p)}$$which implies that $\frac{ \partial (y^i\circ F) }{ \partial x^j }=0$ for all $i\in[n]$ and $j\in [m]$. Therefore, $y^i\circ F$ are constant on $U$. It follows that $F(U)=\{ q \}$. Therefore, $F^{-1}(q)$ is open and as $M$ is connected, $F^{-1}(q)=M$.
---

> [!lemma] Lemma 2
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and a [[Differentiable Function|smooth map]] $F:M\to N$ of constant [[rank]] $k$. Then, for $y\in F(M)$:
> 1. $F^{-1}(y)\subseteq M$ is a regular $m-k$ dimensional [[Submanifold]].
> 2. for the injection $i:F^{-1}(y)\hookrightarrow M$ and $p\in F^{-1}(y)$:$$d_{p}i(\text{T}_{p}(F^{-1}(y)))=\text{ker }d_{p}F$$

> [!proof]-
> We have:
> 1. From [[Submanifold|Theorem 1]].
> 2. Consider the map $F\circ i:F^{-1}(y)\to N,p\mapsto y$. Then, $d_{p}(f\circ i)=0$. Using the chain rule, $$d_{i(p)}F\circ d_{p}i=0$$In particular, $d_{p}i(\text{T}_{p}(F^{-1}(y)))\subseteq \text{ker }d_{p}F$.
>    
>    For the other inclusion, as the rank of $i$ at any $p\in F^{-1}(y)$ is $m-k$. Therefore, by Lemma 1.2, $\text{dim }d_{p}i(\text{T}_{p}(F^{-1}y))=m-k$. Then, $$\text{dim }\text{ker }d_{p}F=\text{dim }\text{T}_{p}M-\text{dim }d_{p}F(\text{T}_{p}M)=m-k$$This implies the inverse conclusion.
---
> [!lemma] Proposition 1
> Let $M,N$ be a [[smooth manifold]] and $F:N\to M$ be a [[Smooth Function|smooth map]]. Then, for a [[Vector Field]] $V\in \Gamma(TM)$, $$\begin{array}{cccc} {F_{*}V:}&{N}&\to&{TN}\\&{p} &\mapsto & {d_{p}F(V(p))} \end{array}{}$$
---
