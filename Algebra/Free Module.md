#Definition #Algebra 

> [!definition]
> A $R$-[[module]] $M$ is ***free*** if it has a basis, a linearly independent collection $\{ x_{i} \}_{i\in I}\subseteq M$ s.t. every $m\in M$ is a finite linear combination of the collection.
- **Related definition**: A free module is ***finite***, if the basis is finite with rank $n$, where $n$ is the number of basis elements.
- **Related definition**: An $R$-module $M$ is ***free*** on a subset $A\subseteq M$ if for all $m\in M$, there exists $x_{1},\dots,x_{k}\in A$ and $r_{1},\dots,r_{k}\in R$ s.t. $m=\sum_{i=1}^{k}r_{i}x_{i}$.
---
##### Properties
> [!lemma] Proposition 1
> Let $R$ be a ring and $M$ a $R$-module. Then, TFAE:
> 1. $M$ is a rank-$n$ free module.
> 2. $M\cong R^n$

> [!proof]-
> We have:
> 1. (1=>2): Let $M$ be a free module with basis $\{ x_{1},..,x_{n} \}$. Then, $Rx_{i}$ is a submodule and $R\to Rx_{i},r\mapsto rx_{i}$ is an isomorphism because $\{ x_{i} \}$ are linearly independent. Therefore, $$\psi:M\to Rx_{1}\oplus \dots \oplus  Rx_{n} $$is an isomorphism and $M\cong R^n$.
> 2. (2=>1): If $M\cong R^n$, with isomorphism $\varphi:R^n\to M$, then $\{ \varphi(e_{i}) \}_{i}$ form a basis. We have: $$\sum_{i=1}^{n}a_{i}\varphi(e_{i})=0 \implies\varphi(a_{1},\dots,a_{n})=0\implies (a_{1},\dots,a_{n})=0$$Further, for any $m\in M$, we have $\varphi ^{-1}(m)=(a_{1},\dots,a_{n})$.
---
> [!lemma] Proposition 2
> For any set $A$, there exists a $R$-module $M(A)$ free on $A$ s.t. 
> 1. if $N$ is any $R$-module, any map $\varphi:A\to N$ extends to $\Phi\in \text{Hom}_{R}(M(A),N)$ uniquely.
> 2. if $A=\{ a_{1},\dots,a_{n} \}$, then $M(A)=Ra_{1}\oplus\dots \oplus Ra_{n}$ 

> [!proof]+
> If $A=\varnothing$, then $M(A)=\{ 0 \}$. If $A\neq \varnothing$, we define: $$M(A):=\{ f:A\to R| \}$$