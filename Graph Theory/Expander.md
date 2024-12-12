#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be an [[Graph|undirected graph]]. For any $0<\phi\leq 1$, 
> 1. A [[Cut (Graph)|cut]] $(S, V\backslash S)$ is ***$\phi$-sparse*** if $\left| E(S, V \backslash S) \right|<\phi\min \left\{  \text{vol}_{G}(S), \text{vol}_{G}(V \backslash S)  \right\}$.
> 3. $G$ is a ***$\phi$-expander*** if $G$ contains no $\phi$-sparse cut.
- **Related definition**: For $S\subseteq V$, the ***volume*** is defined as $\text{vol}_{G}(S):=\sum_{v\in S}^{}d_{G}(v)$. 
- **Related definition**: For a graph $G=(V,E)$, a partition $V_{1},\dots,V_{\ell}$ of $V$ is a ***$\phi$-expander decomposition*** if:
	1. $G[V_{i}]$ is a $\phi$-expander for all $i\in[\ell]$.
	2. $\left| \bigcup_{i\neq j}^{}E(V_{i},V_{j}) \right|=\tilde{O}(\phi m)$.
---
##### Properties

> [!lemma] Lemma 1 (Basic Lemma)
> For any $G=(V,E)$ and $S\subseteq V$:
> 1. $e(S, V \backslash S)\leq \text{vol}_{G}(S)\leq 2e(S, V \backslash S)$ 

> [!proof]+
> We have that:
> 1. The left inequality is trivial as every cut edge contributes to the volume. For the upper inequality, we have that: $$\sum_{v\in S}^{}d_{G}(v)$$
---
> [!lemma] Theorem 2 (Expander Decomposition)
> Consider the following algorithm:
> ```pseudo
> \begin{algorithm} \caption{ExpanderDecomposition($G,\phi$)}
> \begin{algorithmic} 
> \State $\mathcal{V}\gets \{ V \}$
> \While{ there exists $V_{i}\in \mathcal{V}$ s.t. $G[V_{i}]$ is not a $\phi$-expander}
> \State $(S,V_{i} \backslash S)\gets \phi$-sparse cut in $G[V_{i}]$
> \State Replace $V_{i}$ by $S,V_{i} \backslash S$ in $\mathcal{V}$
\EndWhile
\Return $\mathcal{V}$
\end{algorithmic}
\end{algorithm}
> ```
> Then, for every $0<\phi<1$, the algorithm returns a $\phi$-expander decomposition in polynomial time.

> [!proof]+
> By construction, $G[V_{i}]$ is a $\phi$-expander for all $V_{i}\in \mathcal{V}$ in the output. 
> 
> 
> 
> Let $(S,V_{i} \backslash S)$ be a $\phi$-sparse cut in $G[V_{i}]$ where wlog $\sum_{v\in S}d_{G}(v)\leq \sum_{v\in V \backslash S}^{}d_{G}(v)$. Then, we add at most $\phi \sum_{v\in S}^{}d_{G[V_{i}]}(v)\leq \phi \sum_{v\in S}d_{G}(v)$ to $E_{\text{rest}}:=\bigcup_{i\neq j}^{}E(V_{i},V_{j})$. Therefore, for each $v\in S$, we can charge at most $\phi d_{G}(v)$ to pay for the contribution in $E_{\text{rest}}$.
> 
> However, notice that after replacing $V_{i}$ with $S,V_{i} \backslash S$, we have that $$\sum_{v\in S}^{}d_{G[S]}(v)=\sum_{v\in S}^{}d_{G[V_{i}]}(v)-e_{G[V_{i}]}(S,V_{i} \backslash S)\leq \frac{1}{2}\sum_{v\in S}^{}d_{G[V_{i}]}(v)$$

---
##### Examples
> [!h] Example 1
> $K_{n}$ is a $\frac{1}{2}$-expander.

> [!proof]-
> Let $S\subseteq V$ with $\left| S \right|=k\leq n / 2$. Assume $(S,V\backslash S)$ is a $\frac{1}{2}$-sparse cut. Then, $$\frac{kn}{2}\leq|S||V \backslash S|=\left| E(S,V \backslash S) \right| < \frac{1}{2}(n-1)k$$which is a contradiction.
---
