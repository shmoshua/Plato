#Definition #Algebra 

> [!definition]
> Let $R$ be a commutative [[ring]]. 
> 1. A proper ideal $Q\unlhd R$ is called ***primary***, if for all $a,b\in R$ with $ab\in Q$, we have $a\in Q$ or $b\in \sqrt{ Q }$. 
- **Related definition**: For a primary ideal $Q$, if $P:=\sqrt{ Q }$, it is called ***$P$-primary***.
- **Related definition**: Let $I\unlhd R$. 
	1. A ***primary decomposition*** of $I$ is a finite collection $\{ Q_{1},..,Q_{n} \}$ of primary ideals s.t. $I=Q_{1}\cap\dots \cap Q_{n}$.
	2. A primary decomposition $\{ Q_{1},\dots,Q_{n} \}$ is called ***minimal*** if:
		1. $\bigcap_{j\neq i}^{}Q_{j}\nsubseteq Q_{i}$ for all $i$.
		2. $\sqrt{ Q_{i} }\neq \sqrt{ Q_{j} }$ for all $i\neq j$.
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
> [!lemma] Lemma 3 (Intersection of Primary Ideals)
> Let $P\unlhd R$ be prime. 
> 1. if $Q_{1},Q_{2}\unlhd R$ are $P$-primary, then $Q_{1}\cap Q_{2}$ is $P$-primary as well.

> [!proof]-
> By [[Radical (Ring)|Proposition 1.4]], we have $\sqrt{ Q_{1}\cap Q_{2} }=\sqrt{ Q_{1} }\cap \sqrt{ Q_{2} }=P$. Now, let $ab\in Q_{1}\cap Q_{2}$. Then, we know that either $a\in Q_{1}$ or $b\in P$ as well as $a\in Q_{2}$ or $b\in P$. 
> 
> If $a\in Q_{1}\cap Q_{2}$, then we are done. Otherwise, we have that $b\in P$.
---
> [!lemma] Proposition 4 (Existence of Primary Decompositions)
> Let $R$ be a ring. Then,
> 1. If $R$ is [[Noetherian and Artinian Module|Noetherian]], any ideal $I\unlhd R$ admits a primary decomposition.
> 2. if $I\unlhd R$ admits a primary decomposition, it admits a minimal primary decomposition.

> [!proof]-
> We have that:
> 1. Assume otherwise. By [[Noetherian and Artinian Module|Proposition 1]], there exists an ideal $I\unlhd R$ that is maximal among ideals without a primary decomposition. In the quotient ring $S:= R /I$, the zero ideal $I / I$ is then the only ideal without primary decomposition.
> 	
> 	Hence, as $(0)\unlhd S$ is not primary, there exists $a,b\in S$ with $ab=0$ but $a\neq 0$ and $b\notin \sqrt{ (0) }$. As $R$ is Noetherian, so is $S$ and the chain of ideals: $$\text{Ann}(b)\subseteq \text{Ann}(b ^{2})\subseteq\dots$$becomes stationary. Hence, there exists $n$ with $\text{Ann}(b^n)=\text{Ann}(b^{n+1})$. 
> 
> 	However, notice that $(a)\neq 0$ and $(b^n)\neq 0$ by our choice of $a,b$. In particular, these two ideals have primary decomposition. Therefore, we also have a primary decomposition of $(a)\cap(b^n)$ as well. But we claim that $(a)\cap(b^n)=0$: if $x\in(a)\cap(b^n)$, then $x=ca$ and $x=db^n$ for some $c,d\in S$. As $ab=0$, $0=cab=xb=db^{n+1}$ and as $d\in \text{Ann}(b^{n+1})=\text{Ann}(b^n)$, $x=db^n=0$. 
> 
> 	This is a contradiction as $(0)$ doesn't have a primary decomposition by assumption.
> 2. Let $\{ Q_{1},\dots,Q_n \}$ be a primary decomposition. Then, we can take out every primary ideal for which $\bigcap_{j\neq i}^{} Q_{j}\subseteq Q_{i}$. Further, if $\sqrt{ Q_{i} }=\sqrt{ Q_{j} }$, then we replace $Q_{i},Q_{j}$ by $Q_{i}\cap Q_{j}$ which is $\sqrt{ Q_{i} }$-primary as well by Lemma 3.
---

---
##### Examples
> [!h] Example 1
> Let $R$ be a UFD and $Q\unlhd R$ be a principal ideal. 
> 1. $Q$ is primary if and only if $Q=(p^n)$ for some prime $p\in R$ and $n\in \mathbb{N}_{> 0}$.
> 2. $Q=(p_{1}^{k_{1}}\dots p_{n}^{k_{n}})$ admits a primary decomposition: $$Q=(p_{1}^{k_{1}})\cap\dots \cap(p_{n}^{k_{n}})$$

> [!proof]-
> We have:
> 1. If $ab\in (p^n)$, then $ab=cp^n$ for some $c\in R$. Now, either $p^n$ is contained in $a$, in which case $a\in(p^n)$ or there is at least one $p$ in $b$, in which case $b^n\in (p^n)$. 
>    
>    Conversely, let $Q=(p^{k_{1}}_{1}\cdot\dots \cdot p^{k_{n}}_{n})$ be a primary ideal where $p_{1},\dots,p_{n}$ are distinct primes and $k_{1},\dots,k_{n}\in \mathbb{N}_{> 0}$. If $n\geq 2$, then $p^{k_{1}}_{1}\cdot(p_{2}^{k_{2}}\dots p^{k_{n} }_{n})\in Q$ but neither $p^{k_{1}}_{1}\in Q$ or $p_{2}^{k_{2}}\dots p^{k_{n} }_{n}\in \sqrt{ Q }$.

---
> [!h] Example 2
> Let $R$ be a ring.
> 1. Every prime ideal in $R$ is primary.
> 2. Primary ideals are not necessarily powers of prime ideals.
> 3. Powers of prime ideals are not necessarily primary ideals.
> 4. Primary decomposition is not unique.


> [!proof]-
> We have:
> 1. Obvious.
> 2. Let $R:= \mathbb{R}[x,y]$ and $Q:=(x^{2},y)$. Then, $$\sqrt{ Q }=\{ f\in \mathbb{R}[x,y]:f^n\in Q \}=(x,y)$$which is maximal. Hence, $Q$ is $(x,y)$-primary. But for $P:=(x,y)$, $$(x^{2},xy,y^{2})=P^{2}\subsetneq Q\subsetneq P= (x,y)$$
> 3. Let $R:=\mathbb{R}[x,y,z] / (xy-z^{2})$ and $P:=(\overline{x},\overline{z})\unlhd R$. Then, $P$ is prime since $R / P\cong \mathbb{R}[y]$ is an integral domain. However, $P^{2}=(\overline{x}^{2},\overline{x}\overline{z},\overline{z}^{2})$ is not primary as $\overline{x}\overline{y}=\overline{z}^{2}\in P^{2}$, but neither $\overline{x}$ nor $\overline{y}^n$ is in $P^{2}$.
> 4. Consider $I=(x^{2})\unlhd \mathbb{R}[x]$. Then, $(x^{2})$ and $(x)\cap(x^{2})$ are both valid primary decompositions of $I$.
---
> [!h] Example 3
> We have that:
> 1. In $R:=\mathbb{R}[x,y] / (x^{2}+y^{2}-1)$, $I:=(\overline{x}^{2})=(1+\overline{y})\cap(1-\overline{y})$ is the minimal primary decomposition.
> 2. In $R:=\mathbb{Z}[\sqrt{ 5 }i]$, $I:=(6)=$ 

> [!proof]+
> We have that:
> 1. $(\overline{x}^{2})=(1-\overline{y}^{2})=((1+\overline{y})(1-\overline{y}))=(1+\overline{y})\cap(1-\overline{y})$. Now, $$R / (1+\overline{y})\cong\mathbb{R}[\overline{x},\overline{y}] / (1+\overline{y})\cong\mathbb{R}[\overline{x}]$$Hence, $(1+\overline{y}),(1-\overline{y})$ are prime and hence primary.
> 2. We have that $(2),(3)$ are coprime in $R$. Hence, $(6)=(2)\cap(3)$ and this is primary decomposition. 