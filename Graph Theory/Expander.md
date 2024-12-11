#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be an [[Graph|undirected graph]]. For any $0<\phi\leq 1$, 
> 1. A [[Cut (Graph)|cut]] $(S, V\backslash S)$ is ***$\phi$-sparse*** if $\left| E(S, V \backslash S) \right|<\phi\min \left\{  \sum_{v\in S}^{}d(v), \sum_{v\in V \backslash S}^{}d(v)  \right\}$.
> 2. $G$ is a ***$\phi$-expander*** if $G$ contains no $\phi$-sparse cut.
- **Related definition**: For a graph $G=(V,E)$, a partition $V_{1},\dots,V_{\ell}$ of $V$ is a ***$\phi$-expander decomposition*** if:
	1. $G[V_{i}]$ is a $\phi$-expander for all $i\in[\ell]$.
	2. $\left| \bigcup_{i\neq j}^{}E(V_{i},V_{j}) \right|=\tilde{O}(\phi m)$.
---
##### Properties
> [!lemma] Theorem 1 (Expander Decomposition)
> Consider the following algorithm:
> ```pseudo
> \begin{algorithm} \caption{ExpanderDecomposition($G,\phi$)}
> \begin{algorithmic} 
> \State $\mathcal{V}\gets \{ V \}$
> \While{ there exists $V_{i}\in \mathcal{V}$ s.t. $G[V_{i}]$ is not a $\phi$-expander}
> \State $(S,V \backslash S)\gets \phi$-sparse cut in $G[V_{i}]$
> \State Replace $V_{i}$ by $S,V \backslash S$ in $\mathcal{V}$
\EndWhile
\Return $\mathcal{V}$
\end{algorithmic}
\end{algorithm}
> ```
> Then, for every $0<\phi<1$, the algorithm returns a $\phi$-expander decomposition in polynomial time.

> [!proof]+
> By construction, $G[V_{i}]$ is a $\phi$-expander for all $V_{i}\in \mathcal{V}$ in the output. 
> 
> Let $(S,V \backslash S)$ be a $\phi$-sparse cut in $G[V_{i}]$ where wlog $\sum_{v\in S}d_{G}(v)\leq \sum_{v\in V \backslash S}^{}d_{G}(v)$. Then, we add at most $\phi \sum_{v\in S}^{}d_{G[V_{i}]}(v)\leq \phi \sum_{v\in S}d_{G}(v)$

---
##### Examples
> [!h] Example 1
> $K_{n}$ is a $\frac{1}{2}$-expander.

> [!proof]-
> Let $S\subseteq V$ with $\left| S \right|=k\leq n / 2$. Assume $(S,V\backslash S)$ is a $\frac{1}{2}$-sparse cut. Then, $$\frac{kn}{2}\leq|S||V \backslash S|=\left| E(S,V \backslash S) \right| < \frac{1}{2}(n-1)k$$which is a contradiction.
---
