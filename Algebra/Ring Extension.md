#Definition #Algebra 

> [!definition]
> Let $R,R'$ be [[Ring|rings]].
> 1. if $R'\supseteq R$, $R':R$ is a ***ring extension***.
> 2. For a ring extension $R':R$, $a\in R'$ is called ***integral*** over $R$ if there exists a monic polynomial $f\in R[x]$ with $f(a)=0$.
> 3. $R'$ is ***integral*** over $R$ if every element $a\in R'$ is integral over $R$.
- **Related definition**: A ring extension $R':R$ is called ***finite*** if $R'$ is finitely generated as a $R$-[[module]].
---
##### Examples
> [!h] Example 1 (UFD)
> Let $R$ be a [[Unique Factorization Domain|UFD]] and $R':=\text{Quot}R$. Then, 
> 1. $a\in R'$ is integral over $R$ if and only if $a\in R$.

> [!proof]+
> We have:
> 1. if $a\in R$, then obviously it is integral. Conversely, assume that $a=\frac{p}{q}$ is integral over $R$ with $p,q$ coprime, i.e. there exists: $$\left( \frac{p}{q} \right)^n+c_{n-1}\left( \frac{p}{q} \right) ^{n-1}+\dots+c_{0}=0$$with $c_{0},\dots,c-$