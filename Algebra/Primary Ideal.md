#Definition #Algebra 

> [!definition]
> Let $R$ be a commutative [[ring]]. 
> 1. A proper ideal $Q\unlhd R$ is called ***primary***, if for all $a,b\in R$ with $ab\in Q$, we have $a\in Q$ or $b\in \sqrt{ Q }$. 
- **Related definition**: For a primary ideal $Q$, if $P:=\sqrt{ Q }$, it is called ***$P$-primary***.
- **Related definition**: Let $I\unlhd R$. A ***primary decomposition*** of $I$ is a finite collection $\{ Q_{1},..,Q_{n} \}$ of primary ideals s.t. $I=Q_{1}\cap\dots \cap Q_{n}$.
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

> [!proof]-
> We have that:
> 1. If $\sqrt{ Q }=P$, then in $R / Q$ the nilradical $\sqrt{ (0) }=P / Q$, which is maximal in $R / Q$ as $P$ is maximal in $R$. Hence by [[Nilradical|Proposition 2]], every element is either unit or nilpotent. Hence, by Proposition 1.2, $Q$ is $P$-primary.
> 2. We have: $$\sqrt{ P }=\sqrt{ P^n }\subseteq \sqrt{ Q }\subseteq\sqrt{ P }$$and $\sqrt{ Q }=\sqrt{ P }=P$. So it reduces to condition 1. 
---
> [!lemma] Proposition 3 (Existence of Primary Decompositions)
> Let $R$ be a [[Noetherian and Artinian Module|Noetherian ring]]. Then,
> 1. any ideal $I\unlhd R$ admits a primary decomposition.

> [!proof]-
> Assume otherwise. By [[Noetherian and Artinian Module|Proposition 1]], there exists an ideal $I\unlhd R$ that is maximal among ideals without a primary decomposition. In the quotient ring $S:= R /I$, the zero ideal $I / I$ is then the only ideal without primary decomposition.
> 
> Hence, as $(0)\unlhd S$ is not primary, there exists $a,b\in S$ with $ab=0$ but $a\neq 0$ and $b\notin \sqrt{ (0) }$. As $R$ is Noetherian, so is $S$ and the chain of ideals: $$\text{Ann}(b)\subseteq \text{Ann}(b ^{2})\subseteq\dots$$becomes stationary. Hence, there exists $n$ with $\text{Ann}(b^n)=\text{Ann}(b^{n+1})$. 
> 
> However, notice that $(a)\neq 0$ and $(b^n)\neq 0$ by our choice of $a,b$. In particular, these two ideals have primary decomposition. Therefore, we also have a primary decomposition of $(a)\cap(b^n)$ as well. But we claim that $(a)\cap(b^n)=0$: if $x\in(a)\cap(b^n)$, then $x=ca$ and $x=db^n$ for some $c,d\in S$. As $ab=0$, $0=cab=xb=db^{n+1}$ and as $d\in \text{Ann}(b^{n+1})=\text{Ann}(b^n)$, $x=db^n=0$. 
> 
> This is a contradiction as $(0)$ doesn't have a primary decomposition by assumption.
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
> 2. Primary ideals are not necessarily powers of prime ideals.
> 3. Powers of prime ideals are not necessarily primary ideals.

> [!proof]+
> We have:
> 1. Obvious.
> 2. Let $R:= \mathbb{R}[x,y]$ and $Q:=(x^{2},y)$. Then, $$\sqrt{ Q }=\{ f\in \mathbb{R}[x,y]:f^n\in Q \}=(x,y)$$which is maximal. Hence, $Q$ is $(x,y)$-primary. But for $P:=(x,y)$, $$(x^{2},xy,y^{2})=P^{2}\subsetneq Q\subsetneq P= (x,y)$$
> 3. Let $R:=\mathbb{R}[x,y,z] / (xy-z^{2})$ and $P:=(\overline{x},\overline{z})\unlhd R$. Then, $P$ is prime since $R / P\cong \mathbb{R}[y]$ is an integral domain. However, $P^{2}=(\overline{x}^{2},\overline{x}\overline{z},\overline{z}^{2})$ is not primary as $\overline{x}\overline{y}=\overline{z}^{2}\in P^{2}$, but neither $\overline{x}$ nor $\overline{y}^n$ is in $P^{2}$.
---
