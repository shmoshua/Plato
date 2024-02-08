#Definition #Algebra-I  #LST 

> [!definition]
> A structure $(F,+,\cdot)$ is a ***field*** if: 
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
##### Examples
- $\mathbb{Q},\mathbb{R},\mathbb{C}$
- $\mathbb{Z} / p\mathbb{Z}$ for $p$ prime.
- $(\mathbb{R},+,\cdot)$ is a field.
- $(\mathbb{R}^{n\times n},+,\cdot)$ is not a field as [[Singular Matrices|singular matrices]] have no inverse.
- $(\mathbb{R}[s],+,\cdot)$ is not a field, because a multiplicative inverse of a polynomial is not a polynomial.
- $(\mathbb{R}(s),+,\cdot)$ is a field.

---