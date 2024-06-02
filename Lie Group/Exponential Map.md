 #Definition #Analysis #LieGroups 

> [!definition]
> 
> The ***exponential map*** of a [[Lie group]] $G$ with its [[Lie algebra]] $\mathfrak{g}$ is a map $\exp:\mathfrak{g}\to G$ s.t. $$\exp(v)=\varphi_{v}(1)$$where $\varphi_{v}:\mathbb{R}\to G$ is the [[integral curve]] of $v^L\in \Gamma(\text{T}G)$ going through $e$, i.e. $\varphi_{v}(0)=e$.
---
##### Properties

> [!lemma] Lemma 1
> We have that:
> 1. for all $v\in \mathfrak{g}$ and $t\in \mathbb{R}$, $\exp(tv)=\varphi_{v}(t)$.
> 2. if $v,w\in \mathfrak{g}$ with $[v,w]=0$, then $\exp(v+w)=\exp(v)\exp(w)$.

> [!proof]-
> We have:
> 1. By defining $\psi(s):=\varphi_{v}(ts)$, we have that $\psi:\mathbb{R}\to G$ is a smooth homomorphism with $\psi'(0)=t\cdot\varphi'_{v}(0)=tv$. Therefore, $$\exp(tv)=\varphi_{tv}(1)=\psi(1)=\varphi_{v}(t)$$
> 2. Assume $[v,w]=0$. Then by [[Flow|Proposition 3]], $\Phi_{v^L}^s$ and $\Phi_{w^L}^t$ commute for all $s,t\in \mathbb{R}$. Then, by [[Integral Curve|Example 1]], $$\varphi_{w}(t)\varphi_{v}(s)=\varphi_{v}(s)\varphi_{w}(t),\quad \forall s,t\in \mathbb{R}$$We claim that $\psi(t):=\varphi_{v}(t)\varphi_{w}(t)$ is a one-parameter subgroup: it is smooth and: $$\begin{align}\psi(s+t)&=\varphi_{v}(s+t)\varphi_{w}(s+t)\\&=\varphi_{v}(s)\varphi_{v}(t)\varphi_{w}(s)\varphi_{w}(t)\\&=\varphi_{v}(s)\varphi_{w}(s)\varphi_{v}(t)\varphi_{w}(t)\\&=\psi(s)\psi(t)\end{align}$$with $$\begin{align}\psi'(0)&=d_{(e,e)}m(\varphi'_{v}(0),\varphi'_{w}(0))\\&=d_{(e,e)}m(v,w)\\&=d_{(e,e)}m(v,0)+d_{(e,e)}m(0,w)\end{align}$$where for $d_{(e,e)}m(v,0)=d_{(e,e)}m(d_{e}i(v))=d_{e}(m\circ i)(v)=d_{e}\text{id}(v)=v$. This proves that $\psi'(0)=v+w$. Hence, $$\exp(v+w)=\varphi_{v+w}(1)=\psi(1)=\varphi_{v}(1)\varphi_{w}(1)=\exp(v)\exp(w)$$
---
> [!lemma] Proposition 2
> Let $G,H$ be [[Lie Group|Lie groups]] and $\varphi:G\to H$ a Lie group homomorphism. Then, the diagram: $$\begin{CD}G@>\varphi>>H\\@A\exp AA@AA\exp A\\\mathfrak{g}@>>d_{e}\varphi>\mathfrak{h}\end{CD}$$commutes, i.e. $\varphi \circ\exp=\exp \circ\  d_{e}\varphi$. Further, 
> 1. $d_{0}\exp=\text{id}_{\mathfrak{g}}$
> 2. there exists $0\in U\subseteq \mathfrak{g}$ open s.t. $\exp(U)\subseteq G$ is open and $\exp:U\to \exp(U)$ is a diffeomorphism.

> [!proof]-
> We have:
> 1. Let $v\in \mathfrak{g}$ and consider $\psi(t):=\varphi(\exp(tv))$. Then, $$\psi(s+t)=\varphi(\exp((s+t)v))=\varphi(\exp(sv)\exp(tv))=\psi(s)\psi(t)$$with $\psi'(0)=d_{e}\varphi(v)$. Therefore, $$\varphi(\exp(v))=\psi(1)=\varphi_{d_{e}\varphi(v)}(1)=\exp(d_{e}\varphi(v))$$
> 2. For any $v\in \mathfrak{g}$, $$d_{0}\exp(v)=\left. \frac{d}{dt} \right| _{t=0}\exp(tv)=\left. \frac{d}{dt} \right| _{t=0}\varphi_{v}(t)=\varphi'_{v}(0)=v$$
> 3. [[Smooth Function|Inverse Function Theorem]] on $\exp$.
---
> [!lemma] Theorem (Cartan)
> If $G$ is a compact and [[Connected Space|connected]] [[Lie group]], $\exp:\mathfrak{g}\to G$ is surjective.

> [!proof] Proof (Missing)
---
> [!lemma] Proposition 4
> Let $G$ be a connected abelian Lie group. Then,
> 1. $\exp$ is a surjective smooth homomorphism.
> 2. $\text{ker}\exp\leq \mathfrak{g}$ is a discrete subgroup.
> 3. $\exp$ induces a Lie group homomorphism $\mathfrak{g} /\text{ker}\exp\cong G$.

> [!proof]+
> Assume that 
---
##### Examples
> [!h] Example 1 (Matrix Groups)
> For $\text{GL}(n,\mathbb{R})$ and $t\in \mathbb{R}$ and $A\in \text{Mat}_{n,n}(\mathbb{R})=\mathfrak{gl}(n,\mathbb{R})$, we have: $$\exp(tA)=\sum_{n=0}^{\infty} \frac{A^nt^n}{n!}$$Then, it also holds that:
> 1. the power series $\exp(A)$ converges uniformly on balls of finite radius in $\text{Mat}_{n,n}(\mathbb{R})$ to a smooth map.
> 2. if $[A,B]=0$, $\exp(A+B)=\exp(A)\exp(B)$ and $\exp(A)\in \text{GL}(n,\mathbb{R})$.
> 3. for any $A\in \text{Mat}_{n,n}(\mathbb{R})$, $$\varphi_{A}:\mathbb{R}\to \text{GL}(n,\mathbb{R}),\quad t\mapsto \exp(tA)$$is a smooth homomorphism with $\varphi_{A}'(0)=A$. 
> 4. any smooth homomorphism $\psi:\mathbb{R}\to \text{GL}(n,\mathbb{R})$ is of the form $\psi(t)=\exp(t\psi'(0))$.

> [!proof]-
> 
> We have:
> 1. Let $r>0$ and for all $A\in \text{Mat}_{n,n}(\mathbb{R})$ with $\|A\|\leq r$ and $N\geq 1$, we have: $$\left\| \sum_{n=0}^{N} \frac{A^n}{n!} \right\| \leq \sum_{n=0}^{N}\frac{\|A\|^n}{n!}\leq\exp(\|A\|)\leq \exp(r)$$Therefore, $\exp(A)$ converges uniformly on $B_{\leq r}(0)$.
>    
>    For partial derivatives, we have:$$\frac{ \partial  }{ \partial x_{ij} } X^n=\sum_{k_{1}+k_{2}=n-1}^{}X^{k_{1}}E_{ij}X^{k_{2}}$$Therefore, $\left\| \frac{ \partial  }{ \partial x_{ij} }X^n \right\|\leq n\|X^{n-1}\|$. Now, for any partial derivation of order $k$, $$\left\| \frac{ \partial^\alpha }{ \partial x_{\alpha}}X^n  \right\|\leq n(n-1)\dots(n-k+1)\left\| X^{n-k} \right\|  $$for $n\geq k$. This shows that $\sum_{n=0}^{\infty}\frac{ \partial^\alpha }{ \partial x_{\alpha} }\frac{X^n}{n!}$ converges uniformly on balls of finite radius. This shows that $\exp$ is smooth.
> 2. if $AB=BA$ then: $$(A+B)^n=\sum_{k=0}^{n} {n \choose k}A^k B^{n-k}$$Therefore, $$\exp(A+B)=\sum_{n=0}^{\infty}(A+B)^n / n! =\sum_{n=0}^{\infty}\sum_{k=0}^{n}\frac{A^kB^{n-k}}{k!(n-k)!}=\sum_{k=0}^{\infty}\frac{A^k}{k!}\sum_{n=k}^{\infty}\frac{B^{n-k}}{(n-k)!}=\exp(A)\exp(B)$$Further, $I=\exp(0)=\exp(A-A)=\exp(A)\exp(-A)$ and $\exp(A)\in \text{GL}(n,\mathbb{R})$.
> 3. For $t,s\in \mathbb{R}$, $[tA,sA]=0$. Therefore, $$\exp(tA+sA)=\exp(tA)\exp(sA)$$and $\varphi$ is a homomorphism. Furthermore, $\varphi_{A}$ is smooth as $\exp$ is smooth. Lastly, $$\varphi'_{A}(0)=\left. \frac{d}{dt} \right| _{t=0}\exp(tA)=\left. \frac{d}{dt} \right| _{t=0}\sum_{n=0}^{\infty} \frac{A^nt^n}{n!}=\sum_{n=0}^{\infty}\frac{A^{n+1}0^{n}}{n!}=A$$
> 4. Let $\psi:\mathbb{R}\to \text{GL}(n,\mathbb{R})$. Then, $$\psi'(t)=\left. \frac{d}{ds} \right| _{s=0}\psi(t+s)=\psi(t) \left. \frac{d}{ds} \right| _{s=0}\psi(s)=\psi(t)\psi'(0)$$By uniqueness of the solution of ODEs, $\psi(t)=C\cdot \exp(t\cdot \psi'(0))$. As $\psi(0)=I$, $C=1$. 
> 5. As $\varphi_{A}$ is a smooth homomorphism with $\varphi'_{A}(0)=A$, we have that by uniqueness, $$\exp(tA)=\varphi_{A}(t)=\sum_{n=0}^{\infty}\frac{A^nt^n}{n!}$$
---
> [!h] Example 2
> For matrix groups,
> 1. For $n\geq 1$, $\exp:\mathfrak{u}(n)\to \text{U}(n)$ is surjective.
> 2. For $n\geq 1$, $\exp:\mathfrak{sl}(n,\mathbb{R})\to \text{SL}(n,\mathbb{R})$ is not surjective.

> [!proof]-
> We have:
> 1. Let $X$ be a unitary matrix. Then, $X=PDP^{*}$ where $P$ is unitary and $D$ diagonal. Let $D=\text{diag}(\lambda_{1},\dots,\lambda_{n})$. We have that $\left| \lambda_{i} \right|=1$, i.e. hence, there exists $x_{i}\in \mathbb{R}$ s.t. $\exp(ix_{i})=\lambda_{i}$. Hence, let $Y:=i\cdot\text{diag}(x_{1},..,x_{n})$ and:$$\exp(PYP^{*})=\sum_{n=0}^{\infty}\frac{(PYP^{*})^n}{n!}=\sum_{n=0}^{\infty}\frac{PY^nP^{*}}{n!}=P\exp(Y)P^{*}=P\text{diag}(\lambda_{1},\dots,\lambda_{n})P^{*}=X$$We only need to show that $PYP^{*}\in\mathfrak{u}(n)$. We have that: $$PYP^{*}+PY^{*}P^{*}=P(Y+Y^{*})P^{*}=0$$
> 2. We show it concretely for $n=2$. Suppose that $X\in \mathfrak{sl}(2,\mathbb{R})$ with $\exp(X)=\begin{bmatrix}-1&1\\0&-1\end{bmatrix}$. As $\exp(X)$ is not diagonalizable, $X$ is not diagonalizable and has a double root. However as $X$ has trace 0, it has eigenvalue 0. This means then $1$ is an eigenvalue of $\exp(X)$, which is not true.
---