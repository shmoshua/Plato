#Definition #Algebra

> [!definition]
> Let $R$ be a commutative [[Ring|ring]]. An [[ideal]] $\mathfrak{p}\subseteq R$ is a ***prime ideal***, if $R / \mathfrak{p}$ is an [[integral domain]].
---
##### Properties
> [!lemma] Proposition 1
> For a commutative ring $R$, if $\mathfrak{p}\subseteq R$ is an ideal, then $\mathfrak{p}$ is a prime ideal if and only if it holds that $\mathfrak{p}\neq R$ and for all $a,b\in R$ s.t: $$a\cdot b\in \mathfrak{p}\implies a\in \mathfrak{p}\lor b\in \mathfrak{p}$$

>[!proof]-
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