#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $F\in C^\infty(M,N)$ be a [[differentiable function|smooth function]]. The ***differential of $F$*** is:$$\begin{array}{cccc} {d_{p}F:}&{\text{T}_{p}M}&\to&{\text{T}_{F(p)}N}\\&{v} &\mapsto & {(g\mapsto v(g\circ F))} \end{array}{}$$

- **Remark**: given $f\in C^\infty(M)$, the differential at $p$ is defined as $$\begin{array}{cccc} {d_{p}f:}&{\text{T}_{p}M}&\to&{\mathbb{R}}\\&{v} &\mapsto & {v(f)\left. \frac{d}{dt} \right| _{f(p)}} \end{array}{}$$
- **Related definition**: $F$ is an ***immersion***, if $d_{p}F$ is injective for all $p\in M$.
- **Related definition**: For $(U,x^j)$ and $(V,y^i)$ charts at $p$ and $F(p)$ respectively, by [[Tangent Space II|Proposition 2.3]]$$d_{p}F\left( \left. \frac{ \partial  }{ \partial x^j }  \right|_{p}  \right) =\sum_{i=1}^{n}\left. \frac{ \partial (y^i\circ F) }{ \partial x^j } \right| _{p}\left. \frac{ \partial  }{ \partial y^i }  \right|_{F(p)}  $$Then, $\{ \partial(y_{i}\circ F) / \partial x^j \}$ is called the ***Jacobian*** of $F$.
---
##### Properties
> [!lemma] Lemma 1
> Let $M,N,R$ be [[Smooth Manifold|smooth manifolds]] and $F\in C^\infty(M,N)$ and $G\in C^\infty(N,R)$ [[Differentiable Function|smooth maps]] 
> 1. $d_{p}F$ is a well-defined linear map.
> 2.
> 3. $d_{p}(G\circ F)=d_{F(p)}(G)d_{p}(F)$

> [!proof]+
> We have:
> 1. For $v,w\in \text{T}_{p}M$, we have: $$d_{p}F(v)(f+g)=v((f+g)\circ F)=v(f\circ F+g\circ F)=v(f\circ F)+v(g\circ F)=d_{p}F(v)(f)+d_{p}F(v)(g)$$Further, $$\begin{align}d_{p}F(v)(fg)&=v((fg)\circ F)=v((f\circ F)(g\circ F))=f(F(p))v(g\circ F)+v(f\circ F)g(F(p))\\&=f(F(p))d_{p}F(v)(g)+d_{p}F(v)(f)g(F(p))\end{align}$$Therefore, $d_{p}F$ is well-defined. Also, one can naturally see that $d_{p}F$ is linear.
> 2. The rank of $F$ at $p$ is defined as: $$\text{rank }d_{\varphi}$$
> 3. Let $v\in \text{T}_{p}M$ represented by $[U_{1},\varphi_{1},v_{1}]$ and $[U_{2},\varphi_{2},v_{2}]$ and let $(V_{1},\psi_{1}),(V_{2},\psi_{2})$ be two charts at $F(p)$ where $F(U_{1})\subseteq V_{1},F(U_{2})\subseteq V_{2}$. Therefore, $$\begin{align}d_{\psi_{1}(F(p))}(\psi_{2}\psi_{1}^{-1})d_{\varphi_{1}(p)}(\psi_{1} F\varphi_{1}^{-1})v_{1}&=d_{\varphi_{1}(p)}(\psi_{2}F\varphi_{1}^{-1})v_{1}\\&=d_{\varphi_{2}(p)}(\psi_{2}F\varphi_{2}^{-1})d_{\varphi_{1}(p)}(\varphi_{2}\varphi_{1}^{-1})v_{1}\\&=d_{\varphi_{2}(p)}(\psi_{2}F\varphi_{2}^{-1})v_{2}\end{align}$$This shows the well-definedness.
> 4. The rank of $F$ at $p$ is $$\text{rank }d_{\varphi(p)}(\psi F\varphi ^{-1})=\text{dim }d_{p}F(\text{T}_{p}M)$$
---
> [!lemma] Lemma 2
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and a [[Differentiable Function|smooth map]] $F:M\to N$ of constant [[rank]] $k$. Then, for $y\in F(M)$:
> 1. $F^{-1}(y)\subseteq M$ is a regular $m-k$ dimensional [[Regular Submanifold]].
> 2. for the injection $i:F^{-1}(y)\hookrightarrow M$ and $p\in F^{-1}(y)$:$$d_{p}i(\text{T}_{p}(F^{-1}(y)))=\text{ker }d_{p}F$$

> [!proof]-
> We have:
> 1. From [[Regular Submanifold|Theorem 1]].
> 2. Consider the map $F\circ i:F^{-1}(y)\to N,p\mapsto y$. Then, $d_{p}(f\circ i)=0$. Using the chain rule, $$d_{i(p)}F\circ d_{p}i=0$$In particular, $d_{p}i(\text{T}_{p}(F^{-1}(y)))\subseteq \text{ker }d_{p}F$.
>    
>    For the other inclusion, as the rank of $i$ at any $p\in F^{-1}(y)$ is $m-k$. Therefore, by Lemma 1.2, $\text{dim }d_{p}i(\text{T}_{p}(F^{-1}y))=m-k$. Then, $$\text{dim }\text{ker }d_{p}F=\text{dim }\text{T}_{p}M-\text{dim }d_{p}F(\text{T}_{p}M)=m-k$$This implies the inverse conclusion.
---
> [!lemma] Proposition 1
> Let $M,N$ be a [[smooth manifold]] and $F:N\to M$ be a [[Smooth Function|smooth map]]. Then, for a [[Vector Field]] $V\in \Gamma(TM)$, $$\begin{array}{cccc} {F_{*}V:}&{N}&\to&{TN}\\&{p} &\mapsto & {d_{p}F(V(p))} \end{array}{}$$