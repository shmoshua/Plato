#Definition #GraphTheory 

> [!definition]
> Let $H$ be a [[graph]]. 
> 1. the ***Turan number*** $\text{ex}(n,H)$ of $H$ and $n$ is given by: $$\text{ex}(n,H):=\max_{\begin{array}\ \left| G \right| =n\\ H\not\leq G\end{array}}e(G)$$

- **Related definition**: The graph $K_{n_{1},..,n_{r}}$ with $\left| n_{i}-n_{j} \right|\leq 1$is called the ***Turan graph*** $T_{n,r}$.
- **Related definition**: The ***Turan density*** $\pi(H)$ is given by $\pi(H):=\lim_{ n \to \infty }\text{ex}(n,H) / {n \choose 2}$. 
---
##### Properties
> [!lemma] Theorem 1 (Turan 1941)
> We have that: $$\text{ex}(n,K_{r+1})=e(T_{n,r})$$where $T_{n,r}$ is the unique graph giving the maximum. 

> [!proof]-
> Let $G:=(V,E)$ be the maximizer of $\text{ex}(n,K_{r+1})$. Let $v_{m}\in V$ be the vertex of maximal degree. Let further $S:=N(v_{m})$ with $\left| S \right|=d(v_{m})=:d_{m}$. Set $T:= V \backslash S$. As $G$ contains no $K_{r+1}$ and $v_{m}$ is adjacent to every node in $S$, $S$ contains no $r$-clique. 
> 
> Let $H$ be another graph on $V$ where it is given from $G$ by deleting all edges in $E(T)$ and adding every possible edge between $S$ and $T$. Then, of course $H$ also doesn't contain any $K_{r+1}$. 
> 
> If $v\in S$, then we certainly have that $d_{H}(v)\geq d_{G}(v)$ and for $v\in T$, $$d_{H}(v)=\left| S \right| =\Delta(G)\geq d_{G}(v)$$Therefore, we infer that $e(H)\geq e(G)$ and by the maximality, there should be a maximizer of the form $H$. By induction, the graph induced by $S$ has as many edges as a suitable graph $K_{n_{1},\dots, n_{r-1}}$ on $S$. So $e(G)\leq e(H)\leq e(K_{n_{1},\dots,n_{r}})$ with $n_{r}:= \left| T \right|$. As $e(K_{n_{1},\dots,n_{r}})$ is maximal for $\left| n_{i}-n_{j} \right|\leq 1$, we have that $T_{n,r}$ has the maximum possible edges. 
> 
> The uniqueness is obvious.

> [!proof]- Proof (if r|n)
> Consider a weighting of the vertices $w:=(w_{1},\dots,w_{n})$ s.t. $w_{i}\geq 0$ for all $i$ and $\sum_{i=1}^{n}w_{i}=1$. We want to maximize: $$f(w):=\sum_{v_{i}\sim v_{j}}^{}w_{i}w_{j}$$Suppose $w$ is any weighting. Let $v_{i},v_{j}$ be non-adjacent vertices with non-zero weights. Let $s_{i},s_{j}$ be the sum of all weights adjacent to $v_{i}$ and $v_{j}$. Wlog assume $s_{i}\geq s_{j}$. Now, let's move the weight from $v_{j}$ to $v_{i}$. Then, for the new weighting $w'$, we have: $$f(w')=f(w)+w_{j}s_{i}-w_{j}s_{j}\geq f(w)$$We repeat this process until there are no pair of non-adjacent vertices of positive weights anymore. Thus we can conclude that there is an optimal weighting whose non-zero weights are concentrated on a clique, say on a $k$-clique. 
> 
> Now, for $w_{1}>w_{2}>0$, then we can choose $0<\varepsilon<w_{1}-w_{2}$ and change $w_{1}$ to $w_{1}-\varepsilon$ and $w_{2}$ to $w_{2}+\varepsilon$. Then, the new weighting $w'$ satisfies: $$f(w')=f(w)+\varepsilon(w_{1}-w_{2})-\varepsilon^{2}>f(w)$$and we infer that the maximal $f$ is attained if $w_{i}=1 / k$ supported on a $k$-clique. Since there are $k(k-1) / 2$ edges, we have that: $$f(w)=\frac{k(k-1)}{2}\cdot  \frac{1}{k^{2}}=\frac{1}{2}\left( 1-\frac{1}{k} \right)$$Since this expression is increasing in $k$, the best we can do is set $k:= r$ as $G$ has no $K_{r+1}$. Therefore, we get that: $$f(w)\leq \frac{1}{2}\left( 1-\frac{1}{r} \right) $$for any weighting $w$. In particular, this holds for the uniform weighting given by $w_{i}:= \frac{1}{n}$. Therefore, $$\left| E \right| =f(w^{*})n^{2}\leq \left( 1-\frac{1}{r} \right)\frac{n^{2}}{2}=e(T_{n,r})$$
- **Corollary**: We have that $\pi(K_{r})=1- \frac{1}{r-1}$. 
---
> [!lemma] Corollary 2
> Let $a_{1},..,a_{n}\in \mathbb{R}^d$ s.t. $\left\| a_{i} \right\|\geq 1$ for all $i\in[n]$. 
> 1. the maximum number of pairs satisfying $\left\| a_{i}+a_{j} \right\|\leq 1$ is at most $\left\lfloor n^{2} / 4\right\rfloor$

> [!proof]-
> We have that:
> 2. Let $G$ be a graph on $[n]$ where $i\sim j$ if and only if $\left\| a_{i}+a_{j} \right\|<1$. We show that $G$ is triangle-free. For any $i,j,k\in[n]$, $$\left\| a_{i}+a_{j} \right\| ^{2}+\left\| a_{j}+a_{k} \right\| ^{2}+\left\| a_{k}+a_{i} \right\| ^{2}=\left\| a_{i}+a_{j}+a_{k} \right\| ^{2}+\left\| a_{i} \right\| ^{2}+\left\| a_{j} \right\| ^{2}+\left\| a_{k} \right\| ^{2}\geq 3$$Hence at least one of them is at least 1. 
>    
>    Therefore, the maximum number is given by $$\text{ex}(n,K_{3})=e(T_{n,2})=\left\lfloor n^{2} / 4\right\rfloor $$

---
>[!lemma] Theorem 3 (Erdös-Stone)
> Let $H$ be a graph of chromatic number $\chi(H)=r+1$. Then, 
> 1. for any $\varepsilon>0$ and large enough $n$, $$\left( 1-\frac{1}{r} \right){n \choose 2}\leq \text{ex}(n,H)\leq \left( {1-\frac{1}{r}} \right){n \choose 2}+\varepsilon n^{2}$$
---
> [!lemma] Theorem 4
> Let $G$ be a graph on $n$ nodes. 
> 1. $\text{ex}(n,C_{4})\leq \left\lfloor \frac{n}{4}(1+\sqrt{ 4n-3 })\right\rfloor$

> [!proof]-
> We have that:
> 1. Let $G$ be a graph on $n$ without $C_{4}$. Let $S$ be a set of pairs $(u,\{ v,w \})$ where $v,w\in N(u)$ with $v\neq w$. We count $S$ in two different ways. Naively, we have that $\left| S \right|=\sum_{u\in V}^{}{d(u)\choose 2}$. On the other hand, every pair $\{ v,w \}$ has at most one common neighbor as $G$ is $C_{4}$-free. Hence, we have that $$\sum_{u\in V}^{}{d(u) \choose 2}\leq {n \choose 2}$$Or equivalently, $$\sum_{u\in V}^{}d(u)^{2}\leq n(n-1)+\sum_{u\in V}^{}d(u)$$By Cauchy-Schwarz, we have: $$\left( \sum_{u\in V}^{}d(u) \right) ^{2}\leq n\sum_{u\in V}^{}d(u)^{2}\leq n^{2}(n-1)+n\sum_{u\in V}^{}d(u)$$In other words, $$4\left| E \right| ^{2}\leq n^{2}(n-1)+2n \left| E \right| $$Equivalently, $$\left| E \right| ^{2}- \frac{n}{2}\left| E \right|-\frac{n^{2}(n-1)}{4}\leq 0 $$Solving this quadratic equation gives us the answer. 
>    
---
 > [!lemma] Theorem 5 (Kövari-Sos-Turan)
 > For any integers $r\leq s$, 
 > 1. $\text{ex}(n,K_{r,s})\leq cn^{2- 1/r}$

> [!proof]-
> We have that:
> 1. Let $m:= \left| E \right|$ and $V:=\{ x_{1},\dots,x_{n} \}$ and $d_{i}:= d(x_{i})$. Since $G$ is $K_{r,s}$-free, for any given $r$-tuple in $V$, there are at most $s-1$ vertices whose neighborhood contain that $r$-tuple. The neighborhood of $x_{i}$ contains ${d_{i} \choose r}$ $r$-tuples. So, $$\sum_{i=1}^{n}{d_{i} \choose r}\leq (s-1){n \choose r}$$Note that $x\mapsto {x \choose r}$ is convex for $x\geq r-1$. Hence, $$f(x):=\begin{cases}{x \choose r}&x\geq r-1 \\0&\text{otherwise} \end{cases}$$Then, by Jensen, $$\sum_{i=1}^{n}{d_{i} \choose r}=\sum_{i=1}^{n}f(d_{i})\geq nf\left( \frac{1}{n}\sum_{i=1}^{n}d_{i} \right)=nf\left( \frac{2m}{n} \right)$$If $\frac{2m}{n}<r-1$, there is nothing to prove. Suppose that $\frac{2m}{n}\geq r-1$. Then, $$(s-1){n \choose r}\geq nf\left( \frac{2m}{n} \right)=n{2m / n \choose r}$$Then, $$\frac{n}{r!}\left( \frac{2m}{n}-r+1 \right)^r<(s-1)\frac{n^r}{r!}$$and we get that $\left( \frac{2m}{n}-r+1 \right)^r<(s-1)n^{r-1}$. Therefore, $$2m<(s-1)^{1/r}n^{2-1/r}+n(r-1)<c\cdot n^{2-1/r}$$for some $c$. Finishing the proof. 
- **Remark**: $\text{ex}(n,K_{r,s})=O(n^{2-1/r})$ is tight for $r=2,3$ and if $s\geq 1000^r$. 
---
> [!lemma] Corollary 6 (Erdös)
> Let $x_{1},\dots,x_{n}\subseteq \mathbb{R}^{2}$ be $n$ distinct points. 
> 1. there can be at most $cn^{3/2}$ pairs of points of distance $1$. 

> [!proof]-
> We have that:
> 1. Define $G$ on $[n]$ where $i\sim j$ iff $d(x_{i},x_{j})=1$. We claim that $G$ cannot have $K_{2,3}$ as a subgraph as two different circles of radius $1$ can have at most $2$ intersection points. Therefore, by Kövari-Sos-Turan, $$\text{ex}(n,K_{2,3})\leq cn^{3/2}$$
---
