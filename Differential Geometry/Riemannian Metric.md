#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. A ***Riemannian metric*** $g$ on $M$ is a smooth family of [[Inner Product Space|inner products]] on the [[Tangent Space|tangent spaces]] of $M$. Namely, 
> 1. $g$ associates to each $p\in M$ a symmetric positive definite bilinear form $g_{p}:\text{T}_{p}M\times \text{T}_{p}M\to \mathbb{R}$ 
> 2. for all [[Vector Field|smooth vector fields]] $X,Y\in \Gamma(\text{T}M)$, $$\begin{array}{cccc} &{M}&\to&{\mathbb{R}}\\&{p} &\mapsto & {g_{p}(X_{p},Y_{p})} \end{array}{}$$is smooth.
- **Equivalent definition**: A smooth section $g\in \Gamma(\text{T}_{(0,2)}M)=\Gamma(\text{T}^{*}M\otimes \text{T}^{*}M)$ is a Riemannian metric if and only if $g_{p}$ is symmetric and positive definite for all $p\in M$.
- **Related definition**: For a chart $(U,\varphi)$, $$g_{ij}(p):=g_{p}\left( \left. \frac{ \partial  }{ \partial x^i }   \right|_{p},\left. \frac{ \partial  }{ \partial x^j }   \right|_{p} \right) $$are called ***metric coefficients***. Then, they're:
	1. **symmetric**: $g_{ij}=g_{ji}$.
	2. **positive definite**: $\sum_{i,j=1}^{m}g_{ij}v^iv^j=g(v,v)\geq 0$ where $v=\sum_{i=1}^{m}v^i \left. \frac{ \partial  }{ \partial x^i } \right|_{p}$ with equality if and only if $v=0$.
	3. **smoothness**: $g_{ij}(p)$ is smooth in $p$.
- **Remark**: One can also write the Riemannian metric from the metric coefficients as follows: $$g_{p}:=\sum_{i,j=1}^{m}g_{ij}(p)\cdot d_{p}x^i \otimes  d_{p}x^j$$where $\xi \otimes \eta:T_{p}M\times T_{p}M\to \mathbb{R}, (v,w)\mapsto \xi(v)\eta(w)$ for $\xi,\eta\in T^{*}_{p}M$ is a bilinear form on $T_{p}M$.
- **Remark**: We define the following notations:
	1. $d_{p}x^id_{p}x^j:= \frac{1}{2}\left(  d_{p}x^i \otimes  d_{p}x^j+d_{p}x^j \otimes  d_{p}x^i \right)$
	2. $g=g_{ij}dx^idx^j$
---
##### Properties
> [!lemma] Proposition 1
> Every [[smooth manifold]] $M$ admits a Riemannian metric.

> [!proof]-
> Let $\{ (U_{\alpha},x_{\alpha}) \}_{\alpha\in A}$ be the atlas. For each $\alpha\in A$, consider the Riemannian metric $g_{\alpha}$ on $U_{\alpha}$ where $$(g_{\alpha})_{ij}=\delta_{ij}$$Let $\{ \rho_{\alpha} \}$ be a smooth partition of unity of $M$ subordinate to the covering $\{ U_{\alpha} \}$, and define: $$g=\sum_{\alpha\in A}^{}\rho_{\alpha}g_{\alpha}$$Since the family of supports of the $\rho_{\alpha}$ is locally finite, the above sum is locally finite, and hence $g$ is well defined and smooth, and it is bilinear and symmetric at each point. Since $\rho_{\alpha}\geq 0$ for all $\alpha$ and $\sum_{\alpha}^{}\rho_{\alpha}=1$, it also follows that $g$ is positive definite, and thus is a Riemannian metric in $M$.
---
> [!lemma] Lemma 2
> A Riemannian metric $g$ on $M$ defines an element of $\Gamma(T_{(0,2)}M)=\Gamma(T^{*}M\otimes T^{*}M)$. 
> Conversely, every $g\in \Gamma(T_{(0,2)}M)$ s.t. $$g_{p}\in (T_{(0,2)}M)_{p}=T^{*}_{p}M\otimes T^{*}_{p}M$$is a symmetric, positive definite bilinear form on $T_{p}M$. (smoothness in $p$ is encoded in $\Gamma(T_{(0,2)}M)$).
> 
> Further, $\{ d_{p}\varphi^i\otimes d_{p}\varphi^j ,1\leq i,j\leq m\}$ forms a basis of $T^{*}_{p}M\otimes T^{*}_{p}M$.
---
> [!lemma] Lemma 3
> Let $(U,\varphi)$ and $(V,\psi)$ be two charts on $(M,g)$ with coordinates $(x^i)_{i}$, $(y^j)_{j}$ and we have $p=\alpha(q)$ for $\alpha:\psi (U\cap V)\to \varphi(U\cap V)$. Then, on $U\cap V$, 
> 1. $g=h_{ij}dy^i\otimes dy^j$ where $[h_{ij}(y)]=\left[ \frac{ \partial \alpha }{ \partial y } \right]^\top [g_{ij}]\left[ \frac{ \partial \alpha }{ \partial y } \right]$ and $g=g_{ij}dx^i\otimes dx^j$.

> [!proof]+
> Let $g=g_{ij}dx^i\otimes dx^j$. Then, let $g=h_{ij}dy^i\otimes dy^j$ where: $$\begin{align}(\alpha ^{*}g)_{q}\left( \left. \frac{ \partial  }{ \partial y^i }  \right|_{q},\left. \frac{ \partial  }{ \partial y^j }  \right|_{q}  \right) =g_{\alpha(q)}\left( d \right) \end{align}$$
> 
> $$(\alpha ^{*}g)_{y}\left( \frac{ \partial  }{ \partial y^i } ,\frac{ \partial  }{ \partial y^j }  \right)=g_{\alpha(y)}\left( d_{y}\alpha\left( \frac{ \partial  }{ \partial y^i }  \right) ,d_{y}\alpha\left( \frac{ \partial  }{ \partial y^j }  \right) \right)=g_{\alpha(y)}\frac{ \partial \alpha }{ \partial x }  $$
---
##### Examples
> [!h] Example 1
> Let $M=\mathbb{R}^m$ and $(x^1,\dots,x^m)$ be standard coordinates. Then, $$g:=\sum_{i=1}^{m}dx^i\otimes dx^i=\sum_{i=1}^{m}(dx^i)^{2}$$is the Euclidean metric. 
---
> [!h] Example 2
> Let $M=(0,\infty)\times(0,2\pi)$ with coordinates $r,\theta$. Then, $$g=dr^{2}+r^{2}d\theta^{2}$$is the Euclidean metric in polar coordinates.

> [!proof]-
> As $x=r\cos \theta$ and $y=r\sin\theta$, $$\begin{align}g&=(dx)^{2}+(dy)^{2}\\&=(\cos ^{2} \theta (dr)^{2}+r^{2}\sin ^{2} \theta (d\theta)^{2}-2r\cos\theta \sin\theta dr d\theta)+(\sin ^{2}\theta(dr)^{2}+r^{2}\cos ^{2}\theta(d\theta)^{2}+2r\sin\theta \cos\theta dr d\theta)\\&=dr^{2}+r^{2}d\theta^{2}\end{align}$$
---
> [!h] Example 3 (Pullback)
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $f:M\to N$ a smooth map. 
> 1. For a Riemannian metric $h$ on $N$, $$f^{*}(h)_{p}(u,v):=h_{f(p)}(d_{p}f (u),d_{p}f(v))$$for $p\in M$ and $u,v\in \text{T}_{p}M$ defines the ***pullback metric*** on $M$.
> 2. Additionally, if $f$ is an immersion, $f^{*}(h)$ is a Riemannian metric.

> [!proof]-
> Firstly, as $d_{p}f$ is linear and $h_{f(p)}$ is bilinear, $f^{*}(h)_{p}$ is bilinear. Further, from the symmetry of $h_{f(p)}$, $f^{*}(h)_{p}$ is symmetric.
> 
> For the positive definiteness, if $f$ is an immersion, $d_{p}f$ is injective and for every non-zero $v\in \text{T}_{p}M$, $d_{p}f(v)\neq 0$ and $$(f^{*}h)_{p}(v,v)=h_{f(p)}(d_{p}f(v),d_{p}f(v))>0$$
> The smoothness follows from the assumption.
---
> [!h] Example 4 (Musical Notation)
> Let $(M,g)$ be a [[Riemannian manifold]]. For $p\in M$, we have a positive definite symmetric bilinear form $g_{p}^{-1}:\text{T}_{p}^{*}M\times \text{T}^{*}_{p}M\to \mathbb{R}$ defined as: $$g^{-1}_{p}(\xi,\eta):=g_{p}(\xi^\sharp,\eta^\sharp)$$Then, $$g_{p}^{-1}((dx^i)_{p},(dx^j)_{p})=g_{p}\left( g^{ik}(p)\left. \frac{ \partial  }{ \partial x^k }   \right|_{p},g^{j\ell}(p)\left. \frac{ \partial  }{ \partial x^\ell }  \right|_{p}  \right)=(g^{ik}g_{k\ell}g^{j\ell})(p)=(g^{-1}g g^{-1})_{ij}(p)=g^{ij}(p)$$and $$g^{-1}_{p}=g^{ij}(p) \left. \frac{ \partial  }{ \partial x^i } \right| _{p}\otimes \left. \frac{ \partial  }{ \partial x^j } \right| _{p} $$
---