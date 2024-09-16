#Definition #MeasureTheory 

> [!definition]
> Let $\varnothing \neq \mathcal{A} \subseteq \mathcal{P}(X)$. $\mathcal{A}$ is called a:
> 1.  ***Boolean ring*** in $X$, if:
> 	1. $\varnothing \in \mathcal{A}$
> 	2. $A\cup B\in \mathcal{A}$ for all $A,B\in \mathcal{A}$.
> 	3. $A \backslash $
> 	4. $A,B\in \mathcal{A}$ implies $A \cup B \in \mathcal{A}$.
> 	5. $A,B\in\mathcal{A}$ implies $A \backslash B\in \mathcal{A}$.
> 
> Notice that this is a specification of the [[Ring| ring]] we know, but on sets.  A ring is an ***algebra*** if $X\in\mathcal{A}$.

- **Remark**: $A^c:= X \backslash A$ is not necessarily in a ring $\mathcal{A}$, even when $A\in \mathcal{A}$. But it is always in an algebra $\mathcal{A}$.
- **Remark**: With 2 and 3, we have intersection as: $A \cap B = A \backslash (A \backslash B)$
---
##### Examples
1. The union of half-closed intervals in $X=[0,1)$ is an algebra. 
2. For an infinite $X$, $\mathcal{A}:=\{ A\in \mathcal{P}(X):A\text{ is finite or }A^c\text{ is finite} \}$ is an algebra.
---