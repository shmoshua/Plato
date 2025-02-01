#Definition #Algebra 

> [!definition]
> Let $R$ be a commutative [[ring]]. 
> 1. A proper ideal $Q\unlhd R$ is called ***primary***, if for all $a,b\in R$ with $ab\in Q$, we have $a\in Q$ or $b\in \sqrt{ Q }$. 
- **Related definition**: For a primary ideal $Q$, if $P:=\sqrt{ Q }$, it is called ***$P$-primary***.
---
##### Properties
> [!lemma] Proposition 1
> Let $R$ be a ring. 
> 1. If $Q\unlhd R$ is primary, then $\sqrt{ Q }$ is prime.
> 2. $Q\unlhd R$ is primary if and only if every zero-divisor of $R / Q$ is [[Nilradical|nilpotent]]. 

> [!proof]-
> We have:
> 1. if $ab\in \sqrt{ Q }$, then $a^nb^n\in Q$ for some $n$. Hence, either $a^n\in Q$ or $b^n\in \sqrt{ Q }$. This means that $a$ or $b$ lie in $\sqrt{ Q }$. 
> 2. if $Q\unlhd R$ is primary, for every $a,b\in R$ with $\overline{a}\overline{b}=0$, $\overline{a}=0$ or $\overline{b}^n=0$. This proves the statement.
---
> [!lemma] Lemma 2 (Primary Ideals over Maximal Ideals)
> Let $P\unlhd R$ be maximal. If $Q\unlhd R$ satisfies either:
> 1. $\sqrt{ Q }=P$ or
> 2. $P^n\subseteq Q\subseteq P$ for some $n\in \mathbb{N}_{>0}$,
> 
> then $Q$ is $P$-primary.

> [!proof]+
> We have that:
> 1. If $\sqrt{ Q }=P$, then in $R / Q$ the nilradical $\sqrt{ (0) }=P / Q$. 

---
##### Examples
> [!h] Example 1
> Let $R$ be a PID. 
> 1. $Q\unlhd R$ is primary if and only if $Q=(p^n)$ for some prime $p\in R$ and $n\in \mathbb{N}_{> 0}$.

> [!proof]-
> We have:
> 1. If $ab\in (p^n)$, then $ab=cp^n$ for some $c\in R$. Now, either $p^n$ is contained in $a$, in which case $a\in(p^n)$ or there is at least one $p$ in $b$, in which case $b^n\in (p^n)$. 
>    
>    Conversely, let $I=(p^{k_{1}}_{1}\cdot\dots \cdot p^{k_{n}}_{n})$ be a primary ideal where $p_{1},\dots,p_{n}$ are distinct primes and $k_{1},\dots,k_{n}\in \mathbb{N}_{> 0}$. If $n\geq 2$, then $p^{k_{1}}_{1}\cdot(p_{2}^{k_{2}}\dots p^{k_{n} }_{n})\in I$ but neither $p^{k_{1}}_{1}\in I$ or $p_{2}^{k_{2}}\dots p^{k_{n} }_{n}\in \sqrt{ I }$.

---
> [!h] Example 2
> Let $R$ be a ring.
> 1. Every prime ideal in $R$ is primary.