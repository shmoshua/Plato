#Definition #Algebra 

> [!definition]
> Let $R$ be a [[ring]]. A ***left $R$-module*** is a set $M$ with the addition $+:M\times M\to M,(m,n)\mapsto m+n$ and scalar multiplication $\cdot:R\times M\to M,(r,m)\mapsto rm$ s.t. 
> 1. $(M,+,0)$ is an abelian group.
> 2. $r(m+n)=rm+rn$ for all $r\in R$, $m,n\in M$.
> 3. $(r+s)m=rm+sm$ for all $r ,s\in R$, $m\in M$.
> 4. $r(sm)=(rs)m$ for all $r, s\in R$, $m\in M$.
> 5. $1m=m$ for all $m\in M$.
- **Remark**: Similarly, one can define a ***right $R$-module***. If $R$ is commutative, a left $R$-module is also a right module by defining $rm=mr$.
- **Remark**: For a field $K$, a $K$-module is equivalent to a $K$-[[vector space]].
---
##### Examples
> [!h] Example 1
> We have:
> 1. $R$ is a $R$-module with usual addition and multiplication.
> 2. $R^n$ is a $R$-module with component-wise addition and multiplication.
> 3. $\text{Mat}_{m,n}(R)$ is a $R$-module with matrix addition and scalar multiplication.
---
> [!h] Example 2
> Let $A$ be an [[abelian group]]. Then, $A$ is a $\mathbb{Z}$-module with usual addition and $$na:=\begin{cases}a+\dots+a&n>0\\0&n=0\\-a-\dots-a&n<0\end{cases}$$as multiplication.
---
