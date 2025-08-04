#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a [[graph]].
> 1. A ***path*** is a [[walk]] $W=(v_{1},\dots,v_{k})$ s.t. $v_{i}\neq v_{j}$ for all $i\neq j$.
> 2. A **cycle** is a walk $W=(v_{1},\dots,v_{k})$ where $v_{1}=v_{k}$ and $(v_{1},\dots,v_{k-1})$ is a path.

^9274a2

- **Related Notation**: The ***length*** of a walk $W$ is given by the number of edges in $W$. ^14b918
- **Related Notation**: 
	1. For $u,v\in V$, a $(u,v)$-***path*** is a path $(v_{1},\dots,v_{k})$ s.t. $u=v_{1}$ and $v=v_{k}$.
	2. For $A,B\subseteq V$, a ***$AB$-path*** is a path with one endpoint in $A$, the other in $B$ and all interior points in $V \backslash (A\cup B)$. ^150295
- **Related Definition**: A graph $G$ is ***connected*** if for every $v,w\in G$, there exists a $(v,w)$-path. ^0c6bd0
- **Related Definition**: Two paths are ***independent*** if they do not share an inner node.
- **Related Definition**: For $s,t\in V$, the ***distance*** $d_{G}(s,t)$ is the length of the shortest $(s,t)$-path in $G$. If such path doesn't exist, $d_{G}(s,t)=\infty$.
- **Related Definition**: The ***diameter*** of a graph is $\text{diam}(G):= \max_{s,t\in V}d_{G}(s,t)$.
- **Related Definition**: For a connected graph $G$, an edge $e\in E$ is a ***cut edge***, if $G \backslash e$ is not connected. 
- **Related definition**: For a path $P$ and $x\in P$, $x^+,x^-$ are the vertex preceding and following $x$ on $P$, if they exist. For $X\subseteq V(P)$:
	1. $X^+:=\{ x^+:x\in X \}$.
	2. $X^-:=\{ x^-:x\in X \}$.
- **Related definition**: A path $P'$ is ***rotated from $P:=v_{0}\dots v_{n}$*** if it is of the form $$P':=v_{i}v_{i-1}\dots v_{0}v_{i+1}\dots v_{n}$$A path $P'$ is ***derived from $P$*** if it is obtained by a sequence of rotations from $P$. $S(P)\subseteq V(P)$ is the set of all starting vertices of paths dervied from $P$.
---
##### Properties
> [!lemma] Proposition 1
> Let $G$ be a graph and $u,v\in V$. 
> 1. any $(u,v)$-walk contains a $(u,v)$-path. 

^82af28

> [!proof]-
> Let $(v_{1},\dots,v_{k})$ be a $(u,v)$-walk. We show by induction over $k$. 
> 1. if $k=2$, then the walk is also a path.
> 2. if $k\geq 3$, then if there is no $i\neq j$ with $v_{i}=v_{j}$, then we have a path and we're done. Suppose otherwise. Then, wlog assume $i<j$ and: $$(v_{1},\dots,v_{i-1},v_{j},\dots,v_{k})$$ is a $(u,v)$-walk and by induction we have a $(u,v)$-path. 

^4d3705

---
> [!lemma] Proposition 2
> For a finite graph $G$ with $\delta(G)\geq 2$,
> 1. $G$ has a path of length $\delta(G)$. 
> 2. $G$ has a cycle of length at least $\delta(G)+1$.

^4e3ecc

> [!proof]-
> We have:
> 1. Let $x_{0}\dots x_{k}$ be the longest path in $G$. Then, all the neighbors of $x_{k}$ are on the path. Hence, $k\geq d(x_{k})\geq\delta(G)$.
> 2. Further, with $x_{k}$, we get a cycle of length at least $\delta(G)+1$.

^ccedf3

- **Remark**: This result is tight! Consider $K_{\delta+1}$ for any $\delta\geq 2$. ^590fcb
---
> [!lemma] Proposition 3
> Let $G$ be a $n$-vertex graph with $m$ edges. Then, 
> 1. $G$ has at least $n-m$ connected components. 

^aec20e

> [!proof]-
> Delete all edges and get empty graph. Put edges back one by one and track the number of components. 
> 
> Then, for all $m$, the number of connected components can decrease by at most 1. As we have $n$ connected components in the beginning, we have the claim. 

^0d4367

---
> [!lemma] Lemma 4
> Let $G$ be a connected graph. 
> 1. Any edge in a cycle is not a cut edge.

^9e5831

> [!proof]-
> We have that:
> 1. Let $e=\{ u,v \}\in E$ be contained in a cycle, i.e. there exists a $(u,v)$-path $P$ that does not contain $e$ s.t. $P+e$ is a cycle. Therefore, $G \backslash e$ is also connected via $P$. 

^bab021

---
##### Pósa's Lemma
> [!lemma] Lemma 1
> Let $G$ be a graph and $P:=u\dots v$ be the longest path. Let $S:=S(P)$. Then,
> 1. $\partial S\subseteq V(P)$.
> 2. $\partial S\subseteq S^-\cup S^+$ or $V(P)$ forms a cycle in $G$.
> 3. if $d(u)\geq 2$, then $G$ has a cycle containing $S\cup\partial S$.

^c5ca8a

> [!proof]-
> We have that:
> 1. Let $x\in S$ and $y\in N(x)$. As $x\in S$, there is a path $Q:=x\dots v$ derived from $P$. Then, as $Q$ is also a longest path, $y\in V(Q)=V(P)$.
> 2. Let $x\in S$ and $y\in N(x)$ be any neighbor. We will show that $y\in S^-\cup S\cup S^+$. As $x\in S$, there is a path $Q:=x\dots v$ derived from $P$. Further, by 1, $y\in V(P)$.
> 	- if $y=v$, then we have a cycle on $V(P)$.
> 	- otherwise, let $z:=y^-_{Q}$. Suppose that $y\notin S^-\cup S\cup S^+$. We claim that any edge $e\in P$ incident to $y$ lies on every path derived from $P$. Otherwise, in the rotation where $e$ is deleted, one of the endpoints will be added to $S$ and the other into $S^-\cup S^+$. Therefore, $e\in Q$ and $z\in \{ y^+,y^- \}$. However, we can perform a rotation on $Q$ to get:$$Q':=z\dots xy\dots v$$and $z\in S$. Hence, $y\in S^-\cup S\cup S^+$ which is a contradiction. 
> 3. We have that $\partial S\subseteq V(P)$. From 2, if $V(P)$ forms a cycle in $G$ then we have a cycle containing $S\cup \partial S$. Otherwise, $\partial S\subseteq S^-\cup S^+$. Let $y$ be the last vertex of $P$ in $\partial S$. Then, $S\cup \partial S$ would lie on the subpath $P_{1}:=u\dots y$ of $P$, as any vertex in $S$ after $y$ in $P$ would have its successor in $\partial S$. Let $x\in S$ be the neighbor of $y$ in $G$ and let $Q=x\dots v$ be derived from $P$. Then, similar to 2, we have that every edge after $y$ in $P$ are also in every derived path of $P$ and therefore also in $Q$. Let $P_{2}:= y\dots v$ denote the subpath. Then, $P_{2}$ is a subpath of $Q$ as well. Let $Q_{1}$ be a subpath between $x$ and $y$ of $Q$. Then, $$S\cup \partial S \subseteq V(P_{1})=V(P) \backslash V(P_{2})=V(Q_{1})$$and $Q_{1}\cup \{ (y,x) \}$ is a cycle in $G$. Indeed, as $d(u)\geq 2$, there is a non-trivial rotation and $\left| S \right|>1$ and $\left| Q_{1} \right|=\left| P_{1} \right|\geq 3$

^276eab

---
> [!lemma] Corollary 2
> Let $G$ be a graph and $k\geq 2$.
> 1. If for all $S\subseteq V(G)$ with $\left| S \right|\leq k$ we have $\left| \partial S \right|\geq \left| S \right|$, then $G$ has a cycle of length at least $3k$.

^821639

> [!proof]-
> Let $S:=S(P)$ where $P:=u\dots v$ is the longest path. Further, $d(x)\geq 2$ as we can take $S:=\{ x \}$ in the assumption. 
> 
> If $\left| S \right|< k$, then as $u$ has no predecessor, we have that: $$\left| S^-\cup S^+ \right| <2\left| S \right| \leq \left| \partial S \right| $$and therefore, $\partial S\not\subseteq S^-\cup S^+$. This is a contradiction to Lemma 1.2 and we have that $\left| S \right|\geq k$. By Lemma 1.3, we have that there is a cycle containing $S\cup \partial S$. However, for a $k$-element subset $S'\subseteq S$, $$\left| S\cup \partial S \right| \geq \left| S'\cup \partial S' \right| =\left| S' \right| +\left| \partial S' \right| \geq 3\left| S' \right| =3k $$

^6f796d

---
##### Others
> [!lemma] Theorem (Cycles in Digraphs)
> Let $k\in \mathbb{Z}_{\geq 1}$ and $D=(V,E)$ a finite digraph with $\Delta^-$ and $\delta^+$ as the maximal in-degree and minimal out-degree. 
> 1. If it holds that: $$e((\delta^++1)\Delta^-+1)\left( 1-\frac{1}{k} \right) ^{\delta^+}\leq 1$$then $D$ contains a directed cycle of length divisible by $k$.

^eb646f

> [!proof]-
> Let's first remove edges until there are exactly $\delta^+$ out-neighbors for each node. Then, $\delta^+$ stays the same and $\Delta^-$ decreases but the condition still holds. Further, any circle in the new digraph is also one in the old one. 
> 
> Let $c:V\to[k]$ be a random uniform coloring with $\mathbb{P}(c(v)=i)=1 / k$ for all $v\in V$ and $i\in[k]$. For any vertex $v\in V$, let $B_{v}$ be the event that there is no $u$ s.t. $v\to u\in E$ and $c(u)\equiv_{k}c(v)+1$
> 
> We now use the [[Independence|Lovász Local Lemma]].
> 1. $\mathbb{P}(B_{v})= (1-\frac{1}{k})^{\delta^+}$
> 2. $B_{v}$ only depends on the colors of the out-neighbors $N^+(v)$. Therefore, $B_{v}$ is mutually disjoint from all events $B_{u}$ where $\{ v \}\cup N^+(v)$ and $\{ u \}\cup N^+(u)$ are disjoint. This happens exactly when $u$ is either in $\{ v \}\cup N^+(v)$ or is an in-neighbor of one of the vertices. 
>    
>    For each $x\in N^+(v)$, there are at most $\Delta^-$ vertices $u\neq v$ that could be either $u=x$ or $u\to x\in E$. Hence, the total number of vertices $u\neq v$ s.t. $\{ u \}\cup N^+(u)$ intersects $\{ v \}\cup N^+(v)$ is at most $(\delta^++1)\Delta^-$.
> 
> Therefore, by the local lemma, $\mathbb{P}\left( \bigcap_{v\in V}^{}B_{v}^c \right)>0$. 

^c1e54e

---
