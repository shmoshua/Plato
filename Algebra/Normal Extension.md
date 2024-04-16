#Definition #Algebra 

> [!definition]
> A [[Field Extension|field extension]] $L:K$ is ***normal*** if every [[Integral Domain|irreducible]] polynomial $f\in K[X]$ which has a root in $L$ splits in $L$.
---
##### Properties
> [!lemma] Theorem 1
> Let $L:K$ be an extension. Then, the following are equivalent:
> 1. $L:K$ is normal and $[L:K]<+\infty$
> 2. $L$ is a [[splitting field]] of some polynomial $f\in K[X]$

> [!proof]+
> Let $L$ be a splitting field of $g\in K[X]$. Let further $f\in K[X]$ with a root $\alpha\in L$. We need to show that $f$ splits in $L$. Let $M$ be the splitting field of $f\cdot g$. Suppose $\theta_{1},\theta_{2}$ are 2 roots of $f$ in $M$.
> 
> For $j=1,2$, we have that: $$[L(\theta_{j}):L][L:K]=[L(\theta_{j}):K]=[L(\theta_{j}):K(\theta_{j})][K(\theta_{j}):K]$$Since $\theta_{1},\theta_{2}$ are roots of the same irreducible polynomial, $K(\theta_{1})\cong K(\theta_{2})$ and especially, $$[K(\theta_{1}):K]=[K(\theta_{2}):K]$$As $L$ is a splitting field of $g$
---
##### Examples
> [!h] Example 1
> $\mathbb{C}:\mathbb{R}$ is normal.