#Definition #Algorithms #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a [[graph]]. 
> 1. a subset $M\subseteq E$ is a ***matching*** if $e\cap f=\varnothing$ for all $e,f\in M$.

^ba7938

- **Related definition**: A matching $M$ is: ^32ed75
	1. ***maximal*** if there is no other matching $M'\supseteq M$ with $\left| M' \right|> \left| M \right|$.
	2. ***maximum*** if there is no other matching $M'$ with $\left| M' \right|> \left| M \right|$.
	3. ***perfect*** if $\left| M \right|=\left| V(G) \right| / 2$.
- **Related definition**: For a graph $G$, $\nu(G)$ denotes the size of maximum matching. ^cf73c8
- **Remark**: A matching in $G$ corresponds to an independent set in the [[line graph]] $L(G)$. ^3aa979
- **Remark**: The maximum matching problem can be written in ILP as follows: $$\begin{array}{rll}\max&\sum_{e\in E}^{}x_{e}\\\text{subject to}&\sum_{e\ni v}^{}x_{e}\leq 1 & \forall v\in V\\&x_{e}\in \{ 0,1 \}&\forall e\in E\end{array}$$
---
##### Properties
> [!lemma] Proposition 1 
> Let $G=(V,E)$ be a graph. Then,
> 1. $\nu(G)\leq \tau(G)\leq 2\nu(G)$ where $\tau(G)$ is the size of the minimum [[vertex cover]].

> [!proof]-
> See [[Vertex Cover]].

---
##### Matching in bipartite graphs
> [!lemma] Theorem 2 (Hall 1935)
> Let $G:=(A\sqcup B,E)$ be a bipartite graph. TFAE:
> 1. there exists a matching $M$ covering $A$.
> 2. $\left| S \right|\leq \left| N(S) \right|$ for all $S\subseteq A$.

^cbfcfe

> [!proof]-
> We have that:
> 1. (1=>2): If $M$ is such a matching, then for any $S\subseteq A$, $$\left| S \right| = \left| N(S)\cap V(M) \right|\leq \left| N(S) \right|  $$
> 2. (2=>1): We apply induction on $\left| A \right|$.
> 	- If $\left| A \right|=1$, then the statement is true. 
> 	- Let $\left| A \right|\geq 2$. 
> 		- If $\left| S \right|\leq \left| N(S) \right|-1$ for all $\varnothing\neq S\subsetneq A$ then we can pick $ab\in E$ and consider $G':= G \backslash \{ a,b \}$. Then, for every non empty $S\subseteq A \backslash \{ a \}$, we have that: $$\left| S \right| \leq \left| N(S) \right| -1=\left| N_{G'}(S) \right| $$and by IH we have a matching $M'$ in $G'$ covering $A \backslash \{ a \}$. Together with $ab$, we get a matching covering $A$.
> 		- Otherwise, there exists a non-empty $S\subsetneq A$ s.t. $\left| S \right|=\left| N(S) \right|$. Let $A':=S$ and $B':= N(S)$. Then, $G':=G[A'\cup B']$ contains a matching covering $A'$ by induction hypothesis. We now claim that $G \backslash G'$ also satisfies the Hall's condition. For any $S\subseteq A \backslash A'$, if we have that $\left| N_{G \backslash G'}(S) \right|< \left| S \right|$ then we have that: $$\left| N_{G}(S\cup A') \right| =\left| N_{G \backslash G'}(S) \right| +\left| B' \right| <\left| S \right| +\left| A' \right| =\left| S\cup A' \right| $$which is a contradiction. Therefore, by induction again, there exists a matching covering $A \backslash A'$. Combining the two matchings, we have a matching covering $A$.

^f6ad99

---
> [!lemma] Corollary 3
> Let $G:=(A\sqcup B,E)$ be a bipartite graph. Let $k\geq 1$.
> 1. if $\left| S \right|\leq \left| N(S) \right|+k$ for all $S\subseteq A$, then $G$ contains a matching of cardinality $\left| A \right|-k$.
> 2. if $G$ is $k$-regular, then $G$ has a perfect matching.

^d7be1f

> [!proof]-
> We have that:
> 1. If we add $k$ new vertices to $B$ that are connected to all the vertices to $A$, then in the new graph $G'$, we have: $$\left| S \right| \leq \left| N(S) \right| +k=\left| N_{G'}(S) \right| ,\quad \forall S\subseteq A$$By Hall, we have a matching $M$ covering $A$ where at least $\left| A \right|-k$ must be edges of $G$.
> 2. If $G$ is $k$-regular, $\left| A \right|=\left| B \right|$ as the total number of edges is $k\left| A \right|=k\left| B \right|$. Hence, it suffices to show that there exists a matching $M$ covering $A$. For every $S\subseteq A$, we have that there are $k\left| S \right|$ edges joining $S$ to $N(S)$ and these are from the $k\left| N(S) \right|$ edges incident to $N(S)$. Hence, $$k\left|  S\right|\leq k\left| N(S) \right| $$Therefore, we have the statement by Hall.

^4415a5


---
> [!lemma] Corollary 4
> Let $k\geq 1$. A $2k$-regular graph has a $2$-factor.

^2257d4

> [!proof]-
> We may assume that $G$ is connected as we have to show it for each connected component. Let $G$ be a connected $2k$-regular graph. By [[Eulerian Trail|Theorem 2.1]] $G$ contains an Eulerian tour $T$. Let us now define a new graph $G'$ where every vertex $v\in V(G)$ is split into two vertices $v_{+},v_{-}$ in $G'$. 
> 
> If $v\to w\in T$, we put $v_{+}w_{-}\in G'$. Then, $G'$ is bipartite and $k$-regular, i.e. it has a perfect matching by Corollary 3.2. Collapsing $G'$ back to $G$ with the matching, we get a $2$-factor.

^002a60

---
> [!lemma] Corollary 5
> Let $A_{1},\dots,A_{n}$ be a collection of sets. A family $X:=\{ a_{1},\dots,a_{n} \}$ is a SDR if $a_{i}\in A_{i}$ and $\left|X  \right|=n$. TFAE:
> 1. $A_{1},\dots,A_{n}$ has an SDR.
> 2. $\left| I \right|\leq \left| \bigcup_{i\in I}^{}A_{i} \right|$for all $I\subseteq [n]$

^0988a7

> [!proof]-
> We construct a bipartite graph $G$ where: $A:=[n]$ and $B:=\bigcup_{i\in I}^{}A_{i}$ s.t. $ia\in G$ if and only if $a\in A_{i}$. Then, a matching in $G$ exactly corresponds to a SDR and the Halls condition exactly comes down to $\left| I \right|\leq \left| \bigcup_{i\in I}^{}A_{i} \right|$. 

^1c07c9

---
##### Matching in General Graphs
> [!lemma] Theorem 6 (Tutte 1947)
> Let $G=(V,E)$ be a graph. TFAE:
> 1. $G$ has a perfect matching. 
> 2. $q(G \backslash S)\leq \left| S \right|$ for all $S\subseteq V$ where $q(G)$ denotes the number of odd components of $G$. 

> [!proof]-
> We have that:
> 1. (1=>2): If $G$ has a perfect matching, then for every $S\subseteq V$, every odd component has to have a matching edge to $S$. Further, such edges cover different node in $S$. Hence, $q(G \backslash S)\leq \left| S \right|$ holds.
> 2. (2=>1): Let $\mathcal{B}$ be the set of graphs on $V(G)$ that meet the Tutte condition but do not have a perfect matching. We claim that $\mathcal{B}$ is empty. Notice that Tutte's condition is preserved by the addition of edges: For $G':= G\cup e$ we have that $q(G'\backslash S)\leq q(G\backslash S)$ for any $S\subseteq V$. Hence, if $H\in \mathcal{B}$, for any $e\in E$, $H\cup e\in \mathcal{B}$ or $H\cup e$ has a perfect matching. Further if $H\cup e$ has a perfect matching then $H\cup e\cup f$ has a perfect matching as well. Therefore, if $\mathcal{B}$ is non-empty there exists $G\in \mathcal{B}$ s.t. $G\cup e$ has a perfect matching for all $e\in E$.
>    
> 	1. **$G$ has even number of vertices**.
> 	   Consider $S:=\varnothing$. Then, $q(G)=0$. However, a graph of odd order has at least one component of odd order. 
> 
>    Let $U$ be the set of vertices in $G$ that are connected to all other vertices. 
>    
>    - If $G \backslash U$ is a disjoint union of cliques, then there exists a perfect matching as we can match every vertices in $G \backslash U$ trivially and the one node left in each odd component can be matched with $U$ by definition. Lastly, the remaining nodes in $U$ can be matched with each other as $G$ has even number of nodes. This is a contradiction.
>    - If $G \backslash U$ is not a disjoint union of cliques, there exist two vertices in a same component that are not adjacent. We claim that on the shortest path between these two nodes, we can find a path $xyz$ where $xz\notin E$. Otherwise we have that the shortest path is $P=v_{1}\dots v_{\ell}$ where $v_{i-1}v_{i+1}\in E$ for all and $v_{1}v_{3}v_{4}\dots v_{\ell}$ is a shorter path, which is a contradiction. 
>      
>      Further, as $y\notin U$, there exists $w\in G \backslash U$ s.t. $wy\notin E$. Now by the maximality, let $M_{1},M_{2}$ be the perfect matching in $G\cup xz$ and $G\cup wy$. We will find a perfect matching in $M_{1}\cup M_{2}$ that doesn't contain $xz,wy$, i.e. the matching is also in $G$, which is a contradiction.
>      
>      Let $F$ be the graph on $V(G)$ with edges that belong to exactly one of $M_{1}$ or $M_{2}$. Then, $F$ contains $xz$ and $wy$. Since every vertex has degree $1$ in $M_{1}$ or $M_{2}$, we have that in $F$ every vertex has degree $0$ or $2$. Hence, $F$ is a collection of disjoint even cycles and isolated vertices. Let $C$ be a cycle in $F$ containing $xz$. 
>      
>      - If $C$ doesn't contain $wy$, then taking $(M_{1} \backslash C)\cup (M_{2}\cap C)$ will give us a desired matching in $M_{1}\cup M_{2}$.
>      - If $C$ contains $wy$, we can use either $xy$ or $zy$ to construct a perfect matching for all vertices in $C$. This gives us a perfect matching.

---
> [!lemma] Corollary 7 (Petersen 1891)
> Every $3$-regular graph with no cut-edge has a perfect matching.

> [!proof]-
> Let $S\subseteq V(G)$. Let $H$ be a component of $G \backslash S$ with $\left| H \right|$ odd. Then, the number of edges between $S$ and $H$ cannot be $1$ as there is no cut edge. It also cannot be even as $H$ has odd number of vertices and in this case $3\left| H \right|-\text{even}=\text{odd}=2e_{G}(H)$. Therefore, there are at least three edges from $H$ to $S$. 
> 
> Since $G$ is $3$-regular, every vertex in $S$ is incident to at most $3$ edges between $S$ and $G \backslash S$. Therefore, $$3q(G \backslash S)\leq 3\left| S \right| $$which gives the Tutte condition.

---
> [!lemma] Corollary 8 (Berge 1958)
> For a graph $G$, 
> 1. $2\nu(G)=n+\min_{S\subseteq V}(\left| S \right|-q(G \backslash S))$

> [!proof]+
> Let $d(S):=q(G \backslash S)-\left| S \right|$ and let $d:=\max_{S\subseteq V}d(S)$. For $S\subseteq V$, we have that at most $\left| S \right|$ edges can match vertices from $S$ to odd components of $G \backslash S$, so every matching has at least $d(S)$ unmatched vertices. Therefore, no matching can have more than $n-d$ matched vertices. 
> 
> 
---
##### Matching Algorithms
> [!lemma] Theorem 1 (MWU)
> Let $G=(V,E)$ and $\{ w_{v} \}_{v\in V}\subseteq \mathbb{R}_{\geq 0}$. The ***oracle LP*** on $\{ w_{v} \}_{v\in V}$ is defined as:$$\begin{array}{rll}\max&\sum_{e\in E}^{}x_{e}\\\text{subject to}&\sum_{v\in V}^{}w_{v}\sum_{e\ni v}^{}x_{e}\leq \sum_{v\in V}^{}w_{v} & \\&0\leq x_{e}\leq 1&\forall e\in E\end{array}$$Now, consider the following algorithm: 
> ```pseudo
> \begin{algorithm} \caption{MWUMatching($G,\varepsilon$)}
> \begin{algorithmic} 
> \State $w^{(1)}\gets 1$
> \For{$t=1,\dots,T:=8n\ln n / \varepsilon^{2}$}
> \State $x^{(t)}\gets$ \Call{OracleLP}{$w^{(t)}$}
> \State $w^{(t+1)}_{v}\gets \left( 1+ \frac{\varepsilon}{2n}\sum_{e\ni v}^{}x^{(t)}_{e} \right)w^{(t)}_{v}$
\EndFor
> \Return $\overline{x}:=\frac{1}{T}\sum_{t\in [T]}^{}x^{(t)}$
> \end{algorithmic}
> \end{algorithm}
> ```
> Then, for the output $\overline{x}$, 
> 1. $\sum_{e\in E}^{}\overline{x}_{e}\geq \text{OPT}_{LP}$
> 2. $\sum_{e\ni v}^{}\overline{x}_{e}\leq 1+\varepsilon$ for all $v\in V$

> [!proof]-
> We have that:
> 1. Let $x$ be a feasible solution to the LP relaxation of maximum matching problem. Therefore, $\text{OPT}_{LP}\leq \text{OPT}_{\text{Oracle}LP}$ for any $w$. Hence, we have that: $$\sum_{e\in E}^{}\overline{x}_{e}=\frac{1}{T}\sum_{t\in [T]}^{}\underbrace{ \sum_{e\in E}^{}x^{(t)}_{e} }_{ \geq \text{OPT}_{LP} }\geq \text{OPT}_{LP}$$
> 2. We have the following claims. Let $W^{(t)}:=\sum_{v\in V}^{}w_{v}^{(t)}$. Then,
> 	1. **Claim 1**: $W^{(T+1)}\leq n\cdot\exp(\eta T)$
> 	   
> 	   We have that for all $t$: $$\begin{align}W^{(t+1)}&=\sum_{v\in V}^{}w_{v}^{(t+1)}=\sum_{v\in V}^{}\left( 1+ \frac{\varepsilon}{2n}\sum_{e\ni v}^{}x_{e}^{(t)} \right)w_{v}^{(t)}\\&=W^{(t)}+ \frac{\varepsilon}{2n} \sum_{v\in V}^{}w_{v}^{(t)}\sum_{e\ni v}^{}x_{e}^{(t)}\leq (1+ \frac{\varepsilon}{2n})W^{(t)}\end{align}$$Hence, $W^{(T+1)}\leq(1+ \frac{\varepsilon}{2n})^Tn\leq n\exp \left( \frac{\varepsilon}{2n} T \right)$.
> 	
> 	Assume that there exists $v\in V$ s.t. $\sum_{e\ni v}^{}\overline{x}_{e}>1+\varepsilon$. Then, $\sum_{t\in [T]}^{}\sum_{e\ni v}^{}x^{(t)}_{e}>T(1+\varepsilon)$. Further, we have: $\sum_{e\ni v}^{}x_{e}^{(t)}\leq n$. 
> 	$$\begin{align}w^{(T+1)}_{v}=\prod_{t=1}^{T}\left( 1+ \frac{\varepsilon}{2n} \sum_{e\ni v}^{}x_{e}^{(t)} \right)&\geq\prod_{t=1}^{T}\exp \left( \eta \sum_{e\ni v}^{}x_{e}^{(t)}-\eta^{2}\left( \sum_{e\ni v}^{}x_{e}^{(t)} \right)^{2}  \right)\\&\geq\exp \left( \eta \sum_{t\in[T]}^{}\sum_{e\ni v}^{}x_{e}^{(t)}-\eta^{2} \sum_{t\in[T]}^{}\left( \sum_{e\ni v}^{}x_{e}^{(t)} \right)^{2}  \right)\\&\geq\exp \left( \eta \sum_{t\in[T]}^{}\sum_{e\ni v}^{}x_{e}^{(t)}-\eta^{2} \sum_{t\in[T]}^{}\left( \sum_{e\ni v}^{}x_{e}^{(t)} \right)^{2}  \right) \end{align}$$
---
> [!lemma] Theorem 2 (Streaming Perfect Matching)
> Any randomized single-pass streaming algorithm deciding whether a bipartite graph $G=(U\sqcup V ,E)$ has a perfect matching requires $\Omega(n^{2})$ space.

> [!proof]-
> We show that for any randomized algorithm using at most $cn^{2}$ bits, 
> 
> Let $k\in \mathbb{Z}_{\geq 0}$ and let $G=(U\sqcup V,E)$ be a bipartite graph where $U:=U_{1}\sqcup U_{2}$ and $V:=V_{1}\sqcup V_{2}$. We have that $\left| U_{1} \right|=\left| V_{1} \right|=k$ and $\left| U_{2} \right|=\left| V_{2} \right|=k-1$. Let $e_{1},\dots,e_{k^{2}}$ be a fixed order of edges between $U_{1}$ and $V_{1}$. 
> 
> We sample each edge $e_{i}$ uniformly at random, independently. This gives us 

---
##### Examples

> [!h] Example 1
> We have that:
> 1. $\nu(K_{n})= \left\lfloor \frac{n}{2}\right\rfloor$
> 2. $\nu(K_{r,s})=\min \{ r,s \}$.

^ef41f6

---
