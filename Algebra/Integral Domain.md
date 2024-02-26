#Definition #Algebra

> [!definition]
> An ***integral domain*** $R$ is a non-trivial commutative [[Zero Divisor|domain]]. 
- **Related definition**: An element $r\in R$ is called:
  1. ***irreducible*** in $R$ if $r\neq 0$, $r\notin R^{*}$ and for any $a,b\in R$, $r=ab\implies a\in R^{*} \lor b\in R^{*}$
  2. ***prime*** in $R$ if $r\neq 0$, $r\notin R^{*}$ and for any $a,b\in R$, $r|ab\implies r|a \lor r|b$
- **Related definition**: Two elements $a,b\in R \backslash\{ 0 \}$ are called ***associates*** if there exists $r\in R^{*}$ s.t. $a=rb$. Then, we write $a \sim b$.
- **Related definition**: Let $a,b\in R \backslash \{ 0 \}$. Then, $d\in R$ is the ***greatest common divisor (gcd)*** of $a,b$ if
	1. $d|a$ and $d|b$ 
	2. if $c|a\land c|b$ then $c|d$
- **Remark**: $d=\text{gcd}(a,b)$ if $(a,b)\subseteq(d)$ and for any [[Principal Ideal Domain|principal ideal]] $(c)$ s.t. $(a,b)\subseteq(c)$, we have: $(d)\subseteq(c)$.

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
> [!lemma] Lemma 2
> For an integral domain $R$, 
> 1. every prime element is irreducible.
> 2. for every non-zero element $p\in R$, $p$ is prime if and only if $(p)\subseteq R$ is a [[prime ideal]].
> 3. the greatest common divisor of $a,b$ (if it exists) is uniquely determined up to units.
---
##### Examples
- $\mathbb{Q},\mathbb{R},\mathbb{C},\mathbb{Z} / p\mathbb{Z}$ where $p$ prime are [[Field|fields]], so they are integral domains.
- $\mathbb{Z},\mathbb{Z}[i]$

**Non-examples**
- $\mathbb{Z} / m\mathbb{Z}$ where $m$ is not prime. A divisor of $m$ is a [[Zero Divisor|zero divisor]].
- [[General Linear Group|$\text{M}(n,\mathbb{R})$]] has a zero divisor for $n\geq 2$. (Projection in two orthogonal subspaces)

---
