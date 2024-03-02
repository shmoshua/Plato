#Definition #Algebra

> [!definition]
> An ***integral domain*** $R$ is a non-trivial commutative [[Zero Divisor|domain]]. 
- **Related definition**: An element $r\in R$ is called:
  1. ***irreducible*** in $R$ if $r\neq 0$, $r\notin R^{*}$ and for any $a,b\in R$, $r=ab\implies a\in R^{*} \lor b\in R^{*}$
  2. ***prime*** in $R$ if $r\neq 0$, $r\notin R^{*}$ and for any $a,b\in R$, $r|ab\implies r|a \lor r|b$
- **Related definition**: Two elements $a,b\in R \backslash\{ 0 \}$ are called ***associates*** if there exists $r\in R^{*}$ s.t. $a=rb$. Then, we write $a \sim b$.
- **Related definition**: Let $a,b\in R \backslash \{ 0 \}$. Then, $d\in R$ is the ***greatest common divisor (gcd)*** of $a,b$ if
	1. $d|a$ and $d|b$ 
	2. if $c|a\land c|b$ then $c|d$.
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
> 3. the greatest common divisor of $a,b$ (if it exists) is uniquely determined up to multiplication by units.

> [!proof]-
> We have:
> 1. Let $p\in R$ is prime. Let $a,b\in R$ s.t. $p=ab$. Therefore, $p|ab$ and $p|a$ or $p|b$. Wlog assume that $p|a$. Then, there exists $r\in R$ s.t. $pr=a$. Then, $p=prb$ and $p(1-rb)=0$. As $p\neq 0$ and $R$ is an integral domain, $(1-rb)=0$ and $b\in R^{*}$.
> 2. Let $p\in R$ be non-zero prime. Then, $(p)\neq R$ as $p$ is not a unit. Therefore, for any $ab\in (p)$, $p|ab$ and $p|a$ or $p|b$, which means $a\in (p)$ or $b\in (p)$.
>    
>    Conversely, let $(p)\subseteq R$ be a prime ideal. Then, $(p)\neq R$ and therefore, $p\notin R^{*}$. Suppose $p|ab$. Then, $ab\in (p)$ and therefore, $a\in (p)$ or $b\in (p)$. Therefore, $p|a$ or $p|b$.
> 3.  Let $a,b\in R$ and $d,d'\in R$ be the gcds of $a$ and $b$. Then, by the definition, $d|d'$ and $d'|d$. Therefore, there exists $r,r'\in R$ s.t. $$d=d'r'=drr'$$Therefore, $d(1-rr')=0$ and $r,r'\in R^{*}$, i.e. $d\sim d'$.
- **Remark**: In $\mathbb{Z}$, $n\in \mathbb{Z}$ is prime if and only if $n$ is irreducible.
- **Remark**: Generally irreducible elements are not prime, e.g. $2\in \mathbb{Z}[\sqrt{ 5 }]$ is irreducible but not prime as $2\cdot 3 =(1+\sqrt{ 5 })(1-\sqrt{ 5 })$.
- **Remark**: If $R$ is not an integral domain, then prime does not imply irreducibility in general, e.g. $R=\mathbb{Z} /6\mathbb{Z}$ and $2$ is prime but not irreducible as $2=2\cdot{4}$.
---
> [!lemma] Proposition 3
> Let $R$ be an integral domain and $r\in R \backslash\{ 0 \}$ and $r\notin R^{*}$. Then, the following are equivalent:
> 1. $r$ is irreducible.
> 2. $(r)$ is maximal among all proper [[Principal Ideal Domain|principal ideals]].

> [!proof]-
> We have:
> - =>: Suppose $r$ is irreducible and $s\in R$ s.t. $(r)\subseteq(s)\subsetneq R$. Then, firstly $s$ cannot be a unit. Then, $r=xs$ for some $x\in R$. As $r$ is irreducible, $x\in R^{*}$, i.e. $r\sim s$ and $(r)=(s)$.
> - <=: Suppose $(r)$ is maximal among proper principal ideals. Assume $r=xs$ where $x,s$ are both non-zero non-units. Then, $(xs)\subsetneq(x)$ because if $(xs)=(s)$, then $x\in (xs)$ and there exists $t\in R$ s.t. $x=xst$, which means that $st=1$ and $s\in R^{*}$. Therefore, we have: $$(r)=(xs)\subsetneq(x)\subsetneq R$$which is a contradiction.
---
##### Examples
- $\mathbb{Q},\mathbb{R},\mathbb{C},\mathbb{Z} / p\mathbb{Z}$ where $p$ prime are [[Field|fields]], so they are integral domains.
- $\mathbb{Z},\mathbb{Z}[i]$

**Non-examples**
- $\mathbb{Z} / m\mathbb{Z}$ where $m$ is not prime. A divisor of $m$ is a [[Zero Divisor|zero divisor]].
- [[General Linear Group|$\text{M}(n,\mathbb{R})$]] has a zero divisor for $n\geq 2$. (Projection in two orthogonal subspaces)

---
