#Series #GraphTheory 

#### Problem 1
Assume that $G$ is not $2$-edge connected. Then, there exists $e\in E$ s.t. $G \backslash e$ is not connected. Let $A,B$ be the two connected component in $G \backslash e$. As $\left| V \right|$ is even, we have that either $\left| A \right|,\left| B \right|$ are both even or both odd.
1. if they are both even, then consider the perfect matching $M$ $e$ is part of. This is a contradiction as every edge $f\in M$ different from $e$ is contained completely in either $A$ or $B$, hence there will be a node in each $A$ and $B$ that is not covered. 
2. if they are both odd, $e$ has to be a part in every perfect matching. This is a contradiction to the fact that there exists a perfect matching containing an edge incident to $e$. 

---
#### Problem 2
1. Let $G$ have more than $n^{2}$ edges and let $M\subseteq E$ be a perfect matching. Then, $\left| E \backslash M \right|> n^2-n$. Let $uv\in E \backslash M$. Then, there exists an unordered pair $\{ e,f \}\subseteq M$ s.t. $e,uv,f$ forms a path. Now, as there are ${n \choose 2}=\frac{n^{2}-n}{2}$ such pairs by pigeonhole principle we have that there exists $e,f\in M$ s.t. there are three edges in $E \backslash M$ between the nodes of $e$ and $f$. This gives us a $4$-cycle and we can swap $e,f$ from the matching with the 2 other edges in the cycle. This is a contradiction to the uniqueness of the perfect matching.
2. Let $V:=\{ a_{1},\dots,a_{n},b_{1},\dots,b_{n} \}$. Then, consider a graph $G$ on $V$ where $a_{1},\dots,a_{n}$ form a clique and additionally, $a_{i}b_{j}\in E(G)$ if and only if $i\leq j$. Then, $$\left| E \right| =\frac{n(n-1)}{2}+\frac{n(n+1)}{2}=n^{2}$$However, one easily sees that we have a unique perfect matching $M:=\{ a_{i}b_{i} \}_{i\in[n]}$. Indeed, starting from $b_{1},\dots,b_{n}$ one can take the only available edge. 

---
#### Problem 3
We define a bipartite graph $G=(A\sqcup B,E)$ where $B:=\{ A_{kj} \}_{k\in [n],j\in [d_{k}]}$. Then, for $a\in E$, $aA_{kj}\in E$ if and only if $a\in A_{k}$. 