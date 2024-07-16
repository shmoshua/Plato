#Definition #Algebra  #LST

> [!definition]
> A ***ring*** $(R,0,1,+,\cdot)$ is a set $R$ equipped with two binary operations $+:R\times R \to R$ (addition) and $\cdot:R \times R \to R$ (multiplication) s.t. the following axioms hold:
> 1. $(R,0,+)$ is an abelian [[Group|group]].
> 2. **Multiplicative associativity**: for all $a,b,c\in R$
>    $$ (ab)c=a(bc)$$
> 4. **Multiplicative identity**: for all $a\in R$: $$1a=a 1=a$$
> 5. **Distributivity**: for all $a,b,c\in R$: $$a(b+c)=ab+ac\quad \text{and}\quad (a+b)c=ac+bc$$

- **Related Definition**: A ring $(R,+,\cdot)$ is ***commutative***, if the multiplication $\cdot$ is commutative.
- **Related Definition**: A ring $(R,+,\cdot)$ is **trivial**, if $R=\{ 0 \}$, i.e. $0=1$.
- **Related Definition**: If a commutative ring $R$ also has a multiplicative inverse for all all $a\in R\backslash\{ 0 \}$, $R$ is a [[Field|field]].
---
##### Properties
> [!lemma] Proposition 1
> For every ring $(R,+,\cdot)$, the identity elements $0,1$ are unique. Moreover, for all $a\in R$, the inverse element $(-a)$ is unique.

> [!proof]-
> The uniqueness of $0$ and $(-a)$ is inherited from the group $(R,+)$. Let's assume there are two multiplicative identity $1,1'$. Then:
> $$1=1\cdot 1'=1'$$
----
> [!lemma] Fact 2 (Calculation Rules of a Ring)
> For a ring $(R,+,\cdot)$, it holds that:
> 1. for all $a\in R$: $a 0=0a=0$.
> 2. for all $a,b\in R$: $(-a)b=-(ab)=a(-b)$
> 3. for all $a,b\in R:$ $(-a)(-b)=ab$
> 4. $\left( \sum_{i=1}^{m}a_{i} \right)\left( \sum_{j=1}^{n}b_{j} \right)=\sum_{i=1}^{m}\sum_{j=1}^{n}a_{i}b_{j}$

> [!proof]-
> We show that
> 1. $$a 0 = 0+a0 =-(aa)+aa+a0=-(aa)+a(a+0)=-(aa)+aa=0$$ and
> 	$$0a=0+0a=-(aa)+aa+0a=-(aa)+(a+0)a=-(aa)+aa=0$$ 
>2. $$(-a)b=0+(-a)b=-(ab)+ab+(-a)b=-(ab)+(a+(-a))b=-(ab)+0b=-(ab)$$
>	and $$a(-b)=-(ab)+ab+a(-b)=-(ab)+a(b+(-b))=-(ab)+a0=-(ab)+0=-(ab)$$
----
> [!lemma] Lemma 3
> Let $R$ be a ring and $a,b\in R$. Then, TFAE:
> 1. $b|a$, i.e. there exists $c\in R$

##### Examples
> [!h] Example 1 (Basic Examples)
> We have:
> 1. $\mathbb{Z},\mathbb{Q},\mathbb{R},\mathbb{C}$ are rings.
> 2. $\text{Mat}_{n,n}(\mathbb{R})$ for $n\geq 1$ are non-commutative rings. 
> 3. $\mathbb{Z} / n\mathbb{Z}$ for $n\in \mathbb{Z}$ is a commutative ring. 
> 4. $(\mathbb{R}[z],+,\cdot)$ is a commutative ring.
> 5. $(\mathbb{R}(z),+,\cdot)$, the set of rational functions of $s$ with real coefficients, is a commutative ring.
---