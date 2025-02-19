#Definition #GraphTheory 

> [!definition] 
> Let $G=(V,E)$ and $G'=(V',E')$ be two [[graph|graphs]]. A map $\varphi:V\to V'$ is:
> 1. A ***graph homomorphism*** is for all $x\sim y$ in $G$, $\varphi(x)\sim\varphi(y)$ in $G'$.
> 1. A ***graph isomorphism***, if $\varphi$ is bijective and $\varphi,\varphi ^{-1}$ is a homomorphism. We denote $G\cong G'$.
> 2. A ***graph automorphism***, if $G'=G$.

^46553c

- **Related definition**: A map is a ***graph invariant***, if it assigns the same value to isomorphic graphs. ^facdab
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