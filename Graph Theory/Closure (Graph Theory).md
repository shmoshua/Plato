#Definition #GraphTheory 

> [!definition]
> Let $G$ be a [[graph]] on $n$ nodes.
> 1. The ***closure*** $C(G)$ of a graph $G$, is the supergraph of $G$ on $V(G)$ obtained by iteratively adding edges between a pair of non-adjacent vertices whose degree sum is at least $n$.

---
##### Properties
> [!lemma] Proposition 1
> Any graph $G$ has a unique closure.

> [!proof]-
> Let $C_{1}\neq C_{2}$ be closures of $G$. Let $e_{1},\dots,e_{k}$ and $f_{1},..,f_{\ell}$ be the edges we add to $G$ to create $C_{1}$ and $C_{2}$ respectively. Wlog we may assume $k<\ell$. Then, there exists an edge $f_{i}\notin C_{i}$. Let us assume that $i$ is also small as possible. Then, we have that: $$G':=G\cup \{ f_{1},..,f_{i-1} \}\subseteq C_{1}$$and as we are able to add $f_{i}$ to $G'$, we should be able to add it to $C_{1}$ as well, which is a contradiction. 

---
> [!lemma] Theorem 2 (Bondy Chvatal 1976)
> Let $G$ be a simple graph on $n$ vertices. TFAE:
> 1. $G$ is [[Hamiltonian Path|Hamiltonian]].
> 2. $C(G)$ is Hamiltonian.

> [!proof]+
> 