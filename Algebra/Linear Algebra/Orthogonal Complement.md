#Definition #Analysis 

> [!definition]
> Let $(V,\braket{ \cdot , \cdot })$ be a $\mathbb{K}$-[[Inner Product Space| inner product space]]. For any $A \subseteq V$, the ***orthogonal complement*** of $A$ is defined as:
> $$A^{\bot}:=\{ v\in V:\braket{ v , a } =0, \text{ for all }a\in A \}$$
- **Remark**: $A^{\bot}$ is a closed subspace of $V$ as $A^{\bot}=\bigcap_{a\in A}^{}\{ v\in V:\braket{ v , a }=0 \}=\bigcap_{a\in A}^{}\text{ker}\braket{ \cdot , a }$
- **Remark**: $A\cap A^{\bot}=\{ 0 \}$. If $y\in A\cap A^{\bot}$, then $\braket{ y , y }=0$, which happens if and only if $y=0$.
---
##### Properties
> [!lemma] Proposition 1
> We have the following properties:
> 1. $A \subseteq(A^{\bot})^{\bot}$
> 2. $(\overline{A})^{\bot}=A^{\bot}$ where $\overline{A}$ is the [[Interior and Closure|closure]] of $A$.
---