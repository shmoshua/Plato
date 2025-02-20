#Definition #GraphTheory 

> [!definition]
> A ***tree*** is an acyclic [[Path|connected]] [[graph]].

^6a6272

- **Related definition**: For a tree $T=(V,E)$, any vertex $v\in V$ with $d(v)=1$ is called  a ***leaf***. ^8551a4

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

> [!proof]+
> We have:
> 1. (1=>2): $G$ is connected by definition. We show by induction on $n:=\left| V \right|$.
> 	1. If $n=1$ it is obvious.
> 	1. If $n\geq 2$, then let $v\in V$ be a leaf (which exists by Lemma 1.1). Then, $G':=G \backslash \{ v \}$ is a tree as well and we have that $\left| E(G) \right|=\left| E(G') \right|+1=n-2+1=n-1$.
> 2. (2=>3): Assume that $G$ has a cycle. Then, by [[Path (Graph)|Lemma 4]], we can take an edge $e\in G$ s.t. $G \backslash e$ is connected and has $n-2$ edges. This contradicts [[Path (Graph)|Proposition 3]].
> 3. (3=>4)

^7a33da

---
> [!lemma] Theorem 3 (Boruvka)
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
