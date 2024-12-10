#Definition #GraphTheory #Algorithms 

> [!definition]
> Let $G=(V,E)$ be an [[Graph|undirected graph]] on $n$ vertices with weights $w:E \to \mathbb{R_{\geq 0}}$. For any $k\geq 1$, a ***graph spanner*** is a graph $H=(V,E')$ with weights $w':E'\to \mathbb{R_{\geq 0}}$ s.t.
> 1.  $\left| E' \right|=O(n^{1+1 / k})$ and
> 2. $d_{G}(u,v)\leq d_{H}(u,v)\leq(2k-1)d_{G}(u,v)$ for all $u,v\in V$.
---
##### Properties
> [!lemma] Theorem 1 (Greedy)
> Consider the following algorithm:
> ```pseudo
> \begin{algorithm}\caption{ComputeSpanner($G=(V,E),k$)}
> \begin{algorithmic} 
> \State $H\gets (V,\varnothing)$
> \State Sort the edges by weight into $e_{1},\dots,e_{m}$.
> \For{$i\in[m]$}
> \If{$d_{H}(u,v)>(2k-1)w(e_{i})$}
> \State $H\gets H\cup \{ e \}$\EndIf\EndFor
> \Return $H$ with $w'=w|_{E(H)}$.
\end{algorithmic}
\end{algorithm}
> ```
> We have that:
> 1. For every $e=\{ u,v \}\in E$, $d_{H}(u,v)\leq (2k-1)w(e)$.
> 2. $\text{ComputeSpanner}(G,k)$ is a spanner of $G$.

> [!proof]+
> We have that:
> 1. Let $e=\{ u,v \}\in E$. If $e\notin H$, then $d_{H}(u,v)\leq (2k-1) w(e)$ and we are done. Hence, assume that $e\in H$. Then, $d_{H}(u,v)\leq w(e)$ and we are done.
> 1. Firstly, as $E(H)\subseteq E(G)$, we have that $d_{G}(u,v)\leq d_{H}(u,v)$ for all $u,v\in V$. For $u,v\in V$ let $\pi_{u,v}=(u=x_{1},x_{2},\dots,x_{k}=v)$ be the shorted $u$-$v$-path in $G$. Then, from 1,$$d_{H}(u,v)\leq \sum_{i\in[k-1]}^{}d_{H}(x_{i},x_{i+1})\leq (2k-1)\sum_{i\in[k-1]}^{}w(\{ x_{i} ,x_{i+1}\})=(2k-1)d_{G}(u,v)$$
> 2. To show that $\left| E(H) \right|=O(n^{1+1/k})$, we first claim that for the [[Girth and Circumference|girth]], $g(H)>2k$. Assume that $g(H)\leq 2k$. Then, there exists a cycle $C$ in $H$ with length at most $2k$. Let $e=\{ u,v \}\in C$ be the one that is added the last, i.e. with the largest weight. Let $H'$ be $H$ before adding $e$. 
>    
>    We have that: $$d_{H'}(u,v)\leq\sum_{e'\in C \backslash \{ e \}}^{}w(e')\leq(\left| C \right| -1)w(e)\leq (2k-1)w(e)$$which is a contradiction to the fact that $e\in H$. 
