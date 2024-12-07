#Series #ProbabilisticMethods 

##### Problem 1
We will use the Lovász local lemma. Let us choose an assignment where we assign each variable to true uniformly randomly and independently. Further, let $B_{i}$ for $i\in[m]$ be the event that the $i$-th clause is not valid. Then, 
1. $\mathbb{P}(B_{i})\leq 2^{-k}<1$
2. every $B_{i}$ is mutually independent from all but at most $2^{k-2}-1$ other events. 
3. $e\cdot 2^{-k}\left( 2^{k-2} \right)<1$.

Therefore, $\mathbb{P}\left( \bigcap_{i=1}^{m}\overline{B_{i}} \right)>0$ and there is an assignment that makes the CNF satisfiable.

---
##### Problem 2
Let us color the vertices uniformly randomly and independently. For $e\in E$, let $B_{e}$ denote the event that $\left| r(e)-b(e) \right|>\sqrt{ 6d\log d }$. Then, 
1. For an edge $e\in E$, let $X_{1},\dots,X_{d}$ be the random variables valued in $\{ +1,-1 \}$ where $X_{i}=+1$ if and only if $i$-th vertex in $e$ is red. Then, by defining $X:=\sum_{i=1}^{d}X_{i}$, $$\mathbb{P}(B_{e})=\mathbb{P}(\left| X \right|> \sqrt{ 6d \log d } )\leq 2\exp \left( -3\log d \right)=2d^{-3}<1 $$
2. As each vertex is in exactly $d$ edges, each event $B_{e}$ is mutually independent with all other events besides $d^2-1$ events. 