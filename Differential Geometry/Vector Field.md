#Definition #DifferentialGeometry 
> [!definition]
> A (smooth) ***vector field*** $X$ on a [[smooth manifold]] $M$ is a (smooth) [[Vector Bundle|section]] $X:M\to \text{T}M$ of the [[tangent bundle]], i.e. for all $p\in M$, $X(p)\in \{ p \}\times\text{T}_{p}M$.


- **Remark**: A vector field is a section of the tangent bundle and therefore, 
	1. $\Gamma(\text{T}M)$ denotes the space of all smooth vector fields.
- **Remark**: $\Gamma(\text{T}M)$ is also a $C^\infty(M)$-module, where $(fX)(x)=f(x)X(x)$ for all $x\in M$.
- **Related definition**: The local derivation property of a tangent vector can be extended globally: There is an isomorphism between $\Gamma(\text{T}M)\cong \text{Der }C^\infty(M)$ with $X\mapsto (f\mapsto Xf)$ where:$$\begin{array}{cccc} {Xf:}&{M}&\to&{\mathbb{R}}\\&{p} &\mapsto & {X_{p}f=d_{p}f(X_{p})} \end{array}{}$$

- **Remark**: Let $(U,\varphi)$ be a chart of $M$ at $p\in U$. Then, by [[Tangent Space|this]], $\left\{  \frac{ \partial  }{ \partial x^j }  \right\}_{j\in[m]}$ forms a basis of $\text{Der}_{p}C^\infty(M)\cong \text{T}_{p}M$ and any vector field $X$ can be represented as: $$X_{p}:=\sum_{i=1}^{m}X^i(p)\left.  \frac{ \partial  }{ \partial x^i } \right|_{p}  $$on $U$ with $X^i:U\to \mathbb{R}$
---
##### Properties
> [!lemma] Lemma 1
> A vector field $X$ is smooth if and only if for every chart, the local expression $X^i$ is smooth.

> [!proof]+
> Assume $X$ is smooth. Let $(U,\varphi),(V,\psi)$ be a chart on $M$ with $U\subseteq V$. Then, $d\psi \circ X\circ\varphi ^{-1}\in C^\infty$. Then, for any $a\in \varphi(U)$, let $p:=\varphi ^{-1}(a)$ s.t. $$\begin{align}(d\psi \circ X\circ \varphi ^{-1})(a)&=d\psi (X_{p})=\end{align}$$
> 
---
##### Examples
> [!h] Example 1
> 