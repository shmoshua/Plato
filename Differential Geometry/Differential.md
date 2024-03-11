#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $F:M\to N$ be a [[differentiable function|smooth function]]. Then, the ***differential*** is defined as follows: for a chart $(U,\varphi)$ at $p$ and $(V,\psi)$ at $F(p)$ s.t. $F(U)\subseteq V$: $$\begin{array}{cccc} {d_{p}F:}&{\text{T}_{p}M}&\to&{\text{T}_{F(p)}N}\\&{[U,\varphi,v]_{p}} &\mapsto & {[V,\psi,d_{\varphi(p)}(\psi F\varphi ^{-1})v]_{F(p)}} \end{array}{}$$
- **Remark**: given $f\in C^\infty(M)$, the differential at $p$ is defined as $$\begin{array}{cccc} {d_{p}f:}&{T_{p}M}&\to&{\mathbb{R}}\\&{[x,e_{i}]_{p}} &\mapsto & {[x,e_{i}]_{p}f} \end{array}{}$$
- **Related definition**: $F$ is an ***immersion***, if $d_{p}F$ is injective for all $p\in M$.
---
##### Properties
> [!lemma] Lemma 1
> Let $M,N,R$ be [[Smooth Manifold|smooth manifolds]] and [[Differentiable Function|smooth maps]] 
> 1. $d_{p}F$ is well-defined.
> 2. the [[rank]] of $F$ at $p$ is $\text{dim }d_{p}F(\text{T}_{p}M)$.
> 3. $d_{p}(G\circ F)=d_{F(p)}(G)d_{p}(F)$

> [!proof]-
> We have:
> 1. Let $v\in \text{T}_{p}M$ represented by $[U_{1},\varphi_{1},v_{1}]$ and $[U_{2},\varphi_{2},v_{2}]$ and let $(V_{1},\psi_{1}),(V_{2},\psi_{2})$ be two charts at $F(p)$ where $F(U_{1})\subseteq V_{1},F(U_{2})\subseteq V_{2}$. Therefore, $$\begin{align}d_{\psi_{1}(F(p))}(\psi_{2}\psi_{1}^{-1})d_{\varphi_{1}(p)}(\psi_{1} F\varphi_{1}^{-1})v_{1}&=d_{\varphi_{1}(p)}(\psi_{2}F\varphi_{1}^{-1})v_{1}\\&=d_{\varphi_{2}(p)}(\psi_{2}F\varphi_{2}^{-1})d_{\varphi_{1}(p)}(\varphi_{2}\varphi_{1}^{-1})v_{1}\\&=d_{\varphi_{2}(p)}(\psi_{2}F\varphi_{2}^{-1})v_{2}\end{align}$$This shows the well-definedness.
> 2. The rank of $F$ at $p$ is $$\text{rank }d_{\varphi(p)}(\psi F\varphi ^{-1})=\text{dim }d_{p}F(\text{T}_{p}M)$$
---
> [!lemma] Lemma 2
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and a [[Differentiable Function|smooth map]] $F:M\to N$ of constant [[rank]] $k$. Then, for $y\in F(M)$:
> 1. $F^{-1}(y)\subseteq M$ is a regular $m-k$ dimensional [[submanifold]].
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