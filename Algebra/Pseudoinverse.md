#Definition #Algebra 

> [!definition]
> Let $A\in K^{m,n}$. A ***pseudoinverse*** of $A$ is a matrix $A^+\in K^{n,m}$ s.t. 
> 1. $AA^+ A=A$.
> 2. $A^+ AA^+=A^+$.
> 3. $(AA^+)^{*}=A A^+$.
> 4. $(A^+ A)^{*}=A^+ A$.

---
##### Properties
> [!lemma] Proposition 1 (Symmetric Matrices)
> Let $A\in \mathbb{R}^{n,n}$ be symmetric. Then, the pseudoinverse is characterized by:
> 1. $(A^+)^\top=A^+$.
> 2. $A^+v=0$ for all $v\in \text{ker }A$.
> 3. $A^+ Av=A A^+ v=v$ for all $v\in \text{ker }L^ \bot$.