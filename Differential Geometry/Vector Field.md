#Definition #DifferentialGeometry 
> [!definition]
> A (smooth) ***vector field*** $X$ on a [[smooth manifold]] $M$ is a (smooth) [[Vector Bundle|section]] $X:M\to \text{T}M$ of the [[tangent bundle]], i.e. for all $p\in M$, $X_{p}\in \text{T}_{p}M$.

- **Remark**: A vector field is a section of the tangent bundle and therefore, 
	1. $\Gamma(\text{T}M)$ denotes the space of all smooth vector fields.
- **Remark**: $\Gamma(\text{T}M)$ is also a $C^\infty(M)$-module, where $(fX)(p)=f(p)X_{p}$ for all $p\in M$.
- **Related definition**: The local derivation property of a tangent vector can be extended globally: There is an isomorphism between $\Gamma(\text{T}M)\cong \text{Der }C^\infty(M)$ with $X\mapsto (f\mapsto Xf)$ where:$$\begin{array}{cccc} {X(f):}&{M}&\to&{\mathbb{R}}\\&{p} &\mapsto & {X_{p}(f)=d_{p}f(X_{p})} \end{array}{}$$

- **Remark**: Let $(U,\varphi)$ be a chart of $M$ at $p\in U$. Then, by [[Tangent Space|this]], $\left\{  \frac{ \partial  }{ \partial x^j }  \right\}_{j\in[m]}$ forms a basis of $\text{T}_{p}M$ and any vector field $X$ can be represented as: $$X_{p}:=\sum_{i=1}^{m}X^i(p)\left.  \frac{ \partial  }{ \partial x^i } \right|_{p}  $$on $U$ with $X^i:U\to \mathbb{R}$.
- **Related definition**: Let $\varphi\in C^\infty(M,N)$. $X\in \Gamma(\text{T}M)$ and $Y\in \Gamma(\text{T}N)$ are ***$\varphi$-related*** if $d\varphi \circ X=Y\circ\varphi$i.e. $Y_{\varphi(p)}=d_{p}\varphi(X_{p})$ for all $p\in M$.
---
##### Properties

> [!lemma] Proposition 1 
> Let $X$ be a vector field on $M$. Then, the following are equivalent:
> 1. $X$ is smooth.
> 2. For $(U,\varphi)$ chart at $p\in M$ with $x^1,\dots,x^m$ coordinate functions, $$X|_{U}=X^i\cdot \frac{ \partial  }{ \partial x^i } $$where $X^i\in C^\infty(U)$.
> 3. For $V\subseteq M$ open and $f\in C^\infty(V)$, $X(f)\in C^\infty(V)$

> [!proof]-
> We have:
> 1. (1=>2): If $X$ is smooth, then $X|_{U}$ is smooth. Therefore, for any $p\in U$, $$dx^i(X_{p})=X^j(p) \left. \frac{ \partial x^i }{ \partial x^j } \right| _{p}=X^j(p)\delta_{j}^i=X^i(p) $$Hence, $dx^i\circ X|_{U}=X^i$ which is smooth.
> 2. (2=>3): Let $(U,\varphi)$ be a chart s.t. $U\subseteq V$. Then, $$X(f)|_{U}=X^i\cdot \frac{ \partial f }{ \partial x^i } $$Therefore, $X(f)|_{U}$ is a smooth function and $X(f)\in C^\infty(V)$.
> 3. (3=>1): It suffices to show that $X|_{U}$ is smooth for any chart $(U,\varphi)$ and $p\in U$,$$d\varphi(X_{p})=(x,X_{p}(x^i))$$Therefore, $d\varphi \circ X|_{U}=(\varphi,X(x^i))$ which is smooth and $X|_{U}$ is smooth.
> 
---
![[Derivation#^5fac5a|hihi]]
![[Derivation#^c79513|p]]

---
> [!lemma] Proposition 2
> Let $\varphi\in C^\infty(M,N)$. Then, 
> 1. $\varphi ^{*}:C^\infty(N)\to C^\infty(M),f\mapsto f\circ\varphi$ is an algebra homomorphism.
> 2. $X\in \Gamma(\text{T}M)$ and $Y\in \Gamma(\text{T}N)$ are $\varphi$-related if and only if the following diagram commutes: $$\begin{CD}C^\infty(N) @>\varphi ^{*}>>C^\infty(M)\\ @V\alpha YVV&@VV\alpha XV\\C^\infty(N) @>\varphi ^{*}>>C^\infty(M)\end{CD}$$

> [!proof]-
> We have:
> 1. $\varphi ^{*}(1)=1$ and: $$\varphi ^{*}(fg)=fg\circ \varphi=(f\circ \varphi)(g\circ \varphi)=\varphi ^{*}(f)\varphi ^{*}(g)$$
> 2. if $X$ and $Y$ are $\varphi$-related, for $f\in C^\infty(N)$ and $p\in M$: $$\begin{align}\alpha X(\varphi ^{*}(f))(p)&=\alpha X(f\circ \varphi)(p)=X_{p}(f\circ \varphi)=d_{p}(f\circ \varphi)(X_{p})\\&=d_{\varphi(p)}f(d_{p}\varphi(X_{p}))=d_{\varphi(p)}f(Y_{\varphi(p)})=Y_{\varphi(p)}(f)=Y(f)(\varphi(p))=\varphi ^{*}(\alpha Y(f))(p)\end{align}$$
>    Conversely, if the diagram commutes, $$d_{p}\varphi(X_{p})(f)=X_{p}(f\circ \varphi)=\alpha X(\varphi ^{*}(f))(p)=\varphi ^{*}(\alpha Y(f))(p)=\alpha Y(f)(\varphi(p))=Y_{\varphi(p)}(f)$$

---
##### Examples
> [!h] Example 1
> 