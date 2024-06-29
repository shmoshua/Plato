#Definition #DifferentialGeometry 
> [!definition]
> A (smooth) ***vector field*** $X$ on a [[smooth manifold]] $M$ is a (smooth) [[Vector Bundle|section]] $X:M\to \text{T}M$ of the [[tangent bundle]], i.e. for all $p\in M$, $X_{p}\in \text{T}_{p}M$.

- **Remark**: A vector field is a section of the tangent bundle and therefore, 
	1. $\Gamma(\text{T}M)$ denotes the space of all smooth vector fields.
- **Remark**: $\Gamma(\text{T}M)$ is also a $C^\infty(M)$-module, where $(fX)(p)=f(p)X_{p}$ for all $p\in M$.
- **Remark**: Let $(U,\varphi)$ be a chart of $M$ at $p\in U$. Then, any vector field $X$ can be represented as: $$X_{p}:=\sum_{i=1}^{m}X^i(p)\left.  \frac{ \partial  }{ \partial x^i } \right|_{p}  $$on $U$ with $X^i:U\to \mathbb{R}$. We also write: $X=\sum_{i=1}^{m}X^i\cdot \frac{ \partial  }{ \partial x^i }$.
- **Related definition**: Let $\varphi\in C^\infty(M,N)$. $X\in \Gamma(\text{T}M)$ and $Y\in \Gamma(\text{T}N)$ are ***$\varphi$-related*** if $d\varphi \circ X=Y\circ\varphi$ i.e. $Y_{\varphi(p)}=d_{p}\varphi(X_{p})$ for all $p\in M$.
- **Related definition**: Let $G$ be a [[Lie group]] and $M$ a smooth manifold with a smooth [[group action]] $G\times M\to M$, i.e. $L:G\to \text{Diffeo}(M)$. Then, $X\in \Gamma(\text{T}M)$ is ***$G$-invariant*** if for all $g\in G$, $(L_{g})_{*}X=X$ per Proposition 2.
---
##### Properties

> [!lemma] Proposition 1 
> Let $X$ be a vector field on $M$. Then, the following are equivalent:
> 1. $X$ is smooth.
> 2. For $(U,\varphi)$ chart at $p\in M$ with $x^1,\dots,x^m$ coordinate functions, $$X|_{U}=X^i\cdot \frac{ \partial  }{ \partial x^i } $$where $X^i\in C^\infty(U)$.
> 3. For $V\subseteq M$ open and $f\in C^\infty(V)$, $X(f)\in C^\infty(V)$.

> [!proof]-
> We have:
> 1. (1=>2): If $X$ is smooth, then $X|_{U}$ is smooth. Therefore, for any $p\in U$, $$dx^i(X_{p})=X^j(p) \left. \frac{ \partial x^i }{ \partial x^j } \right| _{p}=X^j(p)\delta_{j}^i=X^i(p) $$Hence, $dx^i\circ X|_{U}=X^i$ which is smooth.
> 2. (2=>3): Let $(U,\varphi)$ be a chart s.t. $U\subseteq V$. Then, $$X(f)|_{U}=X^i\cdot \frac{ \partial f }{ \partial x^i } $$Therefore, $X(f)|_{U}$ is a smooth function and $X(f)\in C^\infty(V)$.
> 3. (3=>1): It suffices to show that $X|_{U}$ is smooth for any chart $(U,\varphi)$ and $p\in U$,$$dx^i(X_{p})=(x^i(p),X_{p}(x^i))$$Therefore, $dx^i \circ X|_{U}=(x^i,X(x^i))$ which is smooth and $X|_{U}$ is smooth.
> 
---
![[Derivation#^5fac5a|hihi]]
![[Derivation#^c79513|p]]

---
> [!lemma] Proposition 2 (Pushforward Vector Field)
> Let $\varphi\in C^\infty(M,N)$. Then, 
> 1. $\varphi ^{*}:C^\infty(N)\to C^\infty(M),f\mapsto f\circ\varphi$ is an algebra homomorphism.
> 3. $X\in \Gamma(\text{T}M)$ and $Y\in \Gamma(\text{T}N)$ are $\varphi$-related if and only if the following diagram commutes: $$\begin{CD}C^\infty(N) @>\varphi ^{*}>>C^\infty(M)\\ @V\alpha YVV&@VV\alpha XV\\C^\infty(N) @>\varphi ^{*}>>C^\infty(M)\end{CD}$$
> 4. Let $X,Y\in \Gamma(\text{T}M)$ and $X',Y'\in \Gamma(\text{T}N)$ s.t. $X$ and $X'$ and $\varphi$-related and $Y$ and $Y'$ are $\varphi$-related. Then, $[X,Y]$ is $\varphi$-related to $[X',Y']$.
> 5. If $\varphi$ is a diffeomorphism, $\varphi ^{*}$ is an algebra isomorphism. In this case, for any $X\in \Gamma(\text{T}M)$, there exists a unique $Y\in \Gamma(\text{T}N)$ which is $\varphi$-related to $X$, characterized by: $$\alpha Y=(\varphi ^{*})^{-1}\circ \alpha X\circ \varphi ^{*}$$We denote $Y$ as $\varphi_{*}X$, the ***pushforward vector field*** of $X$.

> [!proof]-
> We have:
> 1. $\varphi ^{*}(1)=1$ and: $$\varphi ^{*}(fg)=fg\circ \varphi=(f\circ \varphi)(g\circ \varphi)=\varphi ^{*}(f)\varphi ^{*}(g)$$
> 3. if $X$ and $Y$ are $\varphi$-related, for $f\in C^\infty(N)$ and $p\in M$: $$\begin{align}\alpha X(\varphi ^{*}(f))(p)&=\alpha X(f\circ \varphi)(p)=X_{p}(f\circ \varphi)=d_{p}(f\circ \varphi)(X_{p})\\&=d_{\varphi(p)}f(d_{p}\varphi(X_{p}))=d_{\varphi(p)}f(Y_{\varphi(p)})=Y_{\varphi(p)}(f)=Y(f)(\varphi(p))=\varphi ^{*}(\alpha Y(f))(p)\end{align}$$
>    Conversely, if the diagram commutes, $$d_{p}\varphi(X_{p})(f)=X_{p}(f\circ \varphi)=\alpha X(\varphi ^{*}(f))(p)=\varphi ^{*}(\alpha Y(f))(p)=\alpha Y(f)(\varphi(p))=Y_{\varphi(p)}(f)$$
> 4. We have: $$\begin{align}\varphi ^{*}\circ  \alpha[X',Y']&=\varphi ^{*}\circ \alpha X'\circ \alpha Y'-\varphi ^{*}\circ \alpha Y'\circ \alpha X'\\&=\alpha X\circ \varphi ^{*}\circ \alpha Y'-\alpha Y\circ \varphi ^{*}\circ \alpha X'\\&=\alpha X\circ \alpha Y\circ \varphi ^{*}-\alpha Y\circ \alpha X\circ \varphi ^{*}\\&=\alpha[X,Y]\circ \varphi ^{*}\end{align}$$Therefore, they are $\varphi$-related by 2. 
> 5. If $\varphi$ is a diffeomorphism, $\varphi ^{-1}\in C^\infty(N,M)$ and $(\varphi ^{-1})^{*}:C^\infty(M)\to C^\infty(N)$ s.t. $$\varphi ^{*}\circ (\varphi ^{-1})^{*}=\text{id}_{C^\infty(M)}$$The rest is immediate by 2. 
- **Corollary**: For a diffeomorphism $\varphi\in C^\infty(M,N)$, $\varphi_{*}:\Gamma(\text{T}M)\to\Gamma(\text{T}N)$ is a Lie algebra homomorphism by 3. 
---
###### Vector Fields in Rn
> [!lemma] Proposition 1
> Let $M\subseteq \mathbb{R}^n$. Then, 
> 1. $X:M\to \mathbb{R}^3$ is a vector field along $M$. 
> 2. $X:M\to \text{T}M$ is a vector field on $M$.
> 3. $X:M\to \text{T}M\subseteq \mathbb{R}^3$ is smooth if there exists $U\supseteq M$ open s.t. $X$ extends to a smooth function $\tilde{X}:U\to \mathbb{R}^3$. 
---
##### Examples
> [!h] Example 1
> 