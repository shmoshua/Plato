#Definition #Topology

> [!definition]
> A ***topological space*** is a pair $(X,\mathcal{O})$ of a set $X$ and a set $\mathcal{ O}$ of subsets of $X$ called **open sets**, s.t.
> 1. Any union of the open sets is open.
> 2. The intersection of any two open sets is open.
> 3. $\varnothing$ and $X$ are open.
> 
> Then, $\mathcal{ O}$ is the ***topology*** of $(X,\mathcal{O})$.
---
##### Related Definitions
For a topological space $X$,
- $A \subset X$ is ***closed***, if $X \backslash A$ is open.
- $U \subset X$ is a ***neighborhood*** of $x\in X$, if there is an open set $V$ s.t. $x\in V \subseteq U$.
- For any subset $B\subseteq X$, a point $x\in X$ is:
  - an ***interior point*** of $B$ if $B$ is a neighborhood of $x$.
  - an ***exterior point*** of $B$ if $X\backslash B$ is a neighborhood of $x$.
  - an ***edge point*** of $B$ if neither $B$ or $X\backslash B$ are a neighborhood of $x$.
- The set $\mathring{B}$ of interior points of $B$ is the ***interior*** or the ***open kernel*** of $B$.
- The set $\bar{B}$ of non-exterior points of $B$ is called the ***closed hull*** of $B$.
---
##### Sum of Topological Spaces
> [!definition]
> For topological spaces $(X,\mathcal{ O})$ and $(Y,\tilde{\mathcal{ O}})$, the ***topologic sum*** of $X$ and $Y$ is defined as $(X+Y)$ with the topology $$\{  U+V:U\in\mathcal{ O},V\in \tilde{ \mathcal{O}} \}$$
> where $+$ defines the direct disjoint sum of two sets, i.e. for two sets $A,B$, $A+B:= A\times \{ 0 \}\cup B\times \{ 1 \}$.
---
##### Cartesian Product of Topological Spaces
> [!definition]
> For topological spaces $X,Y$, a subset $W \subseteq X\times Y$ is ***open in the product topology***, if for every point $(x,y)\in W$ there is a neighborhood $U$ of $x$ in $X$ and a neighborhood $V$ for $y$ in $Y$ s.t. $U\times V\subseteq W$. Then, $X\times Y$ is called the ***Cartesian product*** of $X$ and $Y$.
---