#Definition #Algebra 

> [!definition]
> Let $R,R'$ be [[Ring|rings]].
> 1. if $R'\supseteq R$, $R':R$ is a ***ring extension***.
> 2. For a ring extension $R':R$, $a\in R'$ is called ***integral*** over $R$ if there exists a monic polynomial $f\in R[x]$ with $f(a)=0$.
> 3. $R'$ is ***integral*** over $R$ if every element $a\in R'$ is integral over $R$.
- **Related definition**: A ring extension $R':R$ is called ***finite*** if $R'$ is finitely generated as a $R$-[[module]].
---
##### Properties
> [!lemma] Proposition 1 (Integral and Finite Ring Extensions)
> For a ring extension $R':R$, TFAE:
> 1. $R':R$ is finite.
> 2. $R'=R[a_{1},\dots,a_{n}]$ for integral elements $a_{1},\dots,a_{n}\in R'$ over $R$.
>    
> In this case, $R'$ is integral over $R$.

> [!proof]-
> We have that:
> 1. (1=>2): Let $R'=\braket{ a_{1} ,\dots a_{n}  }$ as a $R$-module. Then, $R'=R[a_{1},\dots,a_{n}]$. We show that $R'$ is integral over $R$. 
>    
>    Let $a\in R'$. As $R'$ is finite over $R$, by [[Module|Cayley Hamilton]] to $\varphi:R'\to R',x \mapsto ax$. Then, there exists a monic polynomial $\chi\in R[x]$ with non-leading coefficients in $R$ s.t. $\chi(\varphi)=0$, i.e. $$\varphi^k+c_{k-1}\varphi^{k-1}+\dots+c_{0}=0$$where $c_{0},\dots,c_{k-1}\in R$. Hence, by letting $x=1$, $$a^k+c_{k-1}\varphi^{k-1}+\dots+c_{0}=0$$
>  2. (2=>1): Let $R'=R[a_{1},..,a_{n}]$ with $a_{1},..,a_{n}$ integral over $R$. Then, every element $a\in R'$ is a polynomial expression of the form $$\sum_{k_{1},\dots,k_{n}}^{}c_{k_{1}\dots k_{n}}a_{1}^{k_{1}}\dots a_{n}^{k_{n}}$$for some $c_{k_{1}\dots k_{n}}\in R$ and $k_{i}<r_{i}$ where $r_{i}$ denotes the degree of the minimal polynomial of $a_{i}$. Hence, $R'$ is finitely generated over $R$ by all monomial expressions $a_{1}^{k_{1}}\dots a_{n}^{k_{n}}$ with $k_{i}<r_{i}$. 

---
> [!lemma] Lemma 2 (Transitivity of Finite and Integral Extensions)
> Let $R'':R':R$ be ring extensions.
> 1. if $R':R$ and $R'':R'$ are finite, then so is $R'':R$.
> 2. if $R':R$ and $R'':R'$ are integral, then so is $R'':R$.

---
##### Examples
> [!h] Example 1 (UFD)
> Let $R$ be a [[Unique Factorization Domain|UFD]] and $R':=\text{Quot}R$. Then, 
> 1. $a\in R'$ is integral over $R$ if and only if $a\in R$.

> [!proof]-
> We have:
> 1. if $a\in R$, then obviously it is integral. Conversely, assume that $a=\frac{p}{q}$ is integral over $R$ with $p,q$ coprime, i.e. there exists: $$\left( \frac{p}{q} \right)^n+c_{n-1}\left( \frac{p}{q} \right) ^{n-1}+\dots+c_{0}=0$$with $c_{0},\dots,c_{n-1}\in R$. We multiply it with $q^n$ and get: $$p^n=-c_{n-1}p^{n-1}q-\dots-c_{0}q^n=-q(c_{n-1}p^{n-1}+\dots+c_{0}q^{n-1})$$and $q|p^n$. As $p$ and $q$ are coprime, we have that $q$ is a unit and $a\in R$.