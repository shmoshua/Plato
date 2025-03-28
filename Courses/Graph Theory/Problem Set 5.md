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

We first have that if such $D_{k}$ exists for all $k$, then for any $I\subseteq [n]$, $\left| \bigcup_{i\in I}^{}A_{i} \right|\geq \left| \bigcup_{i\in I}^{} D_{i}\right|=\sum_{i\in I}^{}d_{i}$. Conversely, let $\sum_{i\in I}^{}d_{i}\leq \left| \bigcup_{i\in I}^{}A_{i} \right|$ for all $I\subseteq [n]$. 

We define a bipartite graph $G=(A\sqcup B,E)$ where $B:=\{ A_{kj} \}_{k\in [n],j\in [d_{k}]}$. Then, for $a\in E$, $aA_{kj}\in E$ if and only if $a\in A_{k}$. Now by Hall, $G$ has a matching covering $B$ if and only if $\left| N(S) \right|\geq \left| S \right|$ for all $S\subseteq B$. Let $S\subseteq B$ and define $I:=\{ k\in[n]:A_{kj}\in S \}$. Then, $$\left| S \right| \leq \sum_{k\in I}^{}d_{i}\leq \left| \bigcup_{k\in I}^{}A_{i} \right| =\left| N(S) \right| $$Hence, there exists a matching $M$ covering $B$. Now, define $D_{k}:=\{ a\in A: aA_{kj} \in M,j\in [d_{k}]\}$. Then, by definition $D_{k}\subseteq A_{k}$ and as $M$ is a matching, $D_{k}$'s are disjoint. Further, as the matching covers $B$, we have that $\left| D_{k} \right|=d_{k}$. This concludes the proof.

---
#### Problem 4
Wlog we may assume that $M_{A},M_{B}$ do not contain any edges that are not incident to $A$ and $B$ respectively. Otherwise we can reduce them so that they are the minimal matching covering $A$ and $B$. 

Consider $M:= M_{A}\cup M_{B}$. Then, for any node $v$ covered by $M_{A}\cup M_{B}$, we have that $d(v)\leq 2$. This implies that in $M$ all components are path or cycles. Further, as no two incident edges in $M$ both come from $M_{A}$ or $M_{B}$, we know that they are alternating in $M$. 

Let $P=v_{1}v_{2}\dots v_{k}$ be a path component in $M$. If $k$ is even, there are odd number of edges in $P$ and we can choose every other edge into a new matching $M'$ s.t. $v_{1},\dots,v_{k}$ are all covered. If $k$ is odd, first notice that $v_{1},v_{k}\in X$ or $v_{1},v_{k}\in Y$. 

We claim that for any path $P=v_{1}\dots v_{k}\subseteq M$ for odd $k$, if $v_{1},v_{k}\in A\cup B$ then exactly one of $v_{1}v_{2},v_{k-1}v_{k}$ is in $M_{A}$.
1. Let $k=3$ and wlog $v_{1}v_{2},v_{2}v_{3}$ are both in $M_{A}$. Then, this is a contradiction to $M_{A}$ being a matching. If $v_{1}v_{2},v_{2}v_{3}$ are both not in $M_{A}$ then they are in $M_{B}$ and it follows by symmetry.
2. Let $k\geq 5$ and wlog $v_{1}v_{2},v_{k-1}v_{k}$ are both in $M_{A}$. If $v_{1},v_{k}\in A$ then $v_{2},v_{k-1}\in B$ and by induction either $v_{2}v_{3}$ or $v_{k-2}v_{k-1}$ is in $M_{A}$. This is a contradiction. If $v_{1},v_{k}\in B$, then we have $v_{2},v_{k-1}\in A$ and the rest is analogous.

Hence, if $k$ is odd, we have that one endpoint is not in $A\cup B$. Hence, we can choose every second edge in $P$ s.t. we cover every nodes in $A\cup B$ covered by $P$. Finally for each cycle, pick every second edge.  This results in a matching and we cover $A\cup B$. 

---
#### Problem 5
1. Let $M$ be a matching in $G$. Assume we have Hall's condition, i.e. $\left| S \right|\leq \left| N(S) \right|$ for all $S\subseteq A$ and $M$ does not cover $A$. 
   
   Now, let $a\in A$ be a point not covered in $M$. We define: $$X:=\{ x\in A: \text{there is a }M\text{-alternating path from }a\text{ to }x \}$$
   
   By Hall, $\left| N(a_{1}) \right|\geq 1$ and let $b_{1}\in N(a_{1})$. If $b_{1}$ is not covered, $a_{1}b_{1}$ is an augmenting path and we are done. Otherwise there exists $a_{2}\in A$ s.t. $b_{1}a_{2}\in M$. Now, there 