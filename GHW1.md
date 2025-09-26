### 1. Well-Spaced Subsets
1. (5min) Assume there is a well-spaced subset $S\subseteq V$ s.t. $\left| S \right|=k+1$ wlog. Note that for any $v\in S$, $N(v)\subseteq V \backslash S$ and $N(v)\cap N(w)=\varnothing$ for all $v,w\in S$. However, there are $3k-1$ vertices and $3k+3$ neighbors. Hence, there exists at least one vertex that is common by pigeonhole, contradiction.
2. Greedy algorithm. Add a vertex $v$ s.t. $N(v)\cap N(S)=\varnothing$ to $S$ until impossible. Let $v_{1},\dots,v_{p}$ be the vertices added in order. Then, we want to show that $k\leq 2p$. 
   
 
3. 
4. Let $v_{1},\dots,v_{4k}$ be a uniformly random ordering. We add $v_{i}$ to $S$ if $N(v_{i})\cap S=\varnothing$ and $N(v_{i})\cap N(v_{j})=\varnothing$ for all $v_{j}\in S\cap \{ v_{1},\dots,v_{i-1} \}$. 
   
   Then, $S$ is a well-spaced subset. Now, 
   
   
   
   Let us randomly uniformly sample a node with $p$. Call that $S$. Then, $$\mathbb{E}[\left| S \right| ]=4pk,\quad \mathbb{E}[e(S)]=p^{2}\left| E \right| =6p^{2}k,\quad \mathbb{E}[\#\text{common neighbors}]=4k\cdot (p^3+p)$$