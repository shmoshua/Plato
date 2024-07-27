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
- **Related definition**: For $R$-modules $M,N$, a ***homomorphism*** is a $R$-linear map, i.e. $\varphi:M\to N$ s.t. 
	1. $\varphi(m+m')=\varphi(m)+\varphi(m')$ and
	2. $\varphi(rm)=r\varphi(m)$
- **Related definition**: $\text{Hom}_{R}(M,N)$ is the space of all homomorphisms from $M$ to $N$.
---
##### Properties
> [!lemma] Proposition 1
> For $\varphi\in \text{Hom}_{R}(M,N)$, we have:
> 1. $\text{ker }\varphi$ is a submodule of $M$.
> 2. $\text{im }\varphi$ is a submodule of $N$.
> 3. $\varphi$ is injective if and only if $\text{ker }\varphi=(0)$.
> 4. $\varphi$ is surjective if and only if $\text{im }\varphi=N$.

> [!proof]-
> We have:
> 1. let $m,n\in \text{ker }\varphi$. Then, $\varphi(m-n)=\varphi(m)+\varphi(-n)=\varphi(m)-\varphi(n)=0$ where $\varphi(n)+\varphi(-n)=\varphi(0)=0$ and $\varphi(-n)=-\varphi(n)$. 
>    
>    Further, for any $r\in R$, $\varphi(rm)=r\varphi(m)=0$.
> 2. let $m,n\in \text{im }\varphi$. Then, there exists $x,y$ with $\varphi(x)=m$ and $\varphi(y)=n$ and: $$\varphi(x-y)=\varphi(x)+\varphi(-y)=m-n$$Further, for any $r\in R$, $\varphi(rx)=r\varphi(x)=rm$. 
> 3. if $\varphi$ is injective, for any $m\in M$, if $\varphi(m)=0=\varphi(0)$, then $m=0$. 
>    
>    Conversely, if $\text{ker }\varphi=(0)$, then for any $m,n$ with $\varphi(m)=\varphi(n)$, $\varphi(m-n)=\varphi(m)-\varphi(n)=0$ and $m-n=0$. 
> 4. clear.
---
> [!lemma] Proposition 2 (Quotients)
> For an $R$-module $M$ and its submodule $N$, 
> 1. the additive abelian quotient $M / N$ can be made into an $R$-module by: $$r(x+N)=rx+N$$
> 2. the natural projection $\pi:M\to M / N,x\mapsto x+N$ is in $\text{Hom}_{R}(M,M / N)$.
> 3. $\text{ker }\pi=N$.

> [!proof]-
> We have that:
> 1. Of course $(M / N,+,N)$ is an abelian group and we can trivially check that the remaining axioms hold.
> 2. $\pi(x+y)=x+y+N=x+N+y+N=\pi(x)+\pi(y)$ and $\pi(rx)=rx+N=r\pi(x)$.
> 3. We have that: $$\text{ker }\pi=\{ x\in M:x+N=N \}=\{ x\in M: x\in N\}=N$$
---
> [!lemma] Proposition 3 (Isomorphism Theorems)
> Let $M,N$ be $R$-modules. 
> 1. for $\varphi\in \text{Hom}_{R}(M,N)$, $\varphi$ induces an isomorphism:  $M /\text{ker} \varphi\cong \text{im }\varphi$
> 2. for submodules $A,B$ of $M$, we have $(A+B) / B\cong A / (A\cap B)$
> 3. for submodules $A,B$ of $M$ with $A\subseteq B$, we have $(M / A) / (B/A)\cong M / B$.

> [!proof]-
> We have that:
> 1. Let $\psi:M / \text{ker }\varphi\to \text{im }\varphi, x+\text{ker }\varphi\mapsto \varphi(x)$. Then, it is well defined: if $x+\text{ker }\varphi=y+\text{ker }\varphi$, then $x-y\in \text{ker }\varphi$ and: $$\varphi(x)=\varphi(y+x-y)=\varphi(y)+\varphi(x-y)=\varphi(y)$$Further, it is a homomorphism as $\psi(x+y+\text{ker }\varphi)=\varphi(x+y)=\varphi(x)+\varphi(y)$ and $\psi(rx+\text{ker }\varphi)=\varphi(rx)=r\varphi(x)=r\psi(x+\text{ker }\varphi)$. More importantly, $$x+\text{ker }\varphi\in\text{ker }\psi \iff\varphi(x)=0\iff x\in \text{ker }\varphi$$Hence $\psi$ is injective and it is surjective by definition.
> 2. 
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
