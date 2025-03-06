#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a [[graph]].
> 1. A ***Hamiltonian path*** is a [[Path (Graph)|path]] which contains all vertices in the $V$. 
> 2. A ***Hamiltonian cycle*** is a cycle which contains all vertices in the $V$. 
> 3. $G$ is ***Hamiltonian*** if it has a Hamiltonian cycle.

^a7fcdb

- **Remark**: Finding Hamiltonian path is NP-hard.

---
##### Properties
> [!lemma] Proposition 1
> Let $G=(V,E)$ be a graph.
> 1. If $G$ is Hamiltonian, then $G$ is $1$-[[Tough Graph|tough]], i.e. for any $S\subseteq V$, $G \backslash S$ has at most $\left| S \right|$ connected components.  

> [!proof]-
> Let $C_{1},\dots,C_{k}$ be the components of $G \backslash S$. Imagine that we are moving along a Hamilton cycle in some order, vertex-by-vertex. We must visit each component of $G \backslash S$ at least once; when we leave $C_{i}$ for the first time, let $v_{i}$ be the subsequent vertex visited, which must be in $S$. Each $v_{i}$ must be distinct because a cycle cannot intersect itself. Hence, $S$ must have at least as many vertices as the number of connected components of $G \backslash S$.