#Definition #GraphTheory #Algorithms 

> [!definition]
> Let $G=(V,E)$ be an [[Graph|undirected graph]] on $n$ vertices with weights $w:E \to \mathbb{R_{\geq 0}}$. For any $k\geq 1$, a ***$(\alpha,\beta)$-graph spanner*** is a graph $H=(V,E')$ with weights $w':E'\to \mathbb{R_{\geq 0}}$ s.t.
> 1.  $\left| E' \right|=O(n^{1+1 / k})$ and
> 2. $d_{G}(u,v)\leq d_{H}(u,v)\leq \alpha d_{G}(u,v)+\beta$ for all $u,v\in V$.

^c6a9ed

---
##### Properties
> [!lemma] Theorem 1 (Greedy)
> Consider the following algorithm:
> ```pseudo
> \begin{algorithm}\caption{GreedySpanner($G=(V,E),k$)}
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
> 2. $\text{GreedySpanner}(G,k)$ is a $(2k-1,0)$-spanner of $G$.

^1b3b1b

> [!proof]-
> We have that:
> 1. Let $e=\{ u,v \}\in E$. If $e\notin H$, then $d_{H}(u,v)\leq (2k-1) w(e)$ and we are done. Hence, assume that $e\in H$. Then, $d_{H}(u,v)\leq w(e)$ and we are done.
> 1. Firstly, as $E(H)\subseteq E(G)$, we have that $d_{G}(u,v)\leq d_{H}(u,v)$ for all $u,v\in V$. For $u,v\in V$ let $\pi_{u,v}=(u=x_{1},x_{2},\dots,x_{k}=v)$ be the shorted $u$-$v$-path in $G$. Then, from 1,$$d_{H}(u,v)\leq \sum_{i\in[k-1]}^{}d_{H}(x_{i},x_{i+1})\leq (2k-1)\sum_{i\in[k-1]}^{}w(\{ x_{i} ,x_{i+1}\})=(2k-1)d_{G}(u,v)$$
> 2. To show that $\left| E(H) \right|=O(n^{1+1/k})$, by [[Girth and Circumference|Bondy-Simonovits]], it suffices to show that for the [[Girth and Circumference|girth]], $g(H)>2k$. Assume that $g(H)\leq 2k$. Then, there exists a cycle $C$ in $H$ with length at most $2k$. Let $e=\{ u,v \}\in C$ be the one that is added the last, i.e. with the largest weight. Let $H'$ be $H$ before adding $e$. 
>    
>    We have that: $$d_{H'}(u,v)\leq\sum_{e'\in C \backslash \{ e \}}^{}w(e')\leq(\left| C \right| -1)w(e)\leq (2k-1)w(e)$$which is a contradiction to the fact that $e\in H$. 

^20abf3

---

> [!lemma] Theorem 2
> Consider the following algorithm: 
> ```pseudo
> \begin{algorithm}\caption{RandomizedSpanner($G=(V,E),k$)}
> \begin{algorithmic} 
> \State $H\gets (V,\varnothing)$
> \For{$t=1,\dots,k$}
> \State $A_{1},\dots,A_{\ell}\gets$ connected components of $H$
> \State $A_{i}$ is `dead' with probability $1-n^{-1/k}$ independently for all $i\in[\ell]$
> \State $A_{i}$ is `dead' for all $i\in[\ell]$ with probability 1 if $t=k$.
> \For{all $v\in A_{i}$ where $A_{i}$ is dead}
> \If{ there exists $u\in N(v)\cap \bigcup_{A_{j}\text{ alive}}^{}A_{j}$}
> \State $H\gets H\cup \{  u,v \}$
> \State $A_{j}\gets A_{j}\cup \{ u,v \}$
> \Else
> \State $H\gets H\cup \{ u,v \}$ where $u\in N(v)\cap A_{j}$ for all $j$, one edge per each $j$.
> \EndIf
> \EndFor
> \EndFor
> \Return $H$
> \end{algorithmic}
> \end{algorithm}
> ```
> Let $G$ be an unweighted graph and $H$ be the output of the algorithm. Then, 
> 1. $\mathbb{E}[\left| H \right|]=O(kn^{1+1 /k})$.
> 3.  $d_{G}(u,v)\leq d_{H}(u,v)\leq (2k-1)d_{G}(u,v)$ for all $u,v\in V$.
> 4. The runtime of the algorithm is $\tilde{O}(m)$.

^46d296

> [!proof]-
> We have that:
> 1. Let $v$ be a vertex with $d$ neighboring clusters. Then, $$\mathbb{E}[\#\text{edges added by }v]\leq\left( 1-\frac{1}{n^{1/k}} \right)^d d+1\leq e^{-d/n^{1 / k}}d+1\leq n^{1/k}+1=O(n^{1/k})$$Hence, $\mathbb{E}[\#\text{edges added in one phase}]=O(n^{1+1/k})$.
>    
>    For the last phase, if we have $X$ surviving clusters, We add at most $nX$ new edges. Thus,  $$\mathbb{E}[\#\text{edges added in last phase}]\leq n\mathbb{E}[X]$$
>    For a cluster $A_{i}$, we have that: $\mathbb{P}(A_{i}\text{ is surviving})=(n^{-1/k})^{k-1}=n^{-(1-1/k)}$. Hence, $$\mathbb{E}[X]=nn^{-(1-1/k)}=n^{1/k}$$which proves the statement.
> 2. Firstly, as $E(H)\subseteq E(G)$, we have again that $d_{G}(u,v)\leq d_{H}(u,v)$. For the other inequality, we claim that:
> 	1. **Claim 1**: Before phase $i$, if $u,v$ are in the same cluster is their distance in $H$ is at most $2i-2$.
> 	   For $i=1$, each cluster is singleton and we have the claim. For $i\geq 2$, Assume $u,v$ are both added in this phase (to $u'$,$v'$ respectively where $u',v'$ are in the same cluster in the previous phase). We have that: $$d_{H}(u,v)\leq d_{H}(u',v')+2\leq 2(i-1)-2+2=2i-2$$
> 	2. **Claim 2**: After phase $k$, $d_{H}(u,v)\leq 2k-1$. 
> 	   For $u,v\in V$, if $u,v$ in the same cluster then: $d_{H}(u,v)\leq 2i-2\leq 2k-2\leq 2k-1$. Since we only add edges afterwards, the distance can only decrease.

^ae8ead

---
