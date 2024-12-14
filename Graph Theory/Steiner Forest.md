#Definition #Algorithms #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be an [[graph|undirected graph]] with edge weight $w: E\to \mathbb{R}_{\geq 0}$. For a given set of terminals $\{ s_{i},t_{i} \}_{i\in[k]}$, the ***Steiner forest problem*** aims to find: $$E'\in\underset{ \begin{array}{c}E'\subseteq E\\ \forall i\in[k]:  d_{G[E']}(s_{i},t_{i})<+\infty\end{array} }{ \arg\min }w(E')$$

^3e602d

---
##### Properties
> [!lemma] Theorem 1 (Tree Embedding)
> ```pseudo
> \begin{algorithm} \caption{SteinerForestTreeEmbedding($G,w$)}
> \begin{algorithmic} 
> \State $E'\gets \varnothing$
> \State $T\gets$\Call{TreeEmbedding}{$G$}
> \State $T\gets$\Call{Contract}{$T$}
> \For{$i\in[k]$}
> \State $p_{i}\gets$ shortest $s_{i}$-$t_{i}$-path in $T$
> \For{$e=\{ u,v \}\in p_{i}$}
> \State $q_{e}\gets$ shortest $u$-$v$-path in $G$
> \State $E'\gets E'\cup q_{e}$
> \EndFor
> \EndFor
> \Return $E'$
> \end{algorithmic}
> \end{algorithm}
> ```
> Then, $\mathbb{E}[w(E')]\leq O(\log n)w(E'_{\text{OPT}})$.

^79a6c9

> [!proof]-
> We see that $\text{OPT}(T)=\bigcup_{i\in[k]} p_{i}$. Then, let $e\in \text{OPT}(T)$. Then, we have that: $$w_{T}(\text{OPT}(T))=\sum_{\{ u,v \}\in \text{OPT}(T)}^{}d_{T}(u,v)\geq\sum_{\{ u,v \}\in \text{OPT}(T)}^{}d_{G}(u,v)\geq w(E')$$Further, we have that: $$O(\log n)w(E'_{\text{OPT}})=O(\log n)\sum_{\{ u,v \}\in E'_{\text{OPT}}}^{}d_{G}(u,v)\geq \sum_{\{ u,v \}\in E'_{\text{OPT}}}^{}d_{T}(u,v)\geq w_{T}(\text{OPT}(T))$$Hence, we have the statement.

^d4e5b3

---
