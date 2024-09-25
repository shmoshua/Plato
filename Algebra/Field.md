#Definition #Algebra  #LST 

> [!definition]
> A structure $(F,+,\cdot)$ is a ***field*** if it is a commutative [[Unit|division ring]], i.e.: 
> 1. $(F,0,+)$ and $(F \backslash \{ 0 \},1,\cdot)$ are [[abelian group|abelian groups]].
> 2. **Distributivity**: for all $a,b,c\in F$: $$a(b+c)=ab+ac\quad \text{and}\quad (a+b)c=ac+bc$$
---
##### Properties 
> [!lemma] Proposition 1 (Equivalent Definitions of Fields)
> Let $R$ be a commutative, non-trivial ring, then TFAE:
> 1. $R$ is a field.
> 2. the only ideals in $R$ are $(0)$ and $R$.
> 3. $R[X]$ is a [[Principal Ideal Domain|principal ideal domain]].
> 4. $R[X]$ is a [[euclidean domain]].

> [!proof]-
> We have:
> 1. (1=>2): Let $I\unlhd R$ be a non-zero ideal and $a\in I$ be the non-zero element. Then, as $R$ is a field $a^{-1}\in R$ and $a^{-1}a=1\in I$. Therefore, $I=R$.
> 2. (2=>1): Let $R$ and $(0)$ be the only ideals in $R$. We will show that $R$ is a division ring. Let $a\in R$. Then, $(a)\neq(0)$ and therefore, $(a)=R$. Hence, there exists $r\in R$ s.t. $ra=1$ since $$(a)=\{ ra:r\in R \}$$Therefore, $r=a^{-1}\in R$ and $R$ is a field.
> 3. (1=>3): If $R$ is a field $R[X]$ is a Euclidean domain and therefore a PID.
> 4. (3=>1): If $R[X]$ is a PID, then it is ID and therefore, $R$ is also an ID as a subring. Then, $R[X] / (X)\cong R$ and $(X)$ is a prime ideal, and as $R[X]$ is a PID $(X)$ is maximal. Therefore, $R$ is a field.
> 5. (1=>4): Obvious.
> 6. (4=>3): Obvious. 
---
> [!lemma] Proposition 2
> A field $(F,+,\cdot)$ is **cancellative**, i.e. for $a,b,c\in F$, if $a\neq 0$, then:$$ ab=ac\quad \Longrightarrow \quad b=c$$

> [!proof]-
> $$b=1b=a^{-1}ab=a^{-1}ac=1c=c$$
---
> [!lemma] Theorem 3
> Let $F$ be a field. If $f\in F[X]$ with $\text{deg}(f)=:n>0$, then $F$ has at most $n$ zeros.
- **Remark**: This is not true for general rings. $x^{2}-1\in (\mathbb{Z} / 8\mathbb{Z})[x]$ has 4 zeros: $1,3,5,7$.
---
> [!lemma] Lemma 4
> A field homomorphism $\varphi:F\to K$ where $K\neq \{ 0 \}$ is always injective.

^509d9f

> [!proof]-
> As a field $F$ only has $(0)$ and $F$ as ideals, $\text{ker }\varphi$ has to be one of the two. However, $\varphi(1)\neq 0$ and therefore $\text{ker }\varphi=(0)$. 

^40c6b7

---
> [!lemma] Theorem 5
> For a field $F$, 
> 1. a finite subgroup $G\unlhd F^\times$ is cyclic.

> [!proof]-
> Let $n:=e(G)$. Then $\alpha^n=1$ for all $\alpha\in G$. However, since $f(x):=x^n-1\in F[X]$ has at most $n$ roots, $\left| G \right|\leq n$. But as $n=e(G)\leq \left| G \right|$, we have that $\left| G \right|=n$ and by [[Exponent of a Group|Proposition 1]], there exists $\alpha\in G$ s.t. $\text{ord}(\alpha)=\left| G \right|$. This proves that $G$ is cyclic.
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