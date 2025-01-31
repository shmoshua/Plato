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
> [!lemma] Proposition 2 (Ideals in Localizations)
> Let $S$ be a multiplicatively closed subset of a ring $R$. Consider the homomorphism $\varphi:R\to S^{-1}R$.
> 1. for any $I\unlhd R$, $I^e=(\varphi(I))=\left\{  \frac{a}{s}:a\in I,s\in S  \right\}$.
> 2. for any $I\unlhd S^{-1}R$, $(I^c)^e=I$. 
> 3. [[Ring Homomorphism|contractions]] and [[Ring Homomorphism|extensions]] give a 1:1-correspondence: $$\begin{align}\{ \text{Prime ideals in }S^{-1}R \}&\leftrightarrow \{ \text{Prime ideals } I\text{ in }R\text{ with }I\cap S=\varnothing\}\\I&\mapsto I^c\\I^e&\leftarrow I\end{align}$$

> [!proof]-
> We have:
> 1. As $\frac{1}{s}\in S^{-1}R$ for all $s\in S$ and $I^e$ is an ideal, $\frac{a}{s}:=\frac{1}{s}\cdot\varphi(a)\in I^e$. However, for the other direction, for any $a\in I$, $\varphi(a)$ is contained in the RHS. This proves the statement as RHS is an ideal.
> 2. By [[Ring Homomorphism|Proposition 4]] it suffices to show that $(I^c)^e\supseteq I$. Let $\frac{a}{s}\in I$. Then, $a\in \varphi ^{-1}(I)=I^c$ since $\varphi(a)=\frac{a}{1}=s\cdot \frac{a}{s}\in I$. Applying 1 to $I^c$, we have that: $\frac{a}{s}\in (I^c)^e$. 
> 3. We first check that $\to$ is well-defined. If $I$ is a prime ideal in $S^{-1}R$, then $I^c$ is a prime ideal in $R$ by [[Prime Ideal|Proposition 2.1]]. Further $S$ are all mapped to units in by $\varphi$ but $I^c$ cannot contain any units. 
>    
>    To check that $\gets$ is well-defined, let $I\unlhd R$ be prime with $I\cap S=\varnothing$. Let $\frac{a}{s}, \frac{b}{t}\in S^{-1}R$ with $\frac{ab}{st}\in I^e$. Then, by 1, $\frac{ab}{st}=\frac{c}{u}$ for some $c\in I$ and $u\in S$, i.e. there exists some $v\in S$ s.t. $v(abu-stc)=0$. This implies that $vabu\in I$. Since $I$ is prime, one of these 4 factors have to lie in $I$, but as $u,v\in S$, either $a\in I$ or $b\in I$. Hence, $\frac{a}{s}\in I^e$ or $\frac{b}{t}\in I^e$.
>    
>    Now, from 2, $(I^c)^e=I$ and we are left to show that $(I^e)^c=I$ for all prime $I\unlhd R$ with $I\cap S=\varnothing$. From [[Ring Homomorphism|Proposition 4]], we only need to show $\subseteq$. Let $a\in (I^e)^c$, i.e. $\varphi(a)=\frac{a}{1}\in I^e$. Then, by $a$, there exists $b\in I$ and $s\in S$ s.t. $\frac{a}{1}=\frac{b}{s}$, i.e. there exists $u\in S$ with $u(as-b)$. hence, $uas\in I$ and as $u,s\in S$ and $I$ is prime, we have that $a\in I$. 

- **Remark**: Applying 3 to localization at prime ideals, we have a correspondence between prime ideals in $R_{P}$ and prime ideals $I$ in $R$ with $I\subseteq P$. 
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
> 5. $\mathbb{Z}_{(p)}$ is the localization of $R$ at the prime ideal $(p)$ for $p\in \mathbb{Z}$ prime. 
