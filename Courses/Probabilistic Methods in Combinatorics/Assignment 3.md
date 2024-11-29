#Series #ProbabilisticMethods 

##### Problem 1
Let $G$ be the graph on $n$ vertices and $m$ edges with no copy of $H$ as subgraph. Let $\sigma_{1},\dots,\sigma_{k}:[n]\to[n]$ be uniformly independent permutations. Then, we define: $G_{i}:=([n],E_{i})$ as a subgraph of $K_{n}$ where $\{ \sigma_{i}(x),\sigma_{i}(y) \}\in E_{i}$ if and only if $\{ x,y \}\in E$. Further, we define the coloring $c: {[n] \choose 2}\to[k]$ where $c(e)=\min\{ i\in [k]: e\in G_{i} \}$.

As none of the $G_{i}$ contain $H$, it suffices to show that for any $e\in {[n] \choose 2}$ we have $e\in G_{i}$ for some $i$. Let $e=\{ x,y \}\in {[n] \choose 2}$ and denote $X_{e}$ as the indicator variable that $e$ is not colored. Then, $$\mathbb{E}[X_{e}]=\mathbb{P}(\forall i\in[k]: e\notin E_{i})=$$

Then, for $X:=\sum_{e\in {[n] \choose 2}}^{}X_{e}$: $$\mathbb{E}[X]=\sum_{e\in {[n ch]}}^{}$$


