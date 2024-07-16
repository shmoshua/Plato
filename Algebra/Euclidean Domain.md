#Definition #Algebra
> [!definition]
> An [[integral domain]] $R$ is ***euclidean***, if there exists a map $N:R \backslash \{ 0 \}\to \mathbb{N}$ s.t. for all $a\in R,b\in R\backslash\{ 0 \}$, there exists $q,r\in R$ with:
> 1. $a=qb+r$ and 
> 2. $r=0$ or $N(r)<N(b)$
> 
> Then, $q$ is the ***quotient*** and $r$ is the ***remainder***.
---
##### Properties
> [!lemma] Theorem 1
> Every euclidean domain is a [[Principal Ideal Domain|principal ideal domain]].

> [!proof]-
> Let $R$ be euclidean and $I\unlhd R$ a non-zero ideal. Then, we choose: $$b\in\arg\min_{c\in I} N(c) $$We will show that $I=(b)$. Let $a\in I$. Then, we have that $a=qb+r$ for some $q,r\in R$. As $a,qb\in I$, we have that $r\in I$ and by the minimality, $r=0$. Therefore, $a=qb$ and $I\subseteq(b)$.

- **Remark**: $R=\left\{  a+b \left( \frac{1+\sqrt{ -19 }}{2} \right) |a,b\in \mathbb{Z} \right\}$ is a PID but not a euclidean domain.
---
> [!lemma] Theorem 2 (Euclidean Algorithm)
> Let $R$ be an euclidean domain and $a,b\in R \backslash\{ 0 \}$. Further, let $r_{n}$ be the last non-zero remainder in the Euclidean algorithm with $a,b$. Then, 
> 1. $r_{n}=\gcd(a,b)$

> [!proof]-
> By Euclidean algorithm, we have that: $$\begin{align}a&=q_{0}b+r_{0}\\b&=q_{1}r_{0}+r_{1}\\r_{0}&=q_{2}r_{1}+r_{2}\\ &\quad \vdots\\r_{n-2}&=q_{n}r_{n-1}+r_{n}\\r_{n-1}&=q_{n+1}r_{n}\end{align}$$where $r_{0},\dots,r_{n}$ are non-zero. Then,
> 
> As $R$ is also a PID by Theorem 1, it suffices to show that $(a,b)=(r_{n})$ by [[Principal Ideal Domain|Theorem 2]].
> 1. By induction, we get that $r_{n}|b$ and $r_{n}|a$. Therefore, $(a,b)\subseteq(r_{n})$.
> 2. We have that $r_{0}\in (a,b)$. Then, $r_{1}=b-q_{1}r_{0}\in (a,b)$. We can inductively continue to get that $r_{n}\in (a,b)$. Hence, $(r_{n})\subseteq(a,b)$.
> 
> Therefore, $(a,b)=(r_{n})$.
---
##### Examples
> [!h] Example 1
> Let $F$ be a field. The following are euclidean domains:
> 1. $F$ with $N(a):=0$
> 2. $F[x]$ with $N(f):=\text{deg}(f)$
> 3. $\mathbb{Z}$ with $N(a):=\left| a \right|$
> 4. $\mathbb{Z}[i]$ with $N(a+bi)=a^{2}+b ^{2}$
---