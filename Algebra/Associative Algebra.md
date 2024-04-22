#Definition #Algebra #RepresentationTheory 

> [!definition]
> Let $K$ be a [[field]]. An ***associative algebra*** over $K$ is a $K$-vector space $A$ endowed with a bilinear map $A\times A\to A,(x,y)\mapsto xy$ s.t. 
> 1. **associativity**: $(xy)z=x(yz)$ for all $x,y,z\in A$.
- **Related definition**: $A$ is ***unital***, if there exists a ***unit*** in $A$, i.e. an element $1\in A$ s.t. $a1=1 a=a$.
- **Related definition**: $A$ is ***commutative***, if $ab=ba$ for all $a,b\in A$.
---
##### Properties
> [!lemma] Proposition 1
> If a unit exists, it is unique.

> [!proof]-
> Let $1,1'$ be two units. Then, $1=11'=1'$.
---
##### Examples
> [!h] Example 1
> We have: 
> 1. $A:=K$ is a commutative associative algebra.
> 2. $A:=K[X_{1},\dots,X_{n}]$ is a commutative associative algebra.
> 3. $A:=\text{End}(V)$ where $V$ is a $K$-vector space. $A$ is commutative if and only if $\text{dim }V\leq 1$.
---
> [!h] Example 2 (Free algebra)
> $A:=K \braket{ x_{1} , \dots,x_{n} }$ where $x_{1},\dots,x_{n}$ denote the letters with multiplication as concatenation of words. $A$ is commutative if and only if $n\leq 1$.
---
> [!h] Example 3 (Group algebra)
> $A:=K[G]$ for a [[group]] $G$ with basis $\{ a_{g}:g\in G \}$ and multiplication $a_{gh}=a_{g}a_{h}$. $A$ is commutative if and only if $G$ is commutative.
---