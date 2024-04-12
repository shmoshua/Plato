#Definition #Topology 

> [!definition]
> Let $X$ be a set. A ***uniform structure*** on $X$ is a collection $\mathcal{U}$ of subsets of $X\times X$ s.t. 
> 1. $A\in \mathcal{U}$ and $A\subseteq B$, then $B\in \mathcal{U}$.
> 2. $A_{1},A_{2}\in \mathcal{U}$, then $A_{1}\cap A_{2}\in \mathcal{U}$.
> 3. $\Delta:=\{ (x,x): x\in X \}\subseteq A$ for all $A\in \mathcal{U}$.
> 4. if $A\in \mathcal{U}$, then $A^{-1}:=\{ (y,x):(x,y)\in A \}\in \mathcal{U}$.
> 5. if $A\in \mathcal{U}$, then there exists $B\in \mathcal{U}$ s.t. $\{ (x,y): \exists z,(x,z),(z,y)\in B \}$
---
##### Examples
> [!h] Example 1
> For a [[metric space]] $(X,d)$, $$\mathcal{U}:=\{ A\subseteq X\times X: \exists\delta>0,d(x,y)<\delta\implies (x,y) \in A\}$$is a uniform structure.