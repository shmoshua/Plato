#Definition #Algorithms 

> [!definition]
> Let $G=(V,E)$ be an [[Graph|undirected graph]] on $n$ vertices with weights $w:E \to \mathbb{R_{\geq 0}}$. For $\varepsilon>0$, a ***cut sparsifier*** is a subgraph $H=(V,E')$ s.t. $E'\subseteq E$ with weights $w':E'\to \mathbb{R_{\geq 0}}$ s.t.
> 1.  $\left| E' \right|=\tilde{O}(n / \varepsilon^{2})$ and
> 2. $\left| w'(E_{H}(S, V \backslash S))-w(E_{G}(S, V \backslash S)) \right|\leq \varepsilon w(E_{G}(S, V \backslash S))$ for all $S\subseteq V$.
---
##### Properties
> [!lemma] Theorem 1 (Complete Graphs)
> Consider the following algorithm: 
> ```pseudo
> \begin{algorithm}\caption{CutSparsifierCompleteGraphs($n,\varepsilon$)}
> \begin{algorithmic} 
> \State $G\gets K_{n}$
> \State $p\gets 30\frac{\log n}{\varepsilon^{2}n}$
> \State $H\gets (V,\varnothing)$
> \For{$e=\{ u,v \}\in E(G)$}
> \State Add $e$ to $H$ with weight $w'(e)=1 / p$ with probability $p$ independently.\EndFor
> \Return $H$
\end{algorithmic}
\end{algorithm}
> ```

