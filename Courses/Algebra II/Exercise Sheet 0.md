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
2. Firstly, we know that $\varphi ^{-1}(\mathfrak{s})$ is an ideal in $R$. Then, clearly $\varphi ^{-1}(\mathfrak{s})\neq R$ as $\mathfrak{s}\neq \mathbb{Z}$. Finally, for $a,b\in R$: $$ab\in \varphi ^{-1}(\mathfrak{s})\implies\varphi(a)\varphi(b)=\varphi(ab)\in \mathfrak{s}\implies\varphi(a)\in \mathfrak{s}\lor\varphi(b)\in \mathfrak{s}$$