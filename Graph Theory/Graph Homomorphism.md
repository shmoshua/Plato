#Definition #GraphTheory 

> [!definition] 
> Let $G=(V,E)$ and $G'=(V',E')$ be two [[graph|graphs]]. A ***graph homomorphism*** is a map $\varphi:V\to V'$ s.t. $$\{ x,y \}\in E\implies\{ \varphi(x),\varphi(y) \}\in E'$$
> $\varphi$ is additionally, 
> 1. an ***isomorphism***, if $\varphi$ is bijective and $\varphi ^{-1}$ is a homomorphism. In this case, $G\cong G'$.
> 2. an ***automorphism***, if $G'=G$.
- **Related definition**: A map is a ***graph invariant***, if it assigns the same value to isomorphic graphs.
---
##### Properties
> [!lemma] Lemma 1
> Let $G,G'$ be two graphs as above with a graph homomorphism $\varphi:V\to V'$. For $x'\in V'$,
> 1. $\varphi ^{-1}(x')$ is an independent set of vertices.

> [!proof]-
> Assume otherwise, i.e. there exists $a,b\in \varphi ^{-1}(x')$ s.t. $ab\in E$. Then, $x'x'\in E'$, which is a contradiction.
---
##### Examples
> [!h] Example 1
> We have:
> 1. Number of vertices and number of edges are graph invariants.
> 2. The greatest number of pairwise adjacent vertices is a graph invariant.