#Definition #GraphTheory 

> [!definition]
> For a [[graph]] $G$, the ***girth*** of $G$, denoted by $g(G)$, is defined as the shortest length of a cycle in $G$

^803604

---
##### Properties
> [!lemma] Theorem 1 (Erdös)
> For any $k,\ell$, there exists a graph $G$ s.t. $\chi(G)>k$ and $g(G)>\ell$.

^4ba9e0

> [!proof]-
> Let $G \sim G(n,p)$ be a random graph on $n$ vertices where between two vertices $x,y$ there exists an edge with a probability $p=n^{-1+1/(\ell+1)}$ independently.
> 
> Let $X$ be the number of cycles of length $\leq \ell$.
> 1. **Claim 1: $\mathbb{P}\left( X< \frac{n}{2} \right)\geq \frac{4}{5}$.**
>     $$\mathbb{E}[X]=\sum_{i=3}^{\ell} {n \choose i}p^i\leq\sum_{i=3}^{\ell} (np)^i=\sum_{i=3}^{\ell}n^{i/(\ell+1)}\leq 2n^{\ell/(\ell+1)}< \frac{n}{10}$$Therefore, by [[Expected Value|Markov]], $$\mathbb{P}\left( X< \frac{n}{2} \right)=1-\mathbb{P}\left( X\geq \frac{n}{2} \right)\geq 1-\frac{2\mathbb{E}[X]}{n}> \frac{4}{5}$$
>  2. **Claim 2: $\mathbb{P}\left( \alpha(G)< \frac{n}{2k} \right)\geq \frac{9}{10}$**
> 	Let $Y$ be the number of independent sets of size $\frac{n}{2k}$. Then, $$\mathbb{E}[Y]={n \choose \frac{n}{2k}}(1-p)^{n/2k \choose_{2}}\leq 2^ne^{-p n^{2}/10k^2}=2^ne^{-n^{1+1/(\ell+1)}/10k^2}< \frac{1}{10}$$ Hence, $\mathbb{P}\left( \alpha(G)\geq \frac{n}{2k} \right)\leq \frac{1}{10}$. 
>
> Therefore, $P\left( X< \frac{n}{2},\alpha(G)< \frac{n}{2k} \right)\geq \frac{4}{5}+\frac{9}{10}-1=\frac{7}{10}$. Hence, there exists a graph with at most $\frac{n}{2}$ short cycles and $\alpha(G)< \frac{n}{2k}$. 
> 
> Now, we can obtain another graph $G'$ from $G$ where we delete one vertex from every cycle. Then, 
> 1. $\left| V(G') \right|\geq \left| V(G) \right|-\frac{n}{2}\geq \frac{n}{2}$ and
> 2. $\alpha(G')\leq\alpha(G)< \frac{n}{2k}$
>    
>  Hence, $g(G')> \ell$ and $\chi(G')\geq \left| V(G') \right|/\alpha(G')>k$.
>

^819748
