### 1. Well-Spaced Subsets
1. (5min) Assume there is a well-spaced subset $S\subseteq V$ s.t. $\left| S \right|=k+1$ wlog. Note that for any $v\in S$, $N(v)\subseteq V \backslash S$ and $N(v)\cap N(w)=\varnothing$ for all $v,w\in S$. However, there are $3k-1$ vertices and $3k+3$ neighbors. Hence, there exists at least one vertex that is common by pigeonhole, contradiction.
2. Greedy algorithm. Add a vertex $v$ s.t. $N(v)\cap N(S)=\varnothing$ to $S$ until impossible. Let $v_{1},\dots,v_{p}$ be the vertices added in order. Then, $S$ is a well-spaced subset. 
   
   Now, for every $v\in V$, there exists $w\in S$ s.t. $d_{G}(v,w)\leq 2$. Let $f(v)$ be the one closest to $v$. However, for any $w\in S$, it can have at most $1+3+6=10$ vertices in its radius 2. Therefore, $$10p\geq 4k$$ and $p\geq \frac{2}{5}k$


o 