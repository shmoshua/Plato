#Definition #Algebra

> [!definition]
> For a commutative [[ring]] $R$, an [[Ideal (Ring)|ideal]] $I\unlhd  R$ is a ***prime ideal***, if one of the following equivalent conditions hold:
> 1. $R / I$ is an [[integral domain]] or
> 2. $I\neq R$ and if $ab\in I$ then $a\in I$ or $b\in I$ for all $a,b\in R$.
---
##### Properties
> [!lemma] Theorem 1 (Equivalent Definitions of Prime Ideals)
> For a commutative ring $R$ and an ideal $I\unlhd R$, TFAE:
> 1. $R / I$ is an integral domain.
> 2. $I\neq R$ and if $ab\in I$ then $a\in I$ or $b\in I$ for all $a,b\in R$.

> [!proof]+
> We have that:
> 1. (1=>2): If $R / I$ is an integral domain, $R / I\neq(0)$ and therefore, $I \neq R$. Further, for $a,b\in R$ with $ab\in I$, we have that: $$(a)$$
>[!proof]+
> (=>): If $\mathfrak{p}$ is a prime ideal, then $R / \mathfrak{p}$ is an integral domain. Therefore, $R / \mathfrak{p}\neq \{ 0 \}$ which means that $\mathfrak{p}\neq R$. Now let $a,b\in R$ s.t. $$a\cdot b\in \mathfrak{p}$$
> Then, $\overline{0}=\overline{a\cdot b}=\overline{a}\cdot \overline{b}$ and as $R / \mathfrak{p}$ is an integral domain, $\overline{a}=\overline{0}$ or $\overline{b}=\overline{0}$. In any case, $$a\in \mathfrak{p}\lor b\in\mathfrak{p}$$
> 
> (<=): Let $\overline{a},\overline{b}\in R / \mathfrak{p}$ with $a\cdot b\in \mathfrak{p}$. Then, $\overline{a}=\overline{0}$ or $\overline{b}=\overline{0}$. Therefore, $R / \mathfrak{p}$ is a integral domain.
---
> [!lemma] Proposition 2
> Let $R,S$ be commutative rings, $\varphi:R\to S$ a [[Ring Homomorphism|ring homomorphsim]] and $\mathfrak{p}\subseteq S$ a prime ideal in $S$. Then, $\varphi ^{-1}[\mathfrak{p}]\subseteq R$ is a prime ideal in $R$.

> [!proof]-
> We first show that $\varphi ^{-1}[\mathfrak{p}]\neq R$. If $\varphi ^{-1}[\mathfrak{p}]=R$, $1_{R}\in \varphi ^{-1}[\mathfrak{p}]$ and therefore, $1_{S}=\varphi(1_{R})\in \mathfrak{p}$. Therefore, $\mathfrak{p}=S$ and $\mathfrak{p}$ is not a prime ideal.
> 
> Let $a,b\in R$ s.t. $a\cdot b\in \varphi ^{-1}[\mathfrak{p}]$. Then, $\varphi(a\cdot b)=\varphi(a)\varphi(b)\in \mathfrak{p}$. As $\mathfrak{p}$ is a prime ideal, we have: $$\varphi(a)\in \mathfrak{p}\lor \varphi(b)\in \mathfrak{p}$$which shows that: $$a\in \varphi ^{-1}[\mathfrak{p}]\lor b\in \varphi ^{-1}[\mathfrak{p}]$$Therefore, by Proposition 1, $\varphi ^{-1}[\mathfrak{p}]$ is a prime ideal.
---
##### Examples
- For $R = \mathbb{Z}$, $m\mathbb{Z}$ is a prime ideal if and only if $m$ is prime or $m=0$. This is equivalent to $m\mathbb{Z}$ being [[Maximal Ideal|maximal]], i.e. $\mathbb{Z} / m\mathbb{Z}$ is a field.
- 