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
> Every euclidean domain is a [[Principal Ideal Domain|principal ideal domain]].

> [!proof]-
> Let $R$ be euclidean and $\mathfrak{a}\subseteq R$ a non-trivial ideal. Then, we choose $a\in \mathfrak{a}$ s.t. $$a=\arg\min_{b\in \mathfrak{a}} N(b) $$Therefore, for any $b\in \mathfrak{a}$, we have that $b=qa+r$ for some $q,r\in R$. As $a,b\in \mathfrak{a}, r\in \mathfrak{a}$. However, by the minimality assumption, $N(r)\geq N(a)$. This means $r=0$. Therefore, $b=qa$. This shows that $\mathfrak{a}=(a)$.
---
> [!lemma] Theorem 2
> Let $R$ be an euclidean domain and $a,b\in R \backslash\{ 0 \}$. Further, let $d=r_{n}$ be the last non-zero remainder in the Euclidean algorithm with $a,b$. Then, 
> 1. $d=\gcd(a,b)$
> 2. $(d)=(a,b)$ and $d=ax+by$ for some $x,y\in R$.

> [!proof]-
> As $R$ is also a PID by Theorem 1, it suffices to show that $(a,b)=(d)$ by [[Principal Ideal Domain|Theorem 3]].
> 1. **Showing $(a,b)\subseteq (d)$**: By induction, we get that $r_{n}|b$ and $r_{n}|a$. Therefore, $(a,b)\subseteq(d)$.
> 2.  **Showing $(a,b)\supseteq (d)$**: By induction, we get that $r_{i}\in (a,b)$ for all $i\in [n]$.
> 
---
##### Examples
> [!h] Example 1
> Let $F$ be a field. The following are euclidean domains:
> 1. $F$ with $N(a):=0$
> 2. $F[x]$ with $N(f):=\text{deg}(f)$
> 3. $\mathbb{Z}$ with $N(a):=\left| a \right|$
> 4. $\mathbb{Z}[i]$ with $N(a+bi)=a^{2}+b ^{2}$
