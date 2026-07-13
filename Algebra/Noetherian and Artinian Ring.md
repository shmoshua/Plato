#Definition #Algebra 

> [!definition]
> Let $R$ be a [[ring]].
> 1. $R$ is a ***Noetherian ring*** if it is a [[Noetherian and Artinian Module|Noetherian $R$-module]].
> 2. $R$ is a ***Artinian ring*** if it is a [[Noetherian and Artinian Module|Artinian $R$-module]].

---
##### Properties
> [!lemma] Corollary 1
> From [[Noetherian and Artinian Module|Proposition 1]], we have that for a ring $R$, TFAE:
> 1. $R$ is Noetherian.
> 2. every ideal $I\unlhd R$ is finitely generated.
---
> [!lemma] Proposition 2
> Let $R$ be a Noetherian integral domain. TFAE:
> 1. Every prime ideal of codimension $1$ is principal.
> 2. $R$ is a [[unique factorization domain]].

> [!proof]-
> We have that:
> 1. (1=>2): Let $f\in R$ be a non-zero non-unit. We can decompose $f$ as a product of irreducible elements since $R$ is Noetherian: Otherwise, $f$ is not irreducible itself so we have a decomposition $f=f_{1}f_{1}'$ into non-units, of which at least one factor, say $f_{1}$, is not a product of irreducible elements. We can continue this process to get: $$(f)\subsetneq(f_{1})\subsetneq (f_{2})\subsetneq\dots$$which is a contradiction to $R$ being Noetherian. 
>    
>    To now prove that $R$ is a UFD, it suffices to show that every irreducible element $f$ is prime. Choose a minimal prime ideal $P$ containing $f$. By Principal ideal theorem, $\text{codim }P=1$ and $P$ is principal and $P=(g)$ for some prime $g$. However as $g|f$ and $f$ is irreducible, $f$ and $g$ are associates. Hence, $f$ is prime as well.
> 1. (2=>1): Let $P$ be a prime ideal of codimension $1$. We can then choose $f\in P$ that is non-zero. As $P\ne (1)$, we can have that $f$ is a non unit. 
>    
>    As $R$ is a UFD, $f=f_{1}\dots f_{k}$ for some prime $f_{1},\dots,f_{k}\in R$. Since $P$ is a prime ideal, $f_{i}\in P$ for some $i$. We thus obtain a chain $(0)\subsetneq(f_{i})\subseteq P$ of prime ideals. But as the codimension is $1$, we have that $(f_{i})=P$. 

---
##### Examples 
> [!h] Example 1
> Let $R:=K[x_{1},x_{2},x_{3},x_{4}] / (x_{1}x_{4}-x_{2}x_{3})$
> 1. $R$ is an integral domain of dimension $3$. 
---
