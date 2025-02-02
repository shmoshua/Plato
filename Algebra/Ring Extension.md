#Definition #Algebra 

> [!definition]
> Let $R,R'$ be [[Ring|rings]].
> 1. if $R'\supseteq R$, $R':R$ is a ***ring extension***.
> 2. For a ring extension $R':R$, $a\in R'$ is called ***integral*** over $R$ if there exists a monic polynomial $f\in R[x]$ with $f(a)=0$.
> 3. $R'$ is ***integral*** over $R$ if every element $a\in R'$ is integral over $R$.
- **Related definition**: A ring extension $R':R$ is called ***finite*** if $R'$ is finitely generated as a $R$-[[module]].
- **Related definition**: For a ring extension $R':R$, the set $\overline{R}$ of all integral elements in $R'$ over $R$ is a ring called ***integral closure*** of $R$ in $R'$. $R$ is ***integrally closed in $R'$***  if $\overline{R}=R$.
- **Related definition**: An integral domain $R$ is ***integrally closed/normal*** if it is integrally closed in $\text{Quot}R$.
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
- **Corollary**: For $R':R$, the integral closure $\overline{R}$ is indeed a ring, as if $a,b\in R'$ are integral over $R$, then so is $R[a,b]$ and in particular $a+b$ and $ab$.
---
> [!lemma] Lemma 2 (Transitivity of Finite and Integral Extensions)
> Let $R'':R':R$ be ring extensions.
> 1. if $R':R$ and $R'':R'$ are finite, then so is $R'':R$.
> 2. if $R':R$ and $R'':R'$ are integral, then so is $R'':R$.

> [!proof]-
> We have:
> 1. Let $a_{1},\dots,a_{n}$ generate $R'$ as a $R$-module and $b_{1},\dots,b_{m}$ generate $R''$ as a $R'$-module. Then, every element in $R''$ is of the form $\sum_{i=1}^{m}c_{i}b_{i}$ for some $c_{i}\in R'$ and $\sum_{i=1}^{m}\sum_{j=1}^{n}c_{ij}a_{j}b_{i}$ for some $c_{ij}\in R$. Hence, $a_{j}b_{i}$ generate $R''$ as a $R$-module.
> 2. Let $a\in R''$. As $a$ is integral over $R'$, there is $n\in \mathbb{N}_{> 0}$ and $c_{0},\dots,c_{n-1}\in R'$ s.t. $a^n+c_{n-1}a^{n-1}+\dots+c_{0}=0$. Then, $a$ is integral over $R[c_{0},\dots,c_{n-1}]$. Further, as $c_{0},\dots,c_{n-1}$ are integral over $R$, by Proposition 1 $R[c_{0},\dots,c_{n-1},a]$ is finite over $R[c_{0},\dots,c_{n-1}]$ and $R[c_{0},\dots,c_{n-1}]$ is finite over $R$. 
>    
>    Therefore, by 1, $R[c_{0},\dots,c_{n-1},a]$ is finite over $R$ and $a$ is integral over $R$ by Proposition 1. 
---
> [!lemma] Lemma 3 (Properties of Integral Ring Extensions)
> Let $R':R$ be an integral ring extension.
> 1. if $I\unlhd R'$, then $(R' /I):R/(I\cap R)$ is an integral ring extension.
> 2. if $S$ is multiplicatively closed in $R$, then $S^{-1}R': S^{-1}R$ is an integral ring extension.
> 3. $R'[x]:R[x]$ is an integral ring extension.


> [!proof]-
> We have:
> 1. Note that $R / (I\cap R)\to R'  / I,\overline{a}\to \overline{a}$ is injective hence it is a ring extension. Now, for any $a\in R'$, we have $a^n+c_{n-1}a^{n-1}+\dots+c_{0}=0$ for some $c_{0},\dots,c_{n-1}\in R$. Hence by passing to the quotient, $$\overline{a}^n+\overline{c_{n-1}}\overline{a}^{n-1}+\dots+\overline{c_{0}}=0$$So $a$ is integral over $R / (I\cap R)$.
> 2. The ring homomorphism $S^{-1}R\to S^{-1}R', \frac{a}{ s}\mapsto \frac{a}{s}$ is well defined and injective. For $\frac{a}{s}\in S^{-1}R'$, we have the monic relation $a^n+c_{n-1}a^{n-1}+\dots+c_{0}=0$. Therefore, $$\left( \frac{a}{s} \right)^n+\frac{c_{n-1}}{s}\left( \frac{a}{s} \right) ^{n-1}+\dots+\frac{c_{0}}{s^n}=0$$Hence, $\frac{a}{s}$ is integral over $S^{-1}R$.
> 3. Let $f=a_{n}x^n+\dots+a_{0}\in R'[x]$. Then, as $a_{0},\dots,a_{n}$ are integral over $R$, it is also integral over $R[x]$. Therefore, $R[x][a_{0},\dots,a_{n}]=R[a_{0},\dots,a_{n}][x]$ is integral over $R[x]$ by Proposition 1. This means that $f$ is integral over $R[x]$. 
---
> [!lemma] Lemma 4 (Properties of Integral Closures)
> Let $R$ be an integral domain and $S\subseteq R$ a multiplicatively closed subset. 
> 1. Let $R':R$ be a ring extension and $\overline{R}$ the integral closure. Then, $S^{-1}\overline{R}$ is the integral closure of $S^{-1}R$ in $S^{-1}R'$. 
> 2. If $R$ is normal, then $S^{-1}R$ is normal.
> 3. If $R_{P}$ is normal for all maximal $P\unlhd R$, then $R$ is normal.
> 4. for $R':R$ a ring extension with an integral domain $R'$, for any two monic $f,g\in R'[x]$ with $fg\in \overline{R}[x]$, we have $f,g\in \overline{R}[x]$.

> [!proof]-
> We have:
> 1. Let $a\in R'$ be integral. Then, $a^n+c_{n-1}a^{n-1}+\dots+c_{0}=0$ for some $c_{0},\dots,c_{n-1}\in R$ and similarly as Lemma 3.2, we have that $\frac{a}{s}$ is integral over $S^{-1}R$ for all $s\in S$. 
>    
>    Similarly, for every $\frac{a}{s}\in \overline{S^{-1}R}$, we have that $f\left( \frac{a}{s} \right):=\left( \frac{a}{s} \right)^n+d_{n-1}\left( \frac{a}{s} \right)^{n-1}+\dots+d_{0}=0$ for $d_{0},..,d_{n-1}\in S^{-1}R$. Now, let $u\in S$ s.t. $u\cdot f\in R[x]$. Then, $$u^n\cdot f(x)=u^nx^n+a_{n-1} u^{n-1}x^{ n-1}+\dots+a_{0}=g(ux)$$for $g(x)=x^n+c_{n-1}x^{n-1}+\dots+c_{0}\in R[x]$. Now, $$g\left(  u \frac{a}{s} \right)=u^n\cdot f\left( \frac{a}{s} \right)=0$$Hence, $\frac{ua}{s}\in \overline{R}$ and $\frac{ua}{us}=\frac{a}{s}\in S^{-1}\overline{R}$.
> 2. Let $R$ be integrally closed in $\text{Quot}R$. Then, $\overline{R}=R$. Hence, $$S^{-1}R=S^{-1}\overline{R}=\overline{S^{-1}R}$$from 1. 
> 3. Let $\frac{a}{s}\in \text{Quot}R$ be integrally over $R$. Then, $$\left( \frac{a}{s} \right) ^n+c_{n-1}\left( \frac{a}{s} \right) ^{n-1}+\dots+c_{0}=0$$for some $c_{0},\dots,c_{n-1}\in R$. We want to show that $x\in R$. 
> 4. 
---
> [!lemma] Lemma 5
> Let $R':R$ be an integral extension of integral domains and assume $R$ is normal.
> 1. for any $a\in R'$ its [[minimal polynomial]] $f$ over $K:=\text{Quot }R$ has coefficients in $R$.
> 2. if $a\in PR'$ for some prime $P\unlhd R$, then all non-leading coefficients of $f$ are contained in $P$.

> [!proof]-
> We have:
> 1. As $a$ is integral over $R$, there is a monic polynomial $g\in R[x]$ with $g(a)=0$. Then, $g\in K[x]$ with $g(a)=0$. Hence, by [[Algebraic and Transcendental Element|Proposition 2]], $f|g$ in $K[x]$, i.e. $g=fh$ in $K[x]$. Hence, by Lemma 4.4, $fh=g\in \overline{R}[x]=R[x]$. Therefore, $f\in R[x]$. 
> 2. Let $a=p_{1}a_{1}+\dots+p_{k}a_{k}$ for some $p_{1},..,p_{k}\in P$ and $a_{1},\dots,a_{k}\in R'$. By replacing $R'$ by $R[a_{1},\dots,a_{k}]$ we may assume that $R'$ is finite over $R$. Hence, we can apply [[Module|Cayley Hamilton]] and define $\varphi:R'\to R',x\mapsto ax$. We get: $$\varphi^n+c_{n-1}\varphi^{n-1}+\dots+c_{0}=0$$with $c_{n-1},\dots,c_{0}\in P$. By plugging $x=1$, we get that $g(a):=a^n+c_{n-1}a^{n-1}+\dots+c_{0}=0$. 
>    
>    As $g(a)=0$, $f|g$ in $K[x]$ again and $g=fh$ in $R[x]$ (by 1). Modulo $P$, we get that $\overline{x}^n=\overline{f}\cdot \overline{h}$ in $(R / P)[x]$. However, $R / P$ is an integral domain and this is only possible if $\overline{f}$ and $\overline{h}$ are powers of $\overline{x}$ themselves. Hence, the non-leading coefficients of $f$ lie in $P$.

---
##### Examples
> [!h] Example 1 (UFD)
> Let $R$ be a [[Unique Factorization Domain|UFD]] and $R':=\text{Quot}R$. Then, 
> 1. $a\in R'$ is integral over $R$ if and only if $a\in R$, i.e. $R$ is normal.

> [!proof]-
> We have:
> 1. if $a\in R$, then obviously it is integral. Conversely, assume that $a=\frac{p}{q}$ is integral over $R$ with $p,q$ coprime, i.e. there exists: $$\left( \frac{p}{q} \right)^n+c_{n-1}\left( \frac{p}{q} \right) ^{n-1}+\dots+c_{0}=0$$with $c_{0},\dots,c_{n-1}\in R$. We multiply it with $q^n$ and get: $$p^n=-c_{n-1}p^{n-1}q-\dots-c_{0}q^n=-q(c_{n-1}p^{n-1}+\dots+c_{0}q^{n-1})$$and $q|p^n$. As $p$ and $q$ are coprime, we have that $q$ is a unit and $a\in R$.