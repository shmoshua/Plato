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
- **Related definition**: Let $I\unlhd R$. 
	1. An ***associated prime ideal*** of $I$ is a prime ideal that can be written as $\sqrt{ I{:}a }$ for some $a\in R$. The set of associated prime ideals of $I$ is denoted $\text{Ass}(I)$.
	2. The minimal elements of $\text{Ass}(I)$ are called ***isolated prime ideals*** of $I$. The others are called ***embedded prime ideals*** of $I$.
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
> [!lemma] Lemma 5
> Let $Q$ be a $P$-primary ideal in $R$. Then, for any $a\in R$, 
> $$\sqrt{ Q{:}a }=\begin{cases}R&a\in Q\\P&a\notin Q\end{cases}$$

> [!proof]-
> We have that:
> 1. if $a\in Q$, then $Q{:}a=R$ and therefore $\sqrt{ Q{:}a }=R$. 
>    
>    if $a\notin Q$, then for any $b\in Q{:}a$, $ab\in Q$ and we have that $b\in P$ as $Q$ is $P$-primary. Hence, $Q\subseteq Q{:a}\subseteq P$ and by taking radicals, $P\subseteq \sqrt{ Q{:}a }\subseteq P$. 
---
> [!lemma] Theorem 6 (First Uniqueness Theorem for Primary Decompositions)
> Let $Q_{1},\dots,Q_{n}$ form a minimal primary decomposition for $I\unlhd R$. Let $P_{i}:=\sqrt{ Q_{i} }$. 
> 1. $\{ P_{1},\dots,P_{n} \}=\text{Ass}(I)$.

> [!proof]-
> We have:
> 1. ($\subseteq$): Let $i\in[n]$. We will show that $P_{i}\in \text{Ass}(I)$. As the decomposition is minimal, we can find $a\in \bigcap_{j\neq i}^{}Q_{j}$ with $a\notin Q_{i}$. Then, $$\begin{align} \sqrt{ I{:}a }&=\sqrt{ Q_{1}{:}a\cap\dots \cap Q_{n}{:}a}\\&=\sqrt{ Q_{1}{:}a }\cap\dots \cap\sqrt{ Q_{n}{:}a }\\&=P_{i}\end{align}$$by Lemma 5. Hence, $P_{i}\in \text{Ass}(I)$.
> 2. ($\supseteq$): Let $P\in \text{Ass}(I)$, i.e. $P=\sqrt{ I{:}a }$ for some $a\in R$. Then, as above, $$P=\sqrt{ I{:}a }=\sqrt{ Q_{1}{:}a }\cap\dots \cap \sqrt{ Q_{n}{:}a }$$. Hence, by [[Prime Ideal|Proposition 3]], $P\supseteq \sqrt{ Q_{i}{:}a }$ for some $i$ since $P$ is prime. However, as we have $P\subseteq \sqrt{ Q_{i}{:}a }$, we get $P=\sqrt{ Q_{i}{:}a }$. As by Lemma 5, $\sqrt{ Q_{i}:a }$ can only be $R$ or $P_{i}$, we get that $P_{i}=P$. 

- **Corollary**: the number of components in the minimal primary decomposition is independent of the decomposition.
---
> [!lemma] Lemma 7
> Let $S$ be a multiplicatively closed subset of $R$ and $Q$ a $P$-primary ideal. Then, w.r.t. $\varphi:R\to S^{-1}R, a\mapsto \frac{a}{1}$, $$(Q^e)^c=\begin{cases}R&S\cap P\neq \varnothing\\Q&S\cap P=\varnothing\end{cases}$$

> [!proof]-
> We have:
> 1. if $S\cap P\neq \varnothing$, then there exists $s\in S$ with $s\in \sqrt{ Q }$, i.e. $s^n\in Q$ for some $n\in \mathbb{N}$. Hence, by [[Localization|Proposition 2]], $$1=\frac{s^n}{s^n}\in S^{-1}Q=Q^e$$Therefore, $Q^e=S^{-1}R$ and $(Q^e)^c=R$.
> 2. if $S\cap P=\varnothing$, then by [[Ring Homomorphism|Proposition 4]], it suffices to show that $(Q^e)^c\subseteq Q$. If $a\in (Q^e)^c$, then $\frac{a}{1}\in Q^e$ and $\frac{a}{1}=\frac{q}{s}$ for some $q\in Q$ and $s\in S$. Hence, $u(as-q)=0$ for some $u\in S$ and this implies that $a\cdot us=uq\in Q$. As $Q$ is $P$-primary, $a\in Q$ or $us\in P$. However, if $us\in P$, then $us\notin S$, which is a contradiction. Hence, $a\in Q$.
---
> [!lemma] Theorem 8 (Second Uniqueness Theorem for Primary Decompositions)
> Let $Q_{1},\dots,Q_{n}$ form a minimal primary decomposition for $I\unlhd R$. Let $P_{i}:= \sqrt{ Q_{i} }$.
> 1. if $P_{i}$ is minimal over $I$, then $(I^e)^c=Q_{i}$ w.r.t. $\varphi :R\to R_{P_{i}}$

> [!proof]-
> By localizing $I=Q_{1}\cap\dots \cap Q_{n}$, we have: $$S^{-1}I=S^{-1}Q_{1}\cap\dots \cap S^{-1}Q_{n}$$Hence, $I^e=Q_{1}^e\cap\dots \cap Q_{n}^e$ by [[Localization|Proposition 2]]. Therefore, by [[Ring Homomorphism|Proposition 4.4]], $$(I^e)^c=(Q_{1}^e)^c\cap\dots \cap(Q_{n}^e)^c=Q_{i}$$where the last step follows as $P_{i}$ is minimal over $I$ and $S:= R \backslash P_{i}$. Therefore, $S\cap P_{j}=\varnothing$ if and only if $j=i$ from Lemma 7.
- **Corollary**: the primary components in the minimal primary decomposition corresponding to minimal prime ideals are independent of the decomposition.
---
##### Primary Decompositions and Noetherian Rings
> [!lemma] Proposition 1
> Let $R$ be a Noetherian ring and $I\unlhd R$.
> 1. $\text{Ass}(I)=\{ P\unlhd R:P\text{ prime, }P=I{:}a\text{ for some }a\in R  \}$
> 2. the isolated prime ideals of $I$ are exactly the minimal prime ideals containing $I$. 

> [!proof]-
> We have:
> 1. As $R$ is Noetherian, by Proposition 4, $I$ admits a minimal primary decomposition $I=Q_{1}\cap\dots \cap Q_{n}$. Hence, by Theorem 6, $\text{Ass}(I)=\{ P_{1},\dots,P_{n} \}$ where $P_{i}:=\sqrt{ Q_{i} }$. 
>    
>    Now, let $P\unlhd R$ prime s.t. $P=I{:}a$ for some $a\in R$. Then, as all prime ideals are radical, $P=\sqrt{ I:a }$. This shows that $P\in \text{Ass}(I)$. 
>    
>    Let $i\in [n]$. We will show that $P_{i}=I{:a}$ for some $a\in R$. Let $K_{i}:=\bigcap_{j\neq i}^{}Q_{j} \backslash Q_{i}$. Then, as $R$ is Noetherian, there exists a maximal element in $\{ I{:}a \}_{a\in K_{i}}$. Let $b\in K_{i}$ for which we get a maximal element. Then, $$I{:}b=Q_{1}{:}b\cap\dots \cap Q_{n}{:}b=Q_{i}{:}b \subseteq P_{i}$$Now, we show that $I{:}b$ is prime. Let $cd\in I{:}b$ with $c\notin I{:}b$. Then, $bcd\in I$ and $d\in I{:}bc$. Notice that $bc\in Q_{j}$ for all $j\neq i$. Further, we have $bc\notin Q_{i}$ as $c\notin Q_{i}{:}b=I {:} b$. Hence, $bc\in K_{i}$ and as $(I{:}b)\subseteq (I{:}bc)$ by maximality, $(I{:}b)=(I{:}bc)$ and $d\in I{:}b$. 
>    
>    Hence, $Q_{i}\subseteq Q_{i}{:}b =I{:} b$, $P_{i}\subseteq \sqrt{ I{:}b }=I{:}b\subseteq P_{i}$. This shows the statement.
> 2. As $R$ is Noetherian, there exists a minimal primary decomposition $I=Q_{1}\cap\dots \cap Q_{n}$. We then set $P_{i}:=\sqrt{ Q_{i} }$. 
>    
>    If $P\supseteq I$ is any prime ideal, then $P\supseteq Q_{1}\cap\dots \cap Q_{n}$ and by [[Prime Ideal|Proposition 3.1]], $Q_{i}\subseteq P$ for some $i$. Hence, $P_{i}\subseteq P$ by taking radicals. 
>    1. Let $P_{i}\in \text{Ass}(I)$ be isolated. If $P$ is any prime ideal with $I\subseteq P\subseteq P_{i}$, then from above $P_{j}\subseteq P\subseteq P_{i}$ for some $j$. But as $P_{i}$ is isolated, $P_{j}=P_{i}$. Hence, $P=P_{i}$. Hence, $P_{i}$ is minimal over $I$.
>    2. Let $P$ be minimal over $I$. Then, by above, $I\subseteq Q_{i}\subseteq P_{i}\subseteq P$ for some $i$. As $P_{i}$ is minimal, we have that $P_{i}=P$. 
- **Corollary**: Isolated prime ideals of an ideal $I\unlhd A(X)$ correspond exactly to maximal subvarieties. 
 
---
> [!lemma] Lemma 2 (Symbolic Powers)
> Let $R$ be a ring. For a prime $P\unlhd R$, consider the ideal: $$P^{(n)}:=\{ a\in R:ab\in P^n\text{ for some }b\in R \backslash P \}$$called the ***$n$-th symbolic power*** of $P$. Then, 
> 1. $P^n\subseteq P^{(n)}\subseteq P$.
> 2. $P^{(n)}$ is $P$-primary.
> 3. $P^{(n)}R_{P}=P^nR_{P}$

> [!proof]-
> We have that:
> 1. The first inclusion is obvious by taking $b=1$. For the second, let $a\in P^{(n)}$. Then, $ab\in P^n\subseteq P$ for some $b\in R \backslash P$. Hence, $a\in P$.
> 2. Taking radicals we get that $P=\sqrt{ P }=\sqrt{ P^n }\subseteq \sqrt{ P^{(n)} }\subseteq \sqrt{ P }=P$. Hence, $\sqrt{ P^{(n)} }=P$. To see that it is primary, let $ab\in P^{(n)}$, i.e. $abc\in P^{n}$ for some $c\in R \backslash P$. If $b\notin  \sqrt{ P^{(n)} }=P$, then we also have $bc\notin P$ and therefore, $a\in P^{(n)}$. 
> 3. For $\subseteq$, let $\frac{b}{s}\in P^{(n)}R_{P}$ i.e. $bc\in P^n$ for some $s,c\in R \backslash P$. Then, $$\frac{b}{s}=\frac{bc}{sc}\in P^n R_{P}$$The other inclusion is obvious as $P^n\subseteq P^{(n)}$.

---
> [!lemma] Theorem 3 (Krull's Principal Ideal Theorem)
> Let $R$ be a Noetherian ring and $a\in R$. 
> 1. for every minimal prime ideal $P$ over $(a)$, $\text{codim}P\leq 1$.
> 2. if $a$ is not a zero-divisor, then for every minimal prime ideal $P$ over $(a)$, $\text{codim}P=1$.

> [!proof]-
> We have:
> 1. Let $Q'\subseteq Q\subsetneq P$ be a chain of prime ideals in $R$. We have to prove that $Q'=Q$. 
> 
> 	We first prove it for the case where $Q'=0$ and $R$ is [[Local Ring|local]] with $P$ as the unique maximal ideal. Consider the symbolic powers $Q^{(n)}$ of $Q$. Then, $Q^{(n+1)}\subseteq Q^{(n)}$. Further, 
> 	1. **Claim 1: $Q^{(n)}\subseteq Q^{(n+1)}+(a)$ for some $n$**: 
>    The ring $R / (a)$ is Noetherian by [[Noetherian and Artinian Module|Lemma 2]] and of dimension 0 since the unique maximal ideal $P / (a)$ is also minimal by assumption. Hence, $R / (a)$ is Artinian by [[Noetherian and Artinian Module|Hopkins]] and the descending chain: $$(Q^{(0)}+(a)) / (a)\supseteq (Q^{(1)}+(a)) / (a)\supseteq \dots$$becomes stationary. Hence, $Q^{(n+1)} + (a) = Q^{(n)}+(a)$ for some $n$, which implies the claim. 
> 	1. **Claim 2: $Q^{(n)}=Q^{(n+1)}+PQ^{(n)}$.** 
>    The inclusion $\supseteq$ is clear. For the converse, if $b\in Q^{(n)}$, then $b=c+ar$ for some $c\in Q^{(n+1)}$ and $r\in R$ from Claim 1. So $ar=b-c\in Q^{(n)}$. But as $P$ is minimal over $(a)$, $a\notin Q$ and as $Q^{(n)}$ is $Q$-primary, we have that: $r\in Q^{(n)}$. This means $b\in Q^{(n+1)}+PQ^{(n)}$.
>  
> 	 Now, taking the quotient by $Q^{(n+1)}$, we have $Q^{(n)} / Q^{(n+1)}=PQ^{(n)} / Q^{(n+1)}=P(Q^{(n)} / Q^{(n+1)})$. As $R$ is local and $Q^{(n)} / Q^{(n+1)}$ is a finitely generated module over $R$, by [[Local Ring|Nakayama]], $$Q^{(n)} / Q^{(n+1)}=0$$and $Q^{(n)}=Q^{(n+1)}$. Therefore, by Lemma 2, $Q^n R_{Q}=Q^{(n)}R_{Q}=Q^{(n+1)}R_{Q}=Q^{n+1}R_{Q}$. Hence, $$Q^n R_{Q}=(QR_{Q})(Q^n R_{Q})$$by [[Ring Homomorphism|Proposition 4.3]]. Now, using Nakayama again, $Q^n R_{Q}=0$. However, as $R$ is an integral domain, this is only possible if $Q=0$.
>  
> 	 Now, assume $Q'\subseteq Q\subsetneq P$ is general. Then,
> 
> 	1. Consider $R / Q'$ and we have $0\subseteq Q / Q'\subsetneq P / Q'$ where $R / Q'$ is a Noetherian ring
> 	2. Consider $(R / Q')_{P}\cong R_{P} / Q'_{P}$ which is local Noetherian ring and we have $0\subseteq Q_{P} / Q_{P}'\subsetneq P_{P} / Q'_{P}$ where the last ideal is the only maximal ideal.
>    
> 	 Hence, by above, $Q_{P} / Q'_{P}=0$ and $Q / Q'=0$. This shows that $Q=Q'$. 
> 2. Let $P_{1},\dots,P_{n}$ be minimal prime ideals over the zero ideal. Then, by Proposition 1, they are in $\text{Ass}(0)$, i.e. there exists non-zero $b_{i}\in R$ s.t. $P_{i}=\sqrt{ 0:b_{i} }$. 
>    
>    We claim that $a\notin P_{i}$ for all $i=1,\dots,n$: If $a\in P_{i}$ then $a\in \sqrt{ 0:b_{i} }$ and $a^rb_{i}=0$ for some $r\geq 0$. If we choose $r$ to be minimal, then, $a(a^{r-1}b_{i})=0$, which is a contradiction as $a$ is not a zero divisor and $a^{r-1}b_{i}\neq 0$.
>    
>    So $a\notin P_{i}$ for all $i$ but $a\in P$. Hence, $P$ cannot be any of the minimal prime ideals. Hence, $P$ must strictly contain one of the $P_{i}$'s. Therefore, $\text{codim}P\geq 1$ and with 1, we have the statement.
---
> [!lemma] Corollary 4 
> Let $R$ be a Noetherian ring and $P_{0}\subsetneq \dots \subsetneq P_{n}$ be a chain of prime ideals with $a\in P_{n}$.
> 1. there exists a chain of prime ideals $P'_{0}\subsetneq \dots \subsetneq P'_{n-1}\subsetneq P_{n}$ s.t. $a\in P'_{1}$.

> [!proof]-
> We can show this by induction over $n$.
> 1. If $n=1$, then the statement is trivially true. 
> 2. if $n\geq 2$, we have that $(a)\subseteq P_{n}$. However, as $\text{codim}P_{n}\geq n$, $P_{n}$ cannot be minimal over $(a)$. Let $(a)\subseteq P'_{n-1}\subsetneq P_{n}$ and by localizing with $P'_{n-1}$, $$(P_{0})_{P'_{n-1}}\subsetneq \dots \subsetneq (P_{n-1})_{P'_{n-1}}$$
>    
>    we have a chain $P'_{0}\subsetneq \dots \subsetneq P'_{n-1}$ with $a\in  P'_{n-1}$. 
---
> [!lemma] Theorem 5 (Krull's Principal Ideal Theorem, general)
> Let $R$ be a Noetherian ring and $a_{1},\dots,a_{n}\in R$. 
> 1. for every minimal prime ideal $P$ over $(a_{1},\dots,a_{n})$, $\text{codim}P\leq n$.

> [!proof]-
> By induction on $n$. 
> 1. if $n=1$, shown by Theorem 3.
> 2. if $n\geq 2$, let $P_{0}\subsetneq\dots \subsetneq P_{s}$ be a chain of prime ideals in $P$. By Corollary we may wlog assume that $a\in P_{1}$. But then, $$P_{1} / (a_{n})\subsetneq \dots \subsetneq P_{s} / (a_{n})$$is a chain of prime ideals of length $s-1$ in $P / (a_{n})$. As $P / (a_{n})$ is minimal over $(\overline{a_{1}},\dots,\overline{a_{n-1}})$, by induction we have that $s-1\leq \text{codim}P / (a_{n})\leq n-1$ and $s\leq n$.
>    
>    However, as the chain was arbitrary $\text{codim}P\leq n$.

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
> 2. In $R:=\mathbb{Z}[\sqrt{ 5 }i]$, $I:=(6)=(2)\cap(3)$.
> 3. In $R:=\mathbb{R}[x,y]$, $I:=(y)\cdot(x,y)=(y)\cap(x^{2},xy,y^{2})=(y)\cap(x,y^{2})$.

> [!proof]-
> We have that:
> 1. $(\overline{x}^{2})=(1-\overline{y}^{2})=((1+\overline{y})(1-\overline{y}))=(1+\overline{y})\cap(1-\overline{y})$. Now, $$R / (1+\overline{y})\cong\mathbb{R}[\overline{x},\overline{y}] / (1+\overline{y})\cong\mathbb{R}[\overline{x}]$$Hence, $(1+\overline{y}),(1-\overline{y})$ are prime and hence primary.
> 2. We have that $(2),(3)$ are coprime in $R$. Hence, $(6)=(2)\cap(3)$ and this is primary decomposition. 