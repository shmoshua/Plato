#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a [[graph]].
> 1. a subset $S\subseteq V$ is a ***vertex cover*** if $e\cap S\neq \varnothing$ for all $e\in E$.

^63a2ab

- **Related definition**: A vertex cover $S$ is: ^32ed75
	1. ***minimal*** if there is no other vertex cover $S'\supseteq S$ with $\left| S' \right|> \left| S \right|$.
	2. ***minimum*** if there is no other matching $S'$ with $\left| S' \right|> \left| S\right|$.
- **Related definition**: For a graph $G$, $\tau(G)$ denotes the size of minimum vertex cover. ^cf73c8

---
##### Properties
> [!lemma] Proposition 1
> For a graph $G$, 
> 1. $\tau(G)=n\ -$ [[Independence and Clique|$\alpha(G)$]].
> 2. $\left| M \right|\leq \tau(G)\leq 2\left| M \right|$ for any [[Matching|maximal matching]] $M$.
> 3. $\nu(G)\leq \tau(G)\leq 2\nu(G)$.

^31a060

> [!proof]-
> We have that:
> 1. For any independent set $S$, $V \backslash S$ is a vertex cover: if $e\cap V \backslash S= \varnothing$ for some $e$, then $e\subseteq S$ and $S$ is not independent. 
>    
>    Conversely, for any vertex cover $S$, $V \backslash S$ is an independent set. If $e\subseteq V \backslash S$, then $e\cap S=\varnothing$, which is a contradiction. 
>    
>    Therefore, $\tau(G)=\left| V(G) \right|-\alpha(G)$.
> 2. Let $M$ be a maximum matching. Then, for any $e\in M$, we need a different node in the vertex cover. Hence, $\nu(G)\leq \tau(G)$.
>    
>    Now, let $M$ be just maximal. Hence, for every $e\in E(G)$, $e\cap V(M)\neq \varnothing$. Hence, $V(M)$ is a vertex cover and $\tau(G)\leq \left| V(M) \right|=2\left| M \right|$. Finally, $\left| M \right|\leq \tau(G)\leq 2\left| M \right|$.
> 3. As a maximum matching is maximal.
>    


^5c6854

---
> [!lemma] Theorem 2 (Hall 1935)
> Let $G:=(A\sqcup B,E)$ be a bipartite graph. TFAE:
> 1. there exists a matching $M$ covering $A$.
> 2. $\left| S \right|\leq \left| N(S) \right|$ for all $S\subseteq A$.

> [!proof]-
> We have that:
> 1. (1=>2): If $M$ is such a matching, then for any $S\subseteq A$, $$\left| S \right| = \left| N(S)\cap V(M) \right|\leq \left| N(S) \right|  $$
> 2. (2=>1): We apply induction on $\left| A \right|$.
> 	- If $\left| A \right|=1$, then the statement is true. 
> 	- Let $\left| A \right|\geq 2$. 
> 		- If $\left| S \right|\leq \left| N(S) \right|-1$ for all $\varnothing\neq S\subsetneq A$ then we can pick $ab\in E$ and consider $G':= G \backslash \{ a,b \}$. Then, for every non empty $S\subseteq A \backslash \{ a \}$, we have that: $$\left| S \right| \leq \left| N(S) \right| -1=\left| N_{G'}(S) \right| $$and by IH we have a matching $M'$ in $G'$ covering $A \backslash \{ a \}$. Together with $ab$, we get a matching covering $A$.
> 		- Otherwise, there exists a non-empty $S\subsetneq A$ s.t. $\left| S \right|=\left| N(S) \right|$. Let $A':=S$ and $B':= N(S)$. Then, $G':=G[A'\cup B']$ contains a matching covering $A'$ by induction hypothesis. We now claim that $G \backslash G'$ also satisfies the Hall's condition. For any $S\subseteq A \backslash A'$, if we have that $\left| N_{G \backslash G'}(S) \right|< \left| S \right|$ then we have that: $$\left| N_{G}(S\cup A') \right| =\left| N_{G \backslash G'}(S) \right| +\left| B' \right| <\left| S \right| +\left| A' \right| =\left| S\cup A' \right| $$which is a contradiction. Therefore, by induction again, there exists a matching covering $A \backslash A'$. Combining the two matchings, we have a matching covering $A$.

---
> [!lemma] Corollary 3
> Let $G:=(A\sqcup B,E)$ be a bipartite graph. Let $k\geq 1$.
> 1. if $\left| S \right|\leq \left| N(S) \right|+k$ for all $S\subseteq A$, then $G$ contains a matching of cardinality $\left| A \right|-k$.
> 2. if $G$ is $k$-regular, then $G$ has a perfect matching.

> [!proof]-
> We have that:
> 1. If we add $k$ new vertices to $B$ that are connected to all the vertices to $A$, then in the new graph $G'$, we have: $$\left| S \right| \leq \left| N(S) \right| +k=\left| N_{G'}(S) \right| ,\quad \forall S\subseteq A$$By Hall, we have a matching $M$ covering $A$ where at least $\left| A \right|-k$ must be edges of $G$.
> 2. If $G$ is $k$-regular, $\left| A \right|=\left| B \right|$ as the total number of edges is $k\left| A \right|=k\left| B \right|$. Hence, it suffices to show that there exists a matching $M$ covering $A$. For every $S\subseteq A$, we have that there are $k\left| S \right|$ edges joining $S$ to $N(S)$ and these are from the $k\left| N(S) \right|$ edges incident to $N(S)$. Hence, $$k\left|  S\right|\leq k\left| N(S) \right| $$Therefore, we have the statement by Hall.


---
> [!lemma] Corollary 4
> Let $k\geq 1$. A $2k$-regular graph has a $2$-factor.

> [!proof]-
> We may assume that $G$ is connected as we have to show it for each connected component. Let $G$ be a connected $2k$-regular graph. By [[Eulerian Trail|Theorem 2.1]] $G$ contains an Eulerian tour $T$. Let us now define a new graph $G'$ where every vertex $v\in V(G)$ is split into two vertices $v_{+},v_{-}$ in $G'$. 
> 
> If $v\to w\in T$, we put $v_{+}w_{-}\in G'$. Then, $G'$ is bipartite and $k$-regular, i.e. it has a perfect matching by Corollary 3.2. Collapsing $G'$ back to $G$ with the matching, we get a $2$-factor.
---
> [!lemma] Corollary 5
> Let $A_{1},\dots,A_{n}$ be a collection of sets. A family $X:=\{ a_{1},\dots,a_{n} \}$ is a SDR if $a_{i}\in A_{i}$ and $\left|X  \right|=n$. TFAE:
> 1. $A_{1},\dots,A_{n}$ has an SDR.
> 2. $\left| I \right|\leq \left| \bigcup_{i\in I}^{}A_{i} \right|$for all $I\subseteq [n]$

> [!proof]-
> We construct a bipartite graph $G$ where: $A:=[n]$ and $B:=\bigcup_{i\in I}^{}A_{i}$ s.t. $ia\in G$ if and only if $a\in A_{i}$. Then, a matching in $G$ exactly corresponds to a SDR and the Halls condition exactly comes down to $\left| I \right|\leq \left| \bigcup_{i\in I}^{}A_{i} \right|$. 

---

> [!lemma] Theorem 6 (König 1931)
> Let $G=(A\sqcup B,E)$ be a [[Graph|bipartite graph]]. Then, 
> 1. $\nu(G)=\tau(G)$

> [!proof]+
> We already have that $\nu(G)\leq \tau(G)$ from Proposition 1. Hence it suffices to show that $\tau(G)\leq \nu(G)$. Let $U$ be a minimum vertex cover in $G$. We construct a matching of size $\left| U \right|$.
> 
> Let $A':= U\cap A$ and $B':=U\cap B$. Let $H,H'$ be the subgraphs induced by $A'\cup B \backslash B'$ and $A \backslash A'\cup B'$.

^c36b60


---
##### Examples
> [!h] Example 1
> We have that:
> 1. $\tau(K_{n})=n-1$
> 2. $\tau(K_{r,s})=\min \{ r,s \}$

^fd5d85

---
