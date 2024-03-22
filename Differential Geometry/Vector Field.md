#Definition #DifferentialGeometry 
> [!definition]
> A (smooth) ***vector field*** $X$ on a [[smooth manifold]] $M$ is a (smooth) [[Vector Bundle|section]] $X:M\to \text{T}M$ of the [[tangent bundle]], i.e. for all $p\in M$, $X(p)\in \{ p \}\times\text{T}_{p}M$.


- **Remark**: A vector field is a section of the tangent bundle and therefore, 
	1. $\Gamma(\text{T}M)$ denotes the space of all smooth vector fields.
- **Remark**: $\Gamma(\text{T}M)$ is also a $C^\infty(M)$-module, where $(fX)(x)=f(x)X(x)$ for all $x\in M$.
- **Related definition**: The local derivation property of a tangent vector can be extended globally: There is an isomorphism between $\Gamma(\text{T}M)\cong \text{Der }C^\infty(M)$ with $X\mapsto (f\mapsto Xf)$ where:$$\begin{array}{cccc} {Xf:}&{M}&\to&{\mathbb{R}}\\&{p} &\mapsto & {X_{p}f=d_{p}f(X_{p})} \end{array}{}$$

- **Remark**: We can express vector fields in local coordinates. Let $(U,\varphi)$ be a chart of $M$ at $p\in U$. We define: $$\begin{array}{cccc} {\partial_{j}(p):}&{C^\infty(M)}&\to&{\mathbb{R}}\\&{} &\mapsto & {} \end{array}{}$$
- For $f\in C^\infty(M)$, we define: $$\partial_{j}(p)(f):=\frac{ \partial (f\circ \varphi ^{-1}) }{ \partial x^j } (\varphi(p))$$ 
---
##### Properties
> [!lemma] Lemma 1
> A vector field $X$ 
---
##### Examples
> [!h] Example 1
> 