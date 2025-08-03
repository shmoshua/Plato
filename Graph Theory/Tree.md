#Definition #GraphTheory 

> [!definition]
> A ***tree*** is an acyclic [[Path|connected]] [[graph]].

^6a6272

- **Related definition**: For a tree $T=(V,E)$, any vertex $v\in V$ with $d(v)=1$ is called  a ***leaf***. ^8551a4
- **Related defintion**: For a connected graph $G$, a ***spanning tree*** $T$ is a tree that is a subgraph of $G$ s.t. $V(T)=V(G)$. ^ce4662
---
##### Properties

> [!lemma] Lemma 1
> Let $T=(V,E)$ be a finite tree with $\left| V \right|\geq 2$. Then, 
> 1. $T$ has at least 2 leaves.
> 2. for any leaf $v\in V$, $T \backslash \{ v \}$ is also a tree.

^8ecefa

> [!proof]-
> We have that:
> 1. Let $P$ be the longest path in tree $T$ with endpoints $u,v$. Since $P$ is the longest, $u,v$ has their neighborhood contained in $P$. However if $d(u)\geq 2$ or $d(v)\geq 2$ then we get a cycle. Hence, $d(u)=d(v)=1$ and $u,v$ are leaves. 
> 2. Let $v$ be a leaf. Then, $T \backslash \{ v \}$ still remains acyclic and connected.

^cffecf

---

> [!lemma] Theorem 2 (Equivalent Definitions of Trees)
> Let $G=(V,E)$ be a non-empty graph. TFAE:
> 1. $G$ is a tree.
> 2. $G$ is connected and $\left| E \right|=\left| V \right|-1$.
> 3. $G$ is acyclic and $\left| E \right|=\left| V \right|-1$
> 4. for all $x,y\in V$ there exists exactly one $(x,y)$-path.

^481b12

> [!proof]-
> We have:
> 1. (1=>2): $G$ is connected by definition. We show by induction on $n:=\left| V \right|$.
> 	1. If $n=1$ it is obvious.
> 	1. If $n\geq 2$, then let $v\in V$ be a leaf (which exists by Lemma 1.1). Then, $G':=G \backslash \{ v \}$ is a tree as well and we have that $\left| E(G) \right|=\left| E(G') \right|+1=n-2+1=n-1$.
> 2. (2=>3): Assume that $G$ has a cycle. Then, by [[Path (Graph)|Lemma 4]], we can take an edge $e\in G$ s.t. $G \backslash e$ is connected and has $n-2$ edges. This contradicts [[Path (Graph)|Proposition 3]].
> 3. (3=>1): Let $V_{1},\dots,V_{k}$ be the connected components of $V$. Then, as each connected components are acyclic and connected, we have that, $\left| E(G[V_{i}]) \right|=\left| V_{i} \right|-1$ for all $i$. Hence, $$\left| V \right| -1=\left| E \right| =\sum_{i=1}^{k}\left| E(G[V_{i}]) \right| =\sum_{i=1}^{k}(\left| V_{i} \right| -1)=\left| V \right| -k$$Hence, $k=1$.
> 4. (1=>4): The existence of path is given by connectedness. We will show that the path is unique. Suppose there exist two paths $P,Q$ from $x$ to $y$. There must exist an edge $e=\{ u,v \}\in P$ that is not in $Q$. Further, there exists a $(u,v)$-walk that doesn't contain $e$. Hence, by [[Path (Graph)|Proposition 1]], the walk contains a $(u,v)$-path and this path doesn't contain $e$. This shows that this path forms a cycle with $e$ and this is a contradiction.
> 5. (4=>1): Connected is given by the existence of paths and if $G$ has a cycle, then there exists two paths. 

^7a33da

---
> [!lemma] Corollary 3
> We have that:
> 1. any connected graph $G$ has a spanning tree.
> 2. every edge in a tree is a [[Path (Graph)|cut edge]].
> 3. adding an edge to a tree creates exactly one cycle.

^848d8c

> [!proof]-
> We have that:
> 1. If $G$ is a tree, we are done. Otherwise, there exists a cycle and we can delete any edge and by [[Path (Graph)|Lemma 4]] we still get a connected graph. As the number of edges decrease by 1 in every step, this holds.
> 2. A tree on $n$ vertices has $n-1$ edges. If we remove one edge, then we have $n-2$ edges and this cannot be connected by [[Path (Graph)|Proposition 3]].
> 3. Let $T$ be a tree and add an edge $e:=u\sim v$ that was not in $T$. Then, as there is a unique $(u,v)$-path and hence adding $e$ creates exactly one cycle. 

^ded13e

---
##### Cayley's Formula
  
> [!definition]
> Let $T$ be a [[tree]] on an ordered set $S$ of $n$ vertices. The ***Prüfer code*** $f(T)$ of $T$ is given by the following process:
> 1. iteratively delete the leaf $v$ with the smallest label
> 2. append the label of $v$'s parent to the sequence.
> 3. After $n-2$ iterations a single edge remains and we have produced a sequence $f(T)$ of length $n-2$.

^7e2ec4

---
> [!lemma] Proposition 1
> Let $T$ be a tree and $f(T)$ the Prüfer code.
> 1. $x\in T$ appears in $f(T)$ if and only if $x$ is not a leaf.

^97eff3

> [!proof]-
> If $x$ is a leaf, by construction $x$ cannot appear in $f(T)$.
>
> Conversely, if $x$ is not a leaf, there exists $\{ u,v \}\subseteq N(x)$. As only leaves can be deleted, either $u$ or $v$ will be deleted before $x$. Hence, $x$ appears in $f(T)$.

^0b054b


---
> [!lemma] Theorem 2
> Let $S$ be an ordered set of $n$ vertices. The following map is a bijection: $$\{ \text{Trees on }S \}\to S^{n-2},\quad T\mapsto f(T)$$

^fa0d83

> [!proof]+
> We prove this by induction over $n$.
> 1. If $n=2$, then there exists only one tree on $S$ and this is uniquely given.
> 2. If $n\geq 3$, we know that $f(T)$ has length $n-2$ for all $f$. To show that it is a bijection, let $s_{1},\dots,s_{n-2}\in S$ be a sequence.
>
> Let $s^{*}$ be the smallest element in $S$ s.t. it does not appear in $s_{1},\dots,s_{n-2}$. Then, by induction there exists a unique tree $T$ on $S \backslash \{ s^{*} \}$ s.t. $f(T)=(s_{2},\dots,s_{n-2})$. Now, consider $T':=T\cup \{ s^{*}s_{1} \}$. Then, $$f(T')=(s_{1},\dots,s_{n-2})$$by Proposition 1 as $s^{*}$ is the leaf with the smallest label by definition. Hence, there exists a unique tree $T'$ on $S$ with $f(T')=(s_{1},\dots,s_{n-2})$.

^6c8dad

- **Corollary: (Cayley)** There are $n^{n-2}$ different labelled trees on $n$ vertices. ^b2855c

---

> [!lemma] Corollary 3 (Cayley's Formula)
> There are $n^{n-2}$ different labelled trees on $n$ vertices.

^5bf805

  

> [!proof]- Proof (Prüfer code)
> Follows from Theorem 2.

^8ff773

> [!proof]- Proof (Joyal, 1981)
> Let $\mathcal{F}$ be a set of tuples $(T,\ell,r)$ where $T$ is a labelled tree on $n$ vertices and $\ell$ and $r$ are two vertices. Then, it suffices to show that: $$\left| \mathcal{F} \right| =n^n$$
>
> Let $f:[n]\to[n]$ be an arbitrary function and let $D_{f}=([n],E)$ be the digraph that is generated from $f$, i.e. $x\to y\iff y=f(x)$. Then, $e(D_{f})=n$ and $d^+\equiv 1$.
>
> Notice that every connected component in $D_{f}$ contains exactly one directed cycle and every other vertex is part of a tree that is attached to the cycle in the component.
>
> Now, let $N:=\{ i\in[n]: i\text{ is in a cycle in }D_{f} \}$. Then, $N$ is the unique maximal subset of $[n]$ s.t. $f|_{N}$ is a bijection. Let $N=\{ v_{1},\dots,v_{k} \}$ be ordered i.e. $v_{i}\leq v_{i+1}$. Then, we construct $(T,\ell,r)$ where,
> 1. $T$ is a union of the path $f(v_{1})\dots f(v_{k})$ and the trees that are attached to the cycles in $D_{f}$.
> 2. $\ell:=f(v_{1})$ and $r:=f(v_{k})$.
>
> To show that this forms a bijection, let $(T,\ell,r)$. Then, there exists a unique $\ell r$-path. Hence, we can construct a function $f$ s.t. that path is given by $N=\{ v_{1},\dots,v_{k} \}$ and more precisely $f(v_{1})\dots f(v_{k})$.

^1fd061

---
> [!lemma] Theorem 4 (Matrix-Tree Theorem)
> Let $G$ be a connected graph. Let $t(G)$ be the number of spanning trees of $G$. Then, 
> $$t(G)=\det (D-A)_{ii}$$where $M_{ii}$ is the submatrix of $M$ given by deleting the $i$-th row and column.

> [!proof]+
> We have that $BB^\top = D-A$. Further $B$ has at least $n-1$ columns as $G$ is connected. 
---
##### Spanning Tree

> [!lemma] Theorem 4 (Boruvka)
>  ```pseudo
>    \begin{algorithm} \caption{ComputeSpanningForest($G$)} 
>    \begin{algorithmic}
>    
>    \State $F\gets (V,\varnothing)$
>    \For{$t = 1,...,\left\lceil \log n\right\rceil$}
>    \State Let $A_1,\dots,A_{k}$ be the connected components of $F$.
>    \For{$j\in[k]$}
>    \State Find an edge $e\in E(A_{i}, V \backslash  A_{i})$ and add it to $F$.
>    \EndFor 
>    \While{ there exists a cycle $C$ in $F$}
>    \State Delete an arbitrary edge $e\in C$ from $F$.
>    \EndWhile
>    \EndFor
>    \Return $F$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    The algorithm $\text{ComputeSpanningForest}$ returns a maximal spanning forest.

^7be53d

> [!proof]-
> Fix any iteration of the outer for loop. Let $A_{1},\dots,A_{k}$ be the connected components of the forest $F$ at the beginning of the loop iteration.
> 
> Since we add a cut edge from $(V_{i},A \backslash V_{i})$ for each $i$ to $F$, we have that each formerly connected component $A_{i}$ is now connected to at least one other component $A_{j}$. Thus, the number of connected components is at most $k / 2$.
> 
> It remains to observe that removing an edge from a cycle $e\in C$ does not affect the connected components. Thus, after each for-loop iteration, the number of connected components is at least halved.
---
