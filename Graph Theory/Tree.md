#Definition #GraphTheory 

> [!definition]
> A ***tree*** is an acyclic [[Path|connected]] [[graph]].

- **Related definition**: For a tree $T=(V,E)$, any vertex $v\in V$ with $d(v)=1$ is called  a ***leaf***.

---
##### Properties
> [!lemma] Theorem 1
> Let $G=(V,E)$ be a non-empty graph. TFAE:
> 1. $G$ is a tree.
> 2. $G$ is connected and $\left| E \right|=\left| V \right|-1$.
> 3. $G$ is acyclic and $\left| E \right|=\left| V \right|-1$
> 4. for all $x,y\in V$ there exists exactly one $(x,y)$-path.

> [!proof]-
> We have:
> 1. (1=>2): $G$ is connected by definition. 
---
> [!lemma] Lemma 1
> Let $T=(V,E)$ be a finite tree with $\left| V \right|\geq 2$. Then, 
> 1. $T$ has at least 2 leaves.
> 2. for any leaf $v\in V$, $T \backslash \{ v \}$ is also a tree.

> [!proof]-
> We have that:

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

> [!proof]-
> Fix any iteration of the outer for loop. Let $A_{1},\dots,A_{k}$ be the connected components of the forest $F$ at the beginning of the loop iteration.
> 
> Since we add a cut edge from $(V_{i},A \backslash V_{i})$ for each $i$ to $F$, we have that each formerly connected component $A_{i}$ is now connected to at least one other component $A_{j}$. Thus, the number of connected components is at most $k / 2$.
> 
> It remains to observe that removing an edge from a cycle $e\in C$ does not affect the connected components. Thus, after each for-loop iteration, the number of connected components is at least halved.
---
