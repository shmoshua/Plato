#Definition #Algebra

> [!definition]
> An ***integral domain*** is a non-trivial commutative [[Zero Divisor|domain]]. 
---
##### Properties
> [!lemma] Proposition 1
> For an integral domain $R$, 
> 1. $R[X]$ is an integral domain.
> 2. $R[X]^{*}=R^{*}$

> [!proof]-
> We have that: 
> 1. Let $p,q\in R[X]$ s.t. $p\neq 0\neq q$ and let $a_{n},b_{m}$ the leading coefficients of $p$ and $q$ respectively. As $R$ is an integral domain, $a_{n}b_{m}\neq 0$ and therefore, $$\text{deg}(pq)=n+m>-\infty$$
> 	Therefore, $pq\neq 0$.
>2. Let $a\in R^{*}$. Then, there exists $b\in R^{*}\subseteq R[X]$ s.t. $ab=1$. Therefore, $a\in R[X]^{*}$. 
>   Now let $p\in R[X]^{*}$. Then, there exists $q\in R[X]^{*}$ s.t. $pq=1$. As $R$ is an integral domain, the product of the leading coefficients $a_{n}\cdot b_{m}\neq 0$. Therefore, we have: $$\text{deg}(p)+\text{deg}(q)=\deg(pq)=0$$from which we can conclude that $\text{deg}(p)=0$ and $\deg(q)=0$. Therefore, $p=a_{0}$ and $q=b_{0}$ and $pq=a_{0}b_{0}=1$. This proves that $p\in R^{*}$.
---
##### Examples
- $\mathbb{Q},\mathbb{R},\mathbb{C},\mathbb{Z} / p\mathbb{Z}$ where $p$ prime are [[Field|fields]], so they are integral domains.
- $\mathbb{Z},\mathbb{Z}[i]$

**Non-examples**
- $\mathbb{Z} / m\mathbb{Z}$ where $m$ is not prime. A divisor of $m$ is a [[Zero Divisor|zero divisor]].
- [[General Linear Group|$\text{M}(n,\mathbb{R})$]] has a zero divisor for $n\geq 2$. (Projection in two orthogonal subspaces)

---
