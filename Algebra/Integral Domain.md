#Definition #Algebra

> [!definition]
> An ***integral domain*** $R$ is a non-trivial commutative [[Zero Divisor|domain]]. 
- **Related definition**: An element $r\in R$ is called:
  1. ***irreducible*** in $R$ if $r\neq 0$, $r\notin R^{\times}$ and for any $a,b\in R$, $r=ab\implies a\in R^{\times} \lor b\in R^{\times}$
  2. ***prime*** in $R$ if $r\neq 0$, $r\notin R^{\times}$ and for any $a,b\in R$, $r|ab\implies r|a \lor r|b$
- **Related definition**: Two elements $a,b\in R \backslash\{ 0 \}$ are called ***associates*** if there exists $r\in R^{\times}$ s.t. $a=rb$. Then, we write $a \sim b$.
- **Related definition**: Let $a,b\in R \backslash \{ 0 \}$. Then, $d\in R$ is the ***greatest common divisor (gcd)*** of $a,b$ if
	1. $d|a$ and $d|b$ 
	2. if $c|a\land c|b$ then $c|d$.
- **Remark**: $d=\text{gcd}(a,b)$ if $(a,b)\subseteq(d)$ and for any [[Principal Ideal Domain|principal ideal]] $(c)$ s.t. $(a,b)\subseteq(c)$, we have: $(d)\subseteq(c)$.

---
##### Properties
> [!lemma] Proposition 1
> For an integral domain $R$, 
> 1. $R[X]$ is an integral domain.
> 2. $R[X]^{\times}=R^{\times}$
> 3. if $R$ is finite, then $R$ is a field.

> [!proof]-
> We have that: 
> 1. Let $p,q\in R[X]$ s.t. $p\neq 0\neq q$ and let $a_{n},b_{m}$ the leading coefficients of $p$ and $q$ respectively. As $R$ is an integral domain, $a_{n}b_{m}\neq 0$ and therefore, $$\text{deg}(pq)=n+m>-\infty$$
> 	Therefore, $pq\neq 0$.
>2. Let $a\in R^{\times}$. Then, there exists $b\in R^{\times}\subseteq R[X]$ s.t. $ab=1$. Therefore, $a\in R[X]^\times$. 
>   
>    Now let $p\in R[X]^{\times}$. Then, there exists $q\in R[X]^{\times}$ s.t. $pq=1$. As $R$ is an integral domain, the product of the leading coefficients $a_{n}\cdot b_{m}\neq 0$. Therefore, we have: $$\text{deg}(p)+\text{deg}(q)=\deg(pq)=0$$from which we can conclude that $\text{deg}(p)=0$ and $\deg(q)=0$. Therefore, $p=a_{0}$ and $q=b_{0}$ and $pq=a_{0}b_{0}=1$. This proves that $p\in R^{\times}$.
> 3. Let $R$ be finite and $(0)\neq I\unlhd R$ an ideal. Then, there exists $0\neq a\in I$ and by the finiteness, there exists $m\neq n\in \mathbb{N}$ s.t. $a^m=a^n$. Therefore, wlog $m>n$ and $1=a^{m-n}$. Hence, $I=R$ and by [[Field|Proposition 1]], $R$ is a field.
---
> [!lemma] Lemma 2
> For an integral domain $R$, 
> 1. every prime element is irreducible.
> 2. for every $0\neq p\in R$, $p$ is prime if and only if $(p)\subseteq R$ is a [[prime ideal]].
> 3. $\gcd(a,b)$ (if it exists) is uniquely determined up to multiplication by units.

> [!proof]-
> We have:
> 1. Let $r\in R$ be prime. If $r=ab$, then $r|ab$ and $r|a$ or $r|b$. Wlog assume that $r|a$. Then, there exists $q\in R$ s.t. $rq=a$. Then, $r=rqb$ and $r(1-qb)=0$. As $r\ne 0$, we have $1=qb$, i.e. $b\in R^\times$.
> 2. Let $p$ be a prime. Then, $(p)\neq R$ and let $ab\in (p)$, i.e. $ab=pr$ for some $r\in R$. Then, $p|ab$ and either $p|a$ or $p|b$, which means $a\in (p)$ or $b\in (p)$.
>    
>    Conversely, let $(p)\unlhd R$ be a prime ideal. Then, $(p)\neq R$ and $p\notin R^\times$. Now, for $a,b\in R$, s.t. $p|ab$, we have $ab\in (p)$ and $a\in (p)$ or $b\in (p)$. Therefore, $p|a$ or $p|b$.
> 3. Let $a,b\in R$ and $d,d'\in R$ be the gcds of $a$ and $b$. Then, by the definition, $d|d'$ and $d'|d$. Therefore, there exists $r,r'\in R$ s.t. $d=d'r=dr'r$. Therefore, $d(1-r'r)=0$ and $1=r'r$ which means that $r,r'\in R^\times$, i.e. $d\sim d'$.

- **Remark**: Generally irreducible elements are not prime, e.g. $2\in \mathbb{Z}[\sqrt{- 5 }]$ is irreducible but not prime as $2\cdot 3 =(1+\sqrt{ -5 })(1-\sqrt{- 5 })$.
- **Remark**: If $R$ is not an integral domain, then prime does not imply irreducibility in general, e.g. $R=\mathbb{Z} /6\mathbb{Z}$ and $2$ is prime but not irreducible as $2=2\cdot{4}$.
- **Remark**: In $\mathbb{Z}[\sqrt{ -5 }]$, $\gcd(6,2+2\sqrt{ -5 })$ doesn't exist: Let $c+d\sqrt{ -5 }$ be the gcd. Then, $1+\sqrt{ -5 }|d$ and $2|d$. Therefore, $N(c+d\sqrt{ -5 })=12$. However, this doesn't exist in $\mathbb{Z}[\sqrt{ -5 }]$.
---
> [!lemma] Proposition 3 (Equivalent Definitions)
> Let $R$ be an integral domain and $a,b\in R$. Then, for $d\in R$, TFAE:
> 1. $(a,b)=(d)$
> 2. there exist $x,y\in R$ s.t. $d=ax+by$ and for all $s,t\in R$, $d|as+bt$.
> 3. there exist $x,y\in R$ s.t. $d=ax+by$ and $d|a$ and $d|b$.

> [!proof]-
> We have:
> 1. (1=>2): Obvious.
> 2. (2=>3): Take $s=1$ and $t=0$ and vice versa.
> 3. (3=>1): $a\in (d)$ and $b\in (d)$, hence $(a,b)\subseteq(d)$. Further, for $r\in R$, we have $$dr=axr+byr\in (a,b)$$
---
> [!lemma] Proposition 4
> Let $R$ be an integral domain and $0\neq r\in R$. Then, TFAE:
> 1. $r$ is irreducible.
> 2. $(r)$ is maximal among all proper [[Principal Ideal Domain|principal ideals]].

> [!proof]-
> We have:
> 1. (1=>2): Let $r$ be irreducible. If there exists $(s)$ s.t. $(r)\subseteq(s)\subseteq R$. If $s\in R^\times$, then $(s)=R$. If $s\notin R^\times$, Then, $r=xs$ for some $x$ and as $r$ is irreducible, $x\in R^\times$. Therefore, $r\sim s$ and $(r)=(s)$.
> 2. (2=>1): Suppose $(r)$ is maximal among proper principal ideals. Let $r=xs$ for some $x,s\in R$. If both of them are non-units, then $(r)\subsetneq(x)$ because if $(r)=(x)$, then $x=rt$ for some $t\in R$ and $x=xst$. Therefore, $x(1-st)=0$ and $st=1$, i.e. $s\in R^\times$ which is a contradiction. 
---
##### Examples
- $\mathbb{Q},\mathbb{R},\mathbb{C},\mathbb{Z} / p\mathbb{Z}$ where $p$ prime are [[Field|fields]], so they are integral domains.
- $\mathbb{Z},\mathbb{Z}[i]$

**Non-examples**
- $\mathbb{Z} / m\mathbb{Z}$ where $m$ is not prime. A divisor of $m$ is a [[Zero Divisor|zero divisor]].
- [[General Linear Group|$\text{M}(n,\mathbb{R})$]] has a zero divisor for $n\geq 2$. (Projection in two orthogonal subspaces)

---
