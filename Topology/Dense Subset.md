#Definition #Topology 

> [!definition]
> For a [[topological space]] $X$ and two subsets $A,B \subseteq X$, ***$A$ is dense w.r.t. $B$*** if: $$B \subseteq \overline{A}$$
> If $A\subseteq X$ is dense w.r.t $X$, it is called **dense in $X$**, i.e. $X =\overline{A}$ or every non-empty open set in $X$ contains a point in $A$.
- **Related Definition**: A subset $A\subseteq X$ is ***nowhere dense*** in $X$, if $\overline{A}^\circ=\varnothing$.
---
##### Propositions
> [!lemma] Proposition 1
> For $A,B,C \subseteq X$, being dense is transitive, i.e. if $A$ is dense w.r.t. $B$ and $B$ is dense w.r.t. $C$, then $A$ is dense w.r.t. $C$.

> [!proof]-
> $$C\subseteq \overline{B}\subseteq \overline{A}$$
---
> [!lemma] Lemma 2
> Let $X$ be a topological space and let $U\subseteq X$ and $F= X \backslash U$. Then, the following are equivalent:
> 1. $U$ is open and dense in $X$.
> 2. $F$ is closed and nowhere dense in $X$. 

> [!proof]-
> We have that: 
> - (1=>2): As $U$ is open, $F$ is closed. Then, for a non-empty open set $V\subseteq X$, $V \cap U\neq \varnothing$. Therefore, $V\not\subseteq F$ and we have that $F^\circ=\varnothing$
> - (2=>1): As $F$ is closed, $U$ is open. Then, as $F^\circ = \varnothing$, for any non-empty open subset $V\subseteq X$, $V\not\subseteq F$ and therefore $V \cap U$. This proves that $U$ is dense.
---
##### Examples
**Dense**
1. $\mathbb{Q}$ is dense in $\mathbb{R}$.
2. A [[Meager Set|generic]] subset of a complete metric space or its open subset.
  
**Nowhere dense**
1. A point $x\in \mathbb{R}^n$ for $n\geq 1$.
2. The [[Cantor Set]] in $[0,1]$.
3. $\{ (x,0)\in\mathbb{R}^{2}: x\in \mathbb{Q} \}$ in $\mathbb{R}^{2}$
4. $f^{-1}(y)$ in $\mathbb{R}^n$ where $f:\mathbb{R}^n\to \mathbb{R}$ is a smooth function and $y$ is a regular point. 
---
