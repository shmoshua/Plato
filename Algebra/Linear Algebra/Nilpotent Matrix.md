#Definition #LST 

> [!definition]
> A matrix $A\in \mathbb{R}^{n,n}$ is ***nilpotent*** if $A^N=0$ for some $N\in \mathbb{N}$.
---
##### Properties
> [!lemma]
> The following statements are equivalent: 
> 1. $A\in \mathbb{R}^{n,n}$ is nilpotent.
> 2. $A^n=0$
> 3. $\text{Spec}(A)=\{ 0,\dots,0 \}$

>[!proof]-
>(2 => 1): Obvious
>
>(3 => 2): If $\text{Spec}(A)=\{ 0,\dots,0 \}$, then $\chi_{A}(\lambda)=\lambda^n$. Then, by [[Cayley-Hamilton Theorem]], $\chi_{A}(A)=A^n=0$.
>
>(1 => 3): 
