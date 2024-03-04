#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a commutative [[Banach algebra]] and $\hat{A}$ the [[Guelfand spectrum]] of $A$. The ***Guelfand topology*** is a topology on $\hat{A}\subseteq A^{*}$ induced by the [[Weak Topology|weak*-topology]] on $A^{*}$.
---
##### Properties
> [!lemma] Theorem 1
> Let $A$ be a commutative [[Banach algebra]]. Then, we have: 
> 1. $\hat{A}$ is locally compact Hausdorff w.r.t. Guelfand topology.
> 2. If $A$ is unital, $\hat{A}$ is compact.
> 3. $\widehat{A_{I}}$ is the [[one-point compactification]] of $\hat{A}$.

> [!proof]+
> Consider the map: $$\begin{array}{cccc} {p:}&{A_{I}:=A\times \mathbb{C}}&\to&{A}\\&{(x,\lambda)} &\mapsto & {x} \end{array}{}$$Then, 
> 1. $\left\| p \right\|=1$ and 
> 2. $p^{*}:A^{*}\to(A_{I})^{*}$ is weak*-continuous and injective, by [[Weak Topology|Proposition 3]].
> 
> Therefore, $$p^{*}(B_{\leq 1}^{A^{*}}(0))=\{ \varphi\in B_{\leq 1}^{(A_{I})^{*}}(0):\varphi((0,1))=0 \}$$By [[Weak Topology|Banach Alagolu]], $B_{\leq 1}^{A^{*}}(0)$ and $B_{\leq 1}^{(A_{I})^{*}}(0)$ are weak*-compact.
