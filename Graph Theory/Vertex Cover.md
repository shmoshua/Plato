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


> [!lemma] Theorem 6 (König 1931)
> Let $G=(A\sqcup B,E)$ be a [[Graph|bipartite graph]]. Then, 
> 1. $\nu(G)=\tau(G)$

^c720dd

> [!proof]-
> We already have that $\nu(G)\leq \tau(G)$ from Proposition 1. Hence it suffices to show that $\tau(G)\leq \nu(G)$. Let $U$ be a minimum vertex cover in $G$. We construct a matching of size $\left| U \right|$.
> 
> Let $A':= U\cap A$ and $B':=U\cap B$. Let $H,H'$ be the subgraphs induced by $A'\cup B \backslash B'$ and $A \backslash A'\cup B'$.
> 
> Since $A'\cup B'$ is a vertex cover, $G$ has no edge from $A \backslash A'$ to $B \backslash B'$. Suppose $S\subseteq A'$ and consider $N_{H}(S)\subseteq B\backslash B'$. If $\left| N_{H}(S) \right|<\left| S \right|$, then we can substitute $S$ with $N_{H}(S)$ and obtain a smaller vertex cover, which is a contradiction. Therefore, the Hall's conditions holds for $H$ and we have a matching $M$ in $H$ that covers $A'$. Similarly, we have a matching $M'$ in $H'$ that covers $B'$. 
> 
> Combining $M,M'$ and the fact that $H,H'$ are disjoint, we have a matching of size $\left| U \right|$.

^c36b60


---
##### Examples
> [!h] Example 1
> We have that:
> 1. $\tau(K_{n})=n-1$
> 2. $\tau(K_{r,s})=\min \{ r,s \}$

^fd5d85

---
