#Definition #RepresentationTheory 

> [!definition]
> A ***representation*** of an [[associative algebra]] $A$ is a tuple $(\rho,V)$ where:
> 1. $V$ is a [[vector space]].
> 2. $\rho:A\to \text{End}(V)$ is an [[algebra homomorphism]].
- **Remark**: A representation is also called a ***left $A$-module***. A ***right $A$-module*** is a vector space $V$ equipped with an antihomomorphism $\rho:A\to \text{End}(V)$, i.e. $\rho(ab)=\rho(b)\rho(a)$ and $\rho(1_{A})=\text{id}_{V}$.
- **Notation**: For $a\in A$ and $v\in V$, $av:=\rho(a)v$. Therefore, algebra homomorphism can be written as $(ab)v=a(bv)$.
- **Remark**: If $A$ is commutative, a left $A$-module is equivalent to a right $A$-module; we just call them $A$-modules.
---
##### Examples
> [!h] Example 1
> Following are representations: 
> 1. $V=0$.
> 2. ***Regular representation***: $V=A$ and $\rho:A\to \text{End}(A)$ with: $$\rho(a)b=ab$$
> 3. $V=\mathbb{K}$
---
