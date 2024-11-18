#Definition #Algorithms 

> [!definition]
> Given an undirected [[graph]] $G=(V,E)$, a ***tree embedding*** is a [[probability space]] $(\mathcal{T},\Sigma,\mathbb{P})$ where $\mathcal{T}:=\{ T_{1},\dots,T_{p} \}$ where $T_{i}$ is a [[tree]] on $V$ s.t.
> 1. for all $u,v\in V$, $d_{G}(u,v)\leq d_{T_{i}}(u,v)$.
> 2. there exists a $c>0$ s.t. for all $u,v\in V$, $\mathbb{E}[d_{T}(u,v)]\leq c\cdot d_{G}(u,v)$
---
##### Properties
> [!lemma] Theorem 1 (Low Diameter Decomposition)
> Let $G=(V,E)$ be an undirected graph with $n:=\left| V \right|$ and $D:=\text{diam}(G)$.
> ```pseudo
> \begin{algorithm} \caption{LDD$(G,D)$}
> \begin{algorithmic}
> \State $\delta\gets [D / 8, D / 4]$, sample uniformly a radius.
> \State $\pi \gets S_{V}$, sample uniformly  a random permutation.
> \For{$v\in V$}
> \State $C_{i}\gets B_{\leq \delta}(\pi(v)) \backslash \bigcup_{j<i}^{}C_{j}$
\EndFor
> \end{algorithmic}
> \end{algorithm}
> ```
> 
> Then, the algorithm outputs a partition $V=\bigsqcup_{i\in[n]}^{} C_{i}$ s.t. 
> 1. for all $i\in[n]$, $\text{diam}(C_{i})\leq D$
> 2. there exists $\alpha\in \text{O}(\log n)$ s.t. for all $v\in V$ and $r\geq 0$, $\mathbb{P}(\forall i:B_{\leq r}(v)\nsubseteq C_{i})\leq \alpha r / D$.

> [!proof]-
> We have that:
> 1. Obvious.
> 2. Let $v\in V$ and $r\geq 0$. We will sort the nodes into $v=v_{0},v_{1},\dots,v_{n-1}$. Then, $$\begin{align}\mathbb{P}(v_{i}\text{ cuts }B_{\leq r}(v))&\leq\mathbb{P}(\pi(v_i)=\min_{j\in[i]}\pi(v_{j}))\cdot \mathbb{P}(\delta\in B_{\leq r}(d_{G}(v,v_{i})))\\&\leq \frac{1}{i}\cdot \frac{2r}{D/8}=\frac{16}{i}\cdot \frac{r}{D}\end{align}$$Therefore, $$\mathbb{P}(\forall i:B_{\leq r}(v)\nsubseteq C_{i})\leq \frac{16r}{D}\sum_{i=1}^{n} \frac{1}{i}=16 H_{n}\cdot \frac{r}{D} $$
---
> [!lemma] Theorem 2 (Tree Embedding)
> ```pseudo
> \begin{algorithm} \caption{Tree$(G,U\subseteq V,D)$}
> \begin{algorithmic}
> \If{$\left| U \right|=1$}
> \State 
> \EndIf
> \State $\delta\gets [D / 8, D / 4]$, sample uniformly a radius.
> \State $\pi \gets S_{V}$, sample uniformly  a random permutation.
> \For{$v\in V$}
> \State $C_{i}\gets B_{\leq \delta}(\pi(v)) \backslash \bigcup_{j<i}^{}C_{j}$
\EndFor
> \end{algorithmic}
> \end{algorithm}
> ```