#Definition #Algorithms 

> [!definition]
> Given an undirected [[graph]] $G=(V,E)$, a ***tree embedding*** is a [[random variable]] $T$  where $T$ is a weighted [[tree]] on $V$ s.t.
> 1. for all $u,v\in V$, $d_{G}(u,v)\leq d_{T}(u,v)$.
> 2. there exists a $c>0$ s.t. for all $u,v\in V$, $\mathbb{E}[d_{T}(u,v)]\leq c\cdot d_{G}(u,v)$

^4915f3

---
##### Properties
> [!lemma] Theorem 1 (Low Diameter Decomposition)
> Let $G=(V,E)$ be an undirected graph with $n:=\left| V \right|$ and $D\geq 0$.
> ```pseudo
> \begin{algorithm} \caption{LDD$(G,D)$}
> \begin{algorithmic}
> \State $\delta\gets [D / 8, D / 4]$ sampled uniformly at random.
> \State $\pi \gets S_{V}$, sample uniformly  a random permutation.
> \For{$v\in V$}
> \State $C_{i}\gets B_{\leq \delta}(\pi(v)) \backslash \bigcup_{j<i}^{}C_{j}$
\EndFor
> \end{algorithmic}
> \end{algorithm}
> ```
> 
> Ignoring empty sets, the algorithm outputs a partition $V=\bigsqcup_{i\in[k]}^{} C_{i}$ s.t. 
> 1. for all $i\in[k]$, $\text{diam}(C_{i})\leq D$
> 2. there exists $\alpha\in \text{O}(\log n)$ s.t. for all $v\in V$ and $0\leq r\leq D$, $\mathbb{P}(B_{\leq r}(v)\text{ is cut})\leq \alpha r / D$.
> 3. there exists $\alpha\in \text{O}(\log n)$ s.t. for all $u,v\in V$, $\mathbb{P}(\forall i:\{ u,v \}\nsubseteq C_{i})\leq \alpha d(u,v) / D$.

^15e851

> [!proof]-
> We have that:
> 1. Obvious.
> 2. Let $v\in V$ and $r\geq 0$. We will sort the nodes into $v=v_{0},v_{1},\dots,v_{n-1}$. 
> 	1. **Claim 1**: If $C_{i}$ is the first partition that cuts $B_{\leq r}(v)$, then we have that $\pi(v_{i})<\pi(v_{j})$ for all $j< i$.
> 	   
> 	   Let $j=\max\{ j<i: \pi(v_{j})<\pi(v_{i}) \}$.
> 		1. If $B_{\leq r}(v)\cap B_{\leq \delta}(v_{j})=\varnothing$, then $r+\delta<d(v,v_{j})\leq d(v,v_{i})$. This shows that $B_{\leq r}(v)\cap B_{\leq \delta}(v_{i})=\varnothing$ which is a contradiction that $C_{i}$ cuts $B_{\leq r}(v)$.
> 		2. If $B_{\leq r}(v)\subseteq B_{\leq \delta}(v_{j})$. Then, $C_{i}$ doesn't cut $B_{\leq r}(v)$ at all, which is a contradiction.
> 		3. If $B_{\leq r}(v)\cap B_{\leq \delta}(v_{j})\neq \varnothing$ and $B_{\leq r}(v)\nsubseteq B_{\leq \delta}(v_{j})$, then $C_{j}$ cuts $B_{\leq r}(v)$ before $C_{i}$. 
> 	
> 	Then, for all $i\in[n]$: Let $C$ be the first partition that cuts $B_{\leq r}(v)$. We have that:$$\begin{align}\mathbb{P}(C_{i}=C)&\leq\mathbb{P}(\pi(v_i)=\min_{j\in[i]}\pi(v_{j}))\cdot \mathbb{P}(d_{G}(v,v_{i})-r\leq\delta\leq d_{G}(v,v_{i})+r)\\&\leq \frac{1}{i}\cdot \frac{2r}{D/8}=\frac{16}{i}\cdot \frac{r}{D}\end{align}$$Therefore, $$\mathbb{P}(B_{\leq r}(v)\text{ is cut})\leq \frac{16r}{D}\sum_{i=1}^{n} \frac{1}{i}=16 H_{n}\cdot \frac{r}{D} $$
> 3. By setting $r=d(u,v)$, we have the statement.

^a6ffa8

---
> [!lemma] Theorem 2 (Tree Embedding)
> Let $G=(V,E)$ be an undirected graph.
> ```pseudo
> \begin{algorithm} \caption{TreeEmbedding$(G,D)$}
> \begin{algorithmic}
> \If{$\left| V(G) \right|=1$}
> \State Attach $v\in V(G)$ as a leaf with length $2D$
> \EndIf
> \State $C_{1},\dots,C_{k}\gets$ \Call{LDD}{$G,D$}
> \For{$i\in[k]$}
> \State Create an auxiliary node and attach \Call{Tree}{$G[C_{i}],D / 2$} with length $2D$.
\EndFor
> \end{algorithmic}
> \end{algorithm}
> ```
> Then, $\text{TreeEmbedding}(G,\text{diam}(G))$ is a tree embedding.

^639521

> [!proof]-
> Let $T:=\text{Tree}(G,D)$ where $D:=\text{diam}(G)$.
> 1. **Claim 1: For any $u,v\in V$ and $i\in \mathbb{N}$, if $u,v$ are separated at level $i$ in $T$, then $d_{T}(u,v)\in \left[\frac{2D}{2^i},\frac{4D}{2^i} \right]$**.
> 	
> 	If $T$ splits $u,v$ at level $i$, then we have that: $$\frac{2D}{2^i}\leq d_{T}(u,v)\leq 2\cdot \sum_{j=i}^{\infty} \frac{D}{2^j}= \frac{4D}{2^i} $$
> 
> Now, if we take $u,v\in V$, let $i\in \mathbb{N}$ s.t. $\frac{D}{2^i}\leq d_{G}(u,v)\leq \frac{D}{2^{i-1}}$. Then, from Theorem 1.1, $u,v$ will be separated before the $i$-th level. Therefore, $$d_{T}(u,v)\geq \frac{2D}{2^i}=\frac{D}{2^{i-1}}\geq d_{G}(u,v)$$Similarly, for any $u,v\in V$, let $E_{i}$ be the event that $u,v$ get separated at level $i$. Then,$$\begin{align}\mathbb{E}[d_{T}(u,v)]=\sum_{i=0}^{\log D-1}\mathbb{P}(E_{i})\mathbb{E}[d_{T}(u,v)|E_{i}]\leq\sum_{i=0}^{\log D-1}\left( \alpha \frac{d_{G}(u,v)}{D / 2^i} \right) \frac{4D}{2^i}=4\alpha \log(D)d_{G}(u,v)\end{align}$$

---
> [!lemma] Theorem 3 (Contraction)
> Consider the following algorithm:
> ```pseudo
> \begin{algorithm}\caption{Contract($T$)}
> \begin{algorithmic} 
> \While{$T$ has an edge $e=\{ u,w \}\in E$ where $u\in V$ and $v$ is an auxiliary node}
> \State Contract $e$ by merging subtree rooted at $u$ into $v$.\EndWhile
> \State $w\gets 4w$
> \Return $T$
> \end{algorithmic}
> \end{algorithm}
> ```
> Then, $\text{Contract}(T)$ returns a tree $T'$ s.t. 
> $$d_{T}(u,v)\leq d_{T'}(u,v)\leq 4d_{T}(u,v)$$

> [!proof]-
> Let $u,v\in V(T)$ and let auxiliary node $w$ at level $i$ is their closest common ancestor. Then, $$d_{T}(u,v)=d_{T}(u,w)+d_{T}(w,v)\leq2\left(  \sum_{j=i}^{\infty}\frac{D}{2^j}\right) =\frac{4D}{2^i}$$ Through contraction, we have that from the original tree, at least $\frac{D}{2^i}$ distance is given for $u,v$. By multiplying the weights by 4, we have that $d_{T}(u,v)\leq \frac{4D}{2^i}\leq d_{T'}(u,v)\leq 4d_{T}(u,v)$ where the upper bound follows from the fact that contraction only decreases the distance.
---
