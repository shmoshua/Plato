#Definition #Algebra

> [!definition]
> For a commutative [[ring]] $R$, an [[Ideal (Ring)|ideal]] $I\unlhd  R$ is a ***prime ideal***, if one of the following equivalent conditions hold:
> 1. $R / I$ is an [[integral domain]] or
> 2. $I\neq R$ and if $ab\in I$ then $a\in I$ or $b\in I$ for all $a,b\in R$.

^c90dca

- **Related definition**: The set of all prime ideals is called the ***spectrum*** of $R$, denoted as $\text{Spec } R$. ^347456
---
##### Properties
> [!lemma] Theorem 1 (Equivalent Definitions of Prime Ideals)
> For a commutative ring $R$ and an ideal $I\unlhd R$, TFAE:
> 1. $R / I$ is an integral domain.
> 2. $I\neq R$ and if $ab\in I$ then $a\in I$ or $b\in I$ for all $a,b\in R$.

^22f699

> [!proof]-
> We have that:
> 1. (1=>2): If $R / I$ is an integral domain, $R / I\neq(0)$ and therefore, $I \neq R$. Further, for $a,b\in R$ with $ab\in I$, we have that: $$(a+I)(b+I)=(ab+I)=I$$Therefore, $(a+I)=I$ or $(b+I)=I$, which proves the statement.
> 2. (2=>1): From $I\neq R$, $R / I\neq(0)$. Let $(a+I)(b+I)=I$. Then, $ab\in I$ and $a\in I$ or $b\in I$. Therefore, $R / I$ is an integral domain.

^d667e0

---
> [!lemma] Proposition 2 (Basic Properties)
> Let $R,S$ be commutative rings, $\varphi:R\to S$ a [[Ring Homomorphism|ring homomorphsim]].
> 1. For a prime ideal $I\unlhd S$, $\varphi ^{-1}(I)\unlhd R$ is a prime ideal.
> 2. Any prime ideal $I\unlhd R$ is radical. 

> [!proof]-
> We have:
> 1. We first show that $\varphi ^{-1}[\mathfrak{p}]\neq R$. If $\varphi ^{-1}[\mathfrak{p}]=R$, $1_{R}\in \varphi ^{-1}[\mathfrak{p}]$ and therefore, $1_{S}=\varphi(1_{R})\in \mathfrak{p}$. Therefore, $\mathfrak{p}=S$ and $\mathfrak{p}$ is not a prime ideal.
> 
> 	Let $a,b\in R$ s.t. $a\cdot b\in \varphi ^{-1}[\mathfrak{p}]$. Then, $\varphi(a\cdot b)=\varphi(a)\varphi(b)\in \mathfrak{p}$. As $\mathfrak{p}$ is a prime ideal, we have: $$\varphi(a)\in \mathfrak{p}\lor \varphi(b)\in \mathfrak{p}$$which shows that: $$a\in \varphi ^{-1}[\mathfrak{p}]\lor b\in \varphi ^{-1}[\mathfrak{p}]$$Therefore, by Proposition 1, $\varphi ^{-1}[\mathfrak{p}]$ is a prime ideal.
> 2. Let $a^n\in I$. Then, by the definition of prime, $a\in I$. 
---
> [!lemma] Proposition 3
> Let $R$ be a commutative ring. 
> 1. Let $I_{1},\dots,I_{n}\unlhd R$ and $P\unlhd R$ a prime ideal. If $I_{1}\cap\dots \cap I_{n}\subseteq P$, then $I_{k}\subseteq P$ for some $k\in[n]$.
> 2. Let $I\unlhd R$ and $P_{1},..,P_{n}\unlhd R$ prime ideals. If $I\subseteq P_{1}\cup\dots \cup P_{n}$, then $I\subseteq P_{k}$ for some $k\in [n]$. 

^805b27

> [!proof]-
> We have that:
> 1. Assume there exists $a_{k}\in I_{k}$ s.t. $a_{k}\notin P$ for all $k\in [n]$. Then, $\prod_{k}^{}a_{k}\in I_{i}$ for all $i\in[n]$ and $$\prod_{k}^{}a_{k}\in I_{1}\cap\dots \cap I_{n}\subseteq P$$ Hence, by prime ideal, $a_{k}\in P$ for some $k$, which is a contradiction.
> 2. We prove by induction on $n$. If $n=1$, the statement holds trivially. Let $n\geq 2$. Now, for every $i\in[n]$, 
> 	1. if $I\subseteq \bigcup_{j\neq i}^{}P_{j}$ for some $j$, then by induction hypothesis, we have the claim. 
> 	2. otherwise, choose $a_{i}\in I$ with $a_{i}\notin \bigcup_{j\neq i}^{}P_{j}$. We define: $$a:= a_{1}\dots a_{n-1}+ a_{n}$$Then, $a\in I$ but not in any of the $P_{i}$. Indeed, if $a\in P_{i}$ for some $i\leq n-1$, then $a_{n}\in P_{i}$, which is a contradiction. If $a\in P_{n}$ then $a_{1}\dots a_{n-1}\in P_{n}$.  As $P_{n}$ is prime there exists $a_{k}\in P_{n}$ for some $k\leq n-1$, which is a contradiction. 

^a47838

---
##### Examples
- For $R = \mathbb{Z}$, $m\mathbb{Z}$ is a prime ideal if and only if $m$ is prime or $m=0$. This is equivalent to $m\mathbb{Z}$ being [[Maximal Ideal|maximal]], i.e. $\mathbb{Z} / m\mathbb{Z}$ is a field.
- 