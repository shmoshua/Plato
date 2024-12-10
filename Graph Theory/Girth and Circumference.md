#Definition #GraphTheory 

> [!definition]
> For a [[graph]] $G$,
> 1.  the ***girth*** of $G$, denoted by $g(G)$, is defined as the shortest length of a cycle in $G$.
> 2. the ***circumference*** of $G$ is defined as the maximum length of a cycle. 

^803604

- **Related definition**: If $G$ is acyclic, $g(G)=\infty$ and the circumference is 0. 

---
##### Properties
> [!lemma] Proposition 1
> Let $G$ be a finite graph with a cycle. Then, 
> 1. $g(G)\leq 2\cdot \text{diam}(G)+1$

> [!proof]-
> Let $C$ be the shortest cycle in $G$. If $g(G)\geq 2\cdot \text{diam}(G)+2$, then $C$ has two vertices $u,v$ whose distance is at least $\text{diam}(G)+1$. However, we have that there exists a $(u,v)$-path $P$ that is shorter. By replacing a path in the cycle with $P$, we get a shorter cycle, which is a contradiction.

^125447

---
> [!lemma] Theorem 1 (Erdös, 1959)
> For any $k,\ell$, there exists a graph $G$ s.t. $\chi(G)>k$ and $g(G)>\ell$.

^4ba9e0

> [!proof]-
> Let $G \sim G(n,p)$ be a [[Erdös-Rényi Graph|random graph]] on $n$ vertices with $p=n^{-1+1/(\ell+1)}$.
> 
> Let $X$ be the number of cycles of length $\leq \ell$.
> 1. **Claim 1: $X< \frac{n}{2}$ w.h.p.**
>     $$\mathbb{E}[X]=\sum_{i=3}^{\ell} \frac{n\dots(n-i+1)}{2i}p^i\leq\sum_{i=3}^{\ell} \frac{(np)^i}{2i}=\sum_{i=3}^{\ell}\frac{n^{i/(\ell+1)}}{2i}=\text{o}(n)$$Therefore, by [[Expected Value|Markov]], $\mathbb{P}\left( X\geq \frac{n}{2} \right)\leq \text{o}(1)$. 
>  2. **Claim 2: $\mathbb{P}\left( \alpha(G)< \frac{n}{2k} \right)\geq \frac{9}{10}$**
> 	Let $Y$ be the number of independent sets of size $\frac{n}{2k}$. Then, $$\mathbb{E}[Y]={n \choose \frac{n}{2k}}(1-p)^{n/2k \choose_{2}}\leq 2^ne^{-p n^{2}/10k^2}=2^ne^{-n^{1+1/(\ell+1)}/10k^2}< \frac{1}{10}$$ Hence, $\mathbb{P}\left( \alpha(G)\geq \frac{n}{2k} \right)\leq \frac{1}{10}$. 
> 	
> Let $n$ be large enough s.t. $\mathbb{P}\left( X< \frac{n}{2} \right)\geq \frac{4}{5}$. Then $\mathbb{P}\left( X< \frac{n}{2},\alpha(G)< \frac{n}{2k} \right)\geq \frac{4}{5}+\frac{9}{10}-1=\frac{7}{10}$. Hence, there exists a graph with at most $\frac{n}{2}$ short cycles and $\alpha(G)< \frac{n}{2k}$. 
> 
> Now, we can obtain another graph $G'$ from $G$ where we delete one vertex from every cycle. Then, 
> 1. $\left| V(G') \right|\geq \left| V(G) \right|-\frac{n}{2}\geq \frac{n}{2}$ and
> 2. $\alpha(G')\leq\alpha(G)< \frac{n}{2k}$
>    
>  Hence, $g(G')> \ell$ and $\chi(G')\geq \left| V(G') \right|/\alpha(G')>k$.
>

^819748

---
> [!lemma] Theorem 2 (Bondy-Simonovits)
> Let $G=(V,E)$ be a graph with $n$ vertices. For any $k\geq 2$,
> 1. if $g(G)> 2k$, then $\left| E \right|\leq O(n^{1+1/k})$

> [!proof]+
> Let $c$ be a constant and assume that $\left| E \right|>cn^{1+1/k}$. Then, $d(G)=2\frac{\left| E \right|}{\left| V \right|}>2cn^{1/k}$ and there exists a subgraph $H\subseteq G$ s.t. $\delta(H)\geq cn^{1/k}$. 
> 
> Fix an arbitrary vertex $x\in H$. Let $V_{i}:=\{ v\in V':d_{H}(u,v)=i \}$. 




> Assume that $\left| E \right|>2n^{1+1/k}$ and define $H:=(V',E')$ be the graph defined by removing vertices with degree $d(v)\leq n^{1/k}$ from $G$. Then,
> 1. for all $v\in V'$, $d_{H}(v)> n^{1/k}$.
> 2. As each vertex removed removes at most $n^{1 / k}$ edges, we have that: $$\left| E' \right| \geq \left| E \right| -n^{1+1/k}>n^{1+1/k}$$
> 3. As $H\subseteq G$, we have that $g(H)\geq g(G)> 2k$.
> 
> Let $v\in V'$ fixed and consider $H^i(v)$ as the graph given by the union of all paths of length $i$ starting from $v$. Then, notice that $H^i(v)$ is a tree for all $i\in[k]$. Otherwise there exists $x\in B_{\leq i}(v)$ and two $v$-$x$-paths $p_{1},p_{2}$ s.t. $(p_{1},p_{2})$ contains a cycle of length $\leq 2k$, which is a contradiction.
> 
> Lastly, we claim that $\left| B_{\leq i+1}(v) \right|>n^{1/k}\left| B_{\leq i}(v) \right|$ for all $0\leq i<k$. Indeed, for every $u\in B_{\leq i}(v)$, $$d_{H^{i+1}(v)}(u)=d_{H}(u)>n^{1/k}$$Therefore, $$\left| B_{\leq i+1}(v) \right| =\left| E(H^{i+1}(v)) \right|+1\geq \frac{1}{2}\sum_{u\in B_{\leq i+1}(v)}^{}d_{H^{i+1}(v)}(u) +1> \frac{1}{2}n^{1/k}\left| B_{\leq i}(v) \right| $$
