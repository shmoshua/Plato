#Series #Algebra 

> [!definition] Problem 1
> Let $K$ be a field, $\mathcal{I}$ be a set of indices and for every $i\in \mathcal{I}$, let $K_{i}\subseteq K$ be a subfield. Show that $\bigcap_{i\in \mathcal{I}}^{}K_{i}$ is a subfield of $K$.

As arbitrary intersections of subgroups form a subgroup as for $x,y\in \bigcap_{i\in \mathcal{I}}^{}H_{i}$, $xy^{-1}\in H_{i}$ for all $i\in \mathcal{I}$. Therefore,
1. $K_{i}$ is an additive subgroup so $\bigcap_{i\in \mathcal{I}}^{}K_{i}$ is an abelian additive subgroup.
2. $K_{i}\backslash\{ 0 \}$ is a multiplicative subgroup so $\left( \bigcap_{i\in \mathcal{I}}^{}K_{i} \right)\backslash\{ 0 \}=\bigcap_{i\in \mathcal{I}}^{}K_{i} \backslash\{ 0 \}$ is an abelian multiplicative subgroup.
and the distributivity is inherited from $K$ directly.
---
> [!definition] Problem 2
> Decide which of the following quotient rings are isomorphic to each other:
> 1. $R_{1}:=\mathbb{R}[X,Y]  / (X^{2})$
> 2. $R_{2}:=\mathbb{R}[X,Y,Z] / (X,Y)$
> 3. $R_{3}:=\mathbb{R}[X,Y,Z]/(Y^{2},X+Z)$
> 4. $R_{4}:=\mathbb{R}[X,Y] / (X+Y)$
> 5. $R_{5}:= \mathbb{R}[X,Y,Z] / (XY)$
> 6. $R_{6}:=\mathbb{R}[X,Y,Z] / (XY+2X+Y+Z)$

hihi

---
> [!definition] Problem 3
> Let $R$ be a commutative ring and let $\varphi:R\hookrightarrow \mathbb{Z}$ be a surjective ring homomorphism. Prove that the following statements are true or give a counter-example:
> 1. $\text{Im }\varphi$ is a prime ideal in $\mathbb{Z}$.
> 2. For $\mathfrak{s}$ a prime ideal in $\mathbb{Z}$, $\varphi ^{-1}(\mathfrak{s})$ is also a prime ideal.
> 3. For $\mathfrak{r}$ a prime ideal in $R$ with $\text{ker}\varphi \subseteq \mathfrak{r}$, $\varphi(\mathfrak{r})$ is also a prime ideal in $\mathbb{Z}$.

We have:
1. $\text{Im }\varphi=\mathbb{Z}$ is not a prime ideal in $\mathbb{Z}$.
2. Firstly, we know that $\varphi ^{-1}(\mathfrak{s})$ is an ideal in $R$. Then, clearly $\varphi ^{-1}(\mathfrak{s})\neq R$ as $\mathfrak{s}\neq \mathbb{Z}$. Finally, for $a,b\in R$: $$ab\in \varphi ^{-1}(\mathfrak{s})\implies\varphi(a)\varphi(b)=\varphi(ab)\in \mathfrak{s}\implies\varphi(a)\in \mathfrak{s}\lor\varphi(b)\in \mathfrak{s}\implies a\in \varphi ^{-1}(\mathfrak{s})\lor b\in \varphi ^{-1}(\mathfrak{s})$$Therefore, $\varphi ^{-1}(\mathfrak{s})$ is prime.
3. Firstly, $\varphi(\mathfrak{r})$ is proper as if $\varphi(\mathfrak{r})=\mathbb{Z}$, then for all $x\notin\mathfrak{r}$, there exists $y\in \mathfrak{r}$ s.t. $x-y\in \text{ker}\varphi \subseteq \mathfrak{r}$ which is a contradiction. Now, let $a,b\in \mathbb{Z}$ s.t. $ab\in \varphi(\mathfrak{r})$. As $\varphi$ is surjective, there exists $x,y\in R$ s.t. $\varphi(x)=a,\varphi(y)=b$. Therefore, there exists $z\in \mathfrak{r}$ s.t. $$\varphi(x)\varphi(y)=\varphi(z)$$In other words, $xy-z\in \text{ker}(\varphi)\subseteq \mathfrak{r}$. Therefore, $xy\in \mathfrak{r}$ and as $\mathfrak{r}$ is prime, $x\in \mathfrak{r}$ or $y\in \mathfrak{r}$. This shows that $a\in \varphi(\mathfrak{r})$ or $b\in \varphi(\mathfrak{r})$. Therefore, $\varphi(\mathfrak{r})$ is prime.
---
> [!definition] Problem 4
> Show that any finite integral domain is a field.

Let $R$ be a finite integral domain and $(0)\neq\mathfrak{a}\subseteq R$ an ideal. Then, there exists non-zero $a\in \mathfrak{a}$ s.t. from the finiteness, $a^m=a^n$ for some $m>n>0$. It follows that $1=a^{m-n}\in \mathfrak{a}$ and $\mathfrak{a}=R$. This proves that $R$ is a field.

---
> [!definition] Problem 5
> Let $R$ and $S$ be rings with $1$ and $\varphi:R\to S$ be a nonzero map which satisfies for all $a,b\in R$:
> 1. $\varphi(a+b)=\varphi(a)+\varphi(b)$ and 
> 2. $\varphi(ab)=\varphi(a)\varphi (b)$. 
> 
> Show that if $\varphi(1_{R})\neq 1_{S}$ then $\varphi(1_{R})$ is a zero divisor. Hence if $S$ has no zero divisors then $\varphi(1_{R})=1_{S}$.

Let $\varphi(1_{R})\neq 1_{S}$. By the uniqueness of $1$ in $S$, there exists $s\in S\backslash\{ 0 \}$ s.t. $\varphi(1_{R})\cdot s\neq s$. In other words, $$(\varphi(1_{R})-1_{S})s\neq 0$$Then, $\varphi(1_{R})$ is a zero divisor as: $$\varphi(1_{R})(\varphi(1_{R})-1_{S})s=(\varphi(1_{R})\varphi(1_{R})-\varphi(1_{R}))s=(\varphi(1_{R})-\varphi(1_{R}))s=0s=0$$

---
> [!definition] Problem 6
> Let $\varphi:R\to Q$ be a surjective ring homomorphism. Prove that there is a one-to-one correspondence between the ideals of $Q$ and the ideals of $R$ that contain $\text{ker}(\varphi)$.

Let $\mathfrak{a}\subseteq Q$ be an ideal. Then, we show that the 
1. $\varphi ^{-1}(\mathfrak{a})$ is an ideal and for $a\in \text{ker}(\varphi)$, $\varphi(a)=0\in (\mathfrak{a})$. Therefore, it is well-defined.

