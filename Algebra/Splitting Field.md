#Definition #Algebra 

> [!definition] 
> A [[Extension Field|field extension]] $L:F$ is a ***splitting field*** of a polynomial $f(x)\in F[X]$ if $f$ factors completely in $L[X]$ and $f$ does not split in any intermediate field $F\subseteq K\subsetneq L$
---
##### Properties
> [!lemma] Theorem 1
> Let $F$ is a field and $f(x)\in F[X]$ a polynomial of degree $n$. Then, there exists a splitting field $K$ of $F$ s.t. $[K:F]\leq n!$

> [!proof]+
> Via induction, if $n=1$, then $K=F$. Suppose that $n>1$. If $f$ factors into linear terms in $F[X]$ then take $K=F$. Otherwise, $f$ has an irreducible factor $g(x)$ of degree $\geq 2$. Then, by Kronecker, there exists an extension which has a root $\alpha$ of $g(x)$ and hence $f(x)$.