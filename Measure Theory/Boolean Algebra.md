#Definition #MeasureTheory 

> [!definition]
> Let $\varnothing \neq \mathcal{A} \subseteq \mathcal{P}(X)$. $\mathcal{A}$ is called a:
> 1.  a ***Boolean ring*** in $X$, if:
> 	1. $\varnothing \in \mathcal{A}$
> 	2. $A\cup B\in \mathcal{A}$ for all $A,B\in \mathcal{A}$.
> 	3. $A \backslash B \in \mathcal{A}$ for all $A,B\in \mathcal{A}$.
> 2. a ***Boolean algebra*** if it is a Boolean ring and $X\in \mathcal{A}$.

- **Remark**: $X \backslash A$ is not necessarily in a Boolean ring $\mathcal{A}$, even when $A\in \mathcal{A}$. But it is always in a Boolean algebra $\mathcal{A}$.
- **Remark**: With 2 and 3, we have intersection as: $A \cap B = A \backslash (A \backslash B)$
---
##### Examples
1. The union of half-closed intervals in $X=[0,1)$ is an algebra. 
2. For an infinite $X$, $\mathcal{A}:=\{ A\in \mathcal{P}(X):A\text{ is finite or }A^c\text{ is finite} \}$ is an algebra.
---