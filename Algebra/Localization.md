#Definition #Algebra 

> [!definition]
> Let $R$ be a commutative [[ring]].
> 1. A subset $S\subseteq R$ is called ***multiplicatively closed***, if $1\in S$ and $ab\in S$ for all $a,b\in S$. 
> 2. For a multiplicatively closed set $S\subseteq R$, the ***localization of $R$ at $S$*** is given by the ring: $$S^{-1}R:= (R\times S) / {\sim}$$where $(a,s)\sim(a',s')$ if and only if there exists $u\in S$ s.t. $u(as'-a's)=0$ where $\frac{a}{s}:=[(a,s)]$. The addition and multiplication are given by: $$\frac{a}{s}+\frac{a'}{s'}=\frac{as'+a's}{ss'},\quad \frac{a}{s}\cdot \frac{a'}{s'}=\frac{aa'}{ss'}$$

^e626db

- **Remark**: If $0\in S$, then $S^{-1}R=0$ by taking $u=0$ all the time. ^59501f

---
##### Properties
> [!lemma] Proposition 1
> Let $R$ be a ring and $S\subseteq R$ a multiplicatively closed subset. Then, 
> 1. $\sim$ is an equivalence relation. 
> 2. $S^{-1}R$ is a ring.
> 3. $S^{-1}R$ is a $R$-[[algebra]].

^321ab4

> [!proof]-
> We have that:
> 1. $\sim$ is clearly reflexive and symmetric. For transitivity, if $(a,s)\sim(a',s')$ and $(a',s')\sim(a'',s'')$, with $u,v\in S$ s.t. $u(as'-a's)=v(a's''-a''s')=0$. Then, $$\begin{align}s'uv(as''-a''s)&=s'uvas''-s'uva''s-uvs''a's+uvs''a's\\&=s''v\cdot u(as'-a's)+su\cdot v(a's''-a''s')=0\end{align}$$where $s'uv\in S$ as it is multiplicatively closed.
> 2. If $(a,s)\sim (a'',s'')$ with $u(as''-a''s)=0$, then: $$u((as'+a's)(s''s')-(a''s'+a's'')(ss'))=(s')^{2}\cdot u(as''-a''s)=0$$and $$u((aa')(s''s')-(a''a')(ss'))=a's'\cdot  u(as''-a''s)=0$$
> 3. Given by $\varphi:R\to S^{-1}R, a\mapsto \frac{a}{1}$. This is injective only if $S$ doesn't contain any zero divisors. 

^b7609c

---
##### Examples
> [!h] Example 1
> We have that:
> 1. for $S:=\{ 1 \}$, $S^{-1}R\cong R$.
> 2. let $S$ be the set of non-zero divisors of $R$. Then, $S$ is multiplicatively closed and if $R$ is an [[integral domain]], i.e. $S=R \backslash\{ 0 \}$, then 
> 	1. $S^{-1}R\cong \text{Quot}(R)$ the [[quotient field]].
> 	2. for any multiplicatively closed $T\subseteq S$, $T^{-1}R$ is a subring of $\text{Quot}(R)$. 
> 3. Let $S:=\{ a^n:n\in \mathbb{N} \}$ for a fixed element $a\in R$. Then, $S^{-1}R=:R_{a}$ and is called the ***localization of $R$ at $a$.***
> 4. For a [[prime ideal]] $P\unlhd R$, $S:= R \backslash P$ is multiplicatively closed. Then, $S^{-1}R=:R_{P}$ and is called ***localization of $R$ at $P$***.
