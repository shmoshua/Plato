#Definition #Topology 

> [!definition]
> Let $X$ be a [[Topological Space]]. A subspace $Y\subseteq X$ is called a ***retract*** of $X$, if there exists a continuous map $r:X\to Y$ s.t.
> 1. $r(y)=y$ for all $y\in Y$, i.e. $r|_{Y}=\text{id}_{Y}$.
---
##### Properties
> [!lemma] Lemma 1
> If $Y$ is a retract of $X$, the group morphism $\pi_{1}(Y,y_{0})\to \pi_{1}(X,y_{0})$ induced by $Y\to X$ is injective.

> [!proof]-
> By [[Fundamental Group|Functoriality]], $i_{*}:\pi_{1}(Y,y_{0})\to \pi_{1}(X,y_{0})$ is a group homomorphism. It is then injective by definition.
---
##### Examples
> [!h] Example 1
> We have that:
> 1. $S^{n-1}$ is a retract of $\mathbb{R}^n \backslash\{ 0 \}$
> 2. $S^{1}$ is not a retract of $\mathbb{R}^2$ by Lemma 1, as $\pi_{1}(S^1,1)\cong\mathbb{Z}$ and $\pi_{1}(\mathbb{R}^{2},1)=\{ \varepsilon_{1} \}$.

> [!proof]-
> Let us define: $$\begin{array}{cccc} {r:}&{\mathbb{R}^n\backslash\{ 0 \}}&\to&{S_{n-1}}\\&{x} &\mapsto & {x / \|x\|} \end{array}{}$$Then, for all $x\in S_{n-1}$, $\|r(x)\|=1$ and $r(x)\in S_{n-1}$. The continuity follows from that of the norm. 
---
