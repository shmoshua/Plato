#Definition #Algebra 

> [!definition]
> For a [[ring]] $R$ and an [[Ideal (Ring)|ideal]] $I\unlhd R$, the ***radical*** of $I$ is: $$\sqrt{ I }:=\{ a\in R\ | \exists n\in \mathbb{N}: a^n \in I\}$$

^134f35

- **Related definition**: An ideal is a ***radical ideal*** if $\sqrt{ I }=I$. ^3cd183
---
##### Properties
> [!lemma] Proposition 1:
> For any ideal $I\unlhd R$,
> 1. $\sqrt{ I }\unlhd R$. 
> 2. $I\leq \sqrt{ I }$
> 3. $\sqrt{ I }$ is a radical ideal.

^ef8725

> [!proof]-
> We have:
> 1. Let $a,b\in \sqrt{ I }$ where $a^n,b^m\in I$. Then, $$(a+b)^{n+m}=\sum_{k=0}^{n+m}{n+m \choose k}a^kb^{n+m-k}$$As for each summand either $k\geq n$ or $n+m-k>m$, we have that $(a+b)^{n+m}\in I$. Further, for $r\in R$ and $a^n\in I$, $(ra)^n=r^na^n\in I$. Therefore, $\sqrt{ I }$ is an ideal.
> 2. trivial.
> 3. Let $a\in \sqrt{  (\sqrt{ I })}$. Then, $a^n\in \sqrt{ I }$ and $a^{mn}\in I$. Therefore, it holds that $a\in \sqrt{ I }$.

^ac2252

---
> [!lemma] Lemma 2
> For a commutative ring $R$ and $I\unlhd R$, 
> 1. $\sqrt{ I }=\bigcap_{I\subseteq P\unlhd R,P\text{ prime}}^{}P$

^5a7a7e

> [!proof]-
> We have:
> 1. $\subseteq$: let $a\in \sqrt{ I }$, i.e. $a^n\in I$. Then, for any prime $P\supseteq I$, $a\in P$ and also in the intersection.
>    
>    $\supseteq:$ let $a\in R \backslash\sqrt{ I }$, i.e. $a^n\notin I$ for all $n$. Let $\mathcal{M}:=\{ J\unlhd R:I\subseteq J, a^n\notin J\text{ for all }n\geq 0 \}$. By Zorn's lemma, there exists a maximal element $P$ and we will show that $P$ is prime. 
>    
>    Assume $P$ is not prime, i.e. there exists $b,c\in R$ s.t. $bc\in P$ but $b,c\notin P$. Then, $P+(b)$ and $P+(c)$ are strictly bigger than $P$. However, as they are not in $\mathcal{M}$, there exists $n,m$ s.t. $a^n\in P+(b)$ and $a^m\in P+(c)$. Then, $$a^{nm}\in(P+(b))(P+(c))\subseteq P+(bc)$$which is a contradiction. Hence, $P$ is prime.

^aed7dc

- **Corollary**: the [[nilradical]] is given by $\sqrt{ (0) }=\bigcap_{P\unlhd R, P\text{ prime}}^{} P$. ^a3929b
---
##### Examples
> [!h] Example 1
> We have:
> 1. $\sqrt{ (x^2) }=(x)$.

^1e2e72
