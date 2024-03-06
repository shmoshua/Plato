#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. The ***tangent bundle*** $\text{T}M$ of $M$ is defined as: $$\text{T}M:=\bigcup_{p\in M}^{}\{ p \}\times \text{T}_{p}M=\{ (p,v) :p\in M,v\in \text{T}_{p}M\}$$
- **Remark**: $\text{T}M$ has a natural projection $\pi:\text{T}M\to M, (p,v)\mapsto p$.
- **Related definition**: For every $U\subseteq M$, $\text{T}U:=\pi ^{-1}(U)$
- **Remark**: For any chart $(U,\varphi)$, the function: $$\begin{array}{cccc} {d\varphi:}&{\text{T}U}&\to&{\varphi(U)\times \mathbb{R}^m}\\&{(p,v)} &\mapsto & {(\varphi(p),d_{p}\varphi (v))} \end{array}{}$$is a bijection.
---
##### Properties
> [!lemma] Lemma 1
> $\text{T}M$ is equipped with the following topology: $E\subseteq \text{T}M$ is open if and only if for every chart $(U,\varphi)$, $d\varphi(E\cap \text{T}U)\subseteq\varphi(U)\times \mathbb{R}^m$ is open. Then, 
> 1. The above topology is well-defined.
> 2. For a chart $(U,\varphi)$, $d\varphi$ is a [[homeomorphism]].
> 3. $\text{T}M$ is a second countable [[Hausdorff space]].
> 5. $\pi:\text{T}M\to M$ is continuous and open.

> [!proof]+
> We have that:
> 1. For a chart $(U,\varphi)$, $\text{T}U\subseteq \text{T}M$ is open. Therefore, $\text{T}M\cap \text{T}U=\text{T}U$ and $\text{T}M$ is open as well. Further, for $E_{1},E_{2}$ open, $$(E_{1}\cap E_{2})\cap \text{T}U=(E_{1}\cap \text{T}U)\cup(E_{2}\cap \text{T}U)$$$E_{1}\cap E_{2}$ is open. Similarly, for $(E_{\alpha})_{\alpha\in A}$ open in $\text{T}M$, $$\bigcup_{\alpha\in A}^{}E_{\alpha}\cap \text{T}U=\bigcup_{\alpha\in A}^{}(E_{\alpha}\cap \text{T}U)$$ and $\bigcup_{\alpha\in A}^{}E_{\alpha}$ is open.
> 2. By definition.
> 3. Let $(p_{1},v_{1})\neq(p_{2},v_{2})$. If $p_{1}\neq p_{2}$, then choose charts $(U_{1},\varphi_{1}),(U_{2},\varphi_{2})$ at $p_{1},p_{2}$ respectively s.t. $$