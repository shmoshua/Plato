#Series #ProbabilisticMethods 

##### Problem 1
Let $G$ be the graph on $n$ vertices and $m$ edges with no copy of $H$ as subgraph. Let $\sigma_{1},\dots,\sigma_{k}:[n]\to[n]$ be uniformly independent permutations. Then, we define: $G_{i}:=([n],E_{i})$ as a subgraph of $K_{n}$ where $\{ \sigma_{i}(x),\sigma_{i}(y) \}\in E_{i}$ if and only if $\{ x,y \}\in E$. Further, we define the coloring $c: {[n] \choose 2}\to[k]$ where $c(e)=\min\{ i\in [k]: e\in G_{i} \}$.

As none of the $G_{i}$ contain $H$, it suffices to show that for any $e\in {[n] \choose 2}$ we have $e\in G_{i}$ for some $i$. Let $e=\{ x,y \}\in {[n] \choose 2}$ and denote $X_{e}$ as the indicator variable that $e$ is not colored. Then, $$\mathbb{E}[X_{e}]=\mathbb{P}(\forall i\in[k]: e\notin E_{i})=\left( 1-\frac{2m}{n(n-1)} \right)^k$$

Then, for $X:=\sum_{e\in {[n] \choose 2}}^{}X_{e}$: $$\begin{align}\mathbb{E}[X]&={n \choose 2}\left( 1-\frac{2m}{n(n-1)} \right)^k\leq{n \choose 2}e^{-\frac{2mk}{n^2}}<{n \choose 2}e^{- 2\log n}\leq \frac{1}{2}\end{align}$$and as $X$ is an integer, there exists a valid coloring. 

---
##### Problem 2
Consider $G \sim G(n,p)$ a random graph with $p=n^{-6/7}$. On $[n]$, there are ${n \choose 8} 7!$ different $C_{8}$ that can happen. Let $C$ be a cycle of length $8$ in $K_{n}$. Consider $X_{C}$ as the indicator variable that $C$ is in $G$. Let $X=\sum_{C}X_{C}$. Then, $$\mathbb{E}[X]={n \choose 8}7! p^8\leq \frac{n^{8/7}}{8}$$

Let $Y$ be the number of edges in $G$. Then, $\mathbb{E}[Y]= {n \choose 2} p$ and consider a graph $G'$ where we delete one edge from each cycle $C_{8}$. Then, the number of edges in $G'$ is at least $Y-X$. 

$$\mathbb{E}[Y-X]\geq \frac{n^{8/7}}{4} - \frac{n^{8/7}}{8}=\frac{n^{8/7}}{8}$$Therefore, there exists an instance where $Y-X\geq \frac{n^{8/7}}{8}$. 


