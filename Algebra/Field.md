#Definition #Algebra  #LST 

> [!definition]
> A structure $(F,+,\cdot)$ is a ***field*** if it is a commutative [[Unit|division ring]], i.e.: 
> 1. $(F,0,+)$ and $(F \backslash \{ 0 \},1,\cdot)$ are [[abelian group|abelian groups]].
> 2. **Distributivity**: for all $a,b,c\in F$: $$a(b+c)=ab+ac\quad \text{and}\quad (a+b)c=ac+bc$$
---
##### Properties 
> [!lemma] Proposition 1
> Let $R$ be a commutative, non-trivial ring, then $R$ is a field if and only if the only ideals in $R$ are $(0)$ and $R$.

> [!proof]-
> - (=>): Let $\mathfrak{a}\neq(0)$ be an ideal in $R$. Then, there exists $x\in \mathfrak{a}$ with $x\neq 0$. As $x^{-1}\in R$ (as $R$ is a field), $1_{R}=x^{-1}x\in \mathfrak{a}$. Therefore, $\mathfrak{a}=R$.
> - (<=): Let $(0)$ and $R$ be the only ideals. Now, we will show that $R^{*}=R \backslash \{ 0 \}$.  
>   Let $a\in R$ for $a\neq 0$. We have that $(a)\neq (0)$. Therefore, $(a)=R$.
>   This means, there exists $r\in R$ s.t. $ra=1$, as $$(a)=\{ ra:r\in R \}$$Therefore, $r=a^{-1}\in R$ and $R$ is a field.
---
> [!lemma] Proposition 2
> A field $(F,+,\cdot)$ is **cancellative**, i.e. for $a,b,c\in F$, if $a\neq 0$, then:$$ ab=ac\quad \Longrightarrow \quad b=c$$

> [!proof]-
> $$b=1b=a^{-1}ab=a^{-1}ac=1c=c$$
---
> [!lemma] Theorem 3
> Let $R$ be an [[integral domain]]. Then, $R$ is a field if and only if $R[X]$ is a [[principal ideal domain]].

> [!proof]-
> Suppose $R[X]$ is a PID. We have that $R[X] / (X)\cong R$. But $X$ is maximal as $X$ is prime. Therefore, $R$ is a field.
> 
> Conversely, for a field $R$, $R[X]$ is a [[Euclidean domain]] and therefore a PID.

- **Remark**: $R[X]$ being UFD does not imply that $R$ is a field, e.g. $R=\mathbb{Z}$.
---
> [!lemma] Theorem 4
> Let $F$ be a field. If $f\in F[X]$ with $\text{deg}(f)=:n>0$, then $F$ has at most $n$ zeros.
- **Remark**: This is not true for general rings. $x^{2}-1\in (\mathbb{Z} / 8\mathbb{Z})[x]$ has 4 zeros: $1,3,5,7$.
---
> [!lemma] Lemma 5
> A field homomorphism $\varphi:F\to K$ is always injective.

> [!proof]-
> As a field $F$ only has $(0)$ and $F$ as ideals, $\text{ker }\varphi$ has to be one of the two. However, $\varphi(1)\neq 0$ and therefore $\text{ker }\varphi=(0)$. 
---
##### Examples
> [!h] Example 1 (Basic Examples)
> We have:
> 1. $\mathbb{Q},\mathbb{R},\mathbb{C}$ are fields.
> 2. $\mathbb{Z} / p\mathbb{Z}$ for $p$ prime is a field.
> 4. $(\mathbb{R}(s),+,\cdot)$ is a field.
---
##### Non-Examples
> [!h] Non-Example 1 (Basic Non-Examples)
> We have:
> 1. $\mathbb{Z}$ is not a field.
> 2.  $(\mathbb{R}[x],+,\cdot)$ is not a field, because a multiplicative inverse of a polynomial is not a polynomial.
---
> [!h] Non-Example 2 (Quaternions)
> The [[Quaternion|quaternions]] are a non-commutative division ring.