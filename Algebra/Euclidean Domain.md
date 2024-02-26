#Definition #Algebra
> [!definition]
> An [[integral domain]] $R$ is ***euclidean***, if there exists a map $N:R \backslash \{ 0 \}\to \mathbb{N}$ s.t. for all $a,b\in R\backslash\{ 0 \}$, there exists $q,r\in R$ with:
> 1. $a=qb+r$ and 
> 2. $r=0$ or $N(r)<N(b)$
> 
> Then, $q$ is the ***quotient*** and $r$ is the ***remainder***.
---
##### Properties
> [!lemma] Theorem 1
> Every euclidean ring is a [[Principal Ideal|principal ideal ring]].

> [!proof]+
> Let $R$ be euclidean and $\mathfrak{a}\subseteq R$ a non-trivial ideal. Then, we choose $a\in \mathfrak{a}$ s.t. $$a=\arg\min_{b\in \mathfrak{a}} \delta(b) $$Therefore, for any $b\in \mathfrak{a}$, we have that $b=qa+r$ for some $q,r\in R$. As $a,b\in \mathfrak{a}, r\in \mathfrak{a}$. However, by the minimality assumption, $\delta(r)\geq\delta(a)$. This means $r=0$. Therefore, $b=qa$. This shows that $\mathfrak{a}=(a)$.
---
