#Series #GraphTheory 

#### Problem 1
Assume $X$ is a minimal separating set. Fix $x\in X$ and define $Y:=X \backslash x$. Then, $X \backslash x$ is not separating and there is a $uv$-path  that does not contain a vertex in $Y$. However, this path has to cross a point in $X$. Hence, this path has to contain $x$ and no other vertex in $X$. Hence, we have that $x$ has a neighbor in both components of $u$ and $v$ in $G \backslash X$, given by the path.

Conversely, assume $X$ is not minimal, i.e. there exists $x\in X$ s.t. $Y:= X \backslash x$ is also separating. Assume however that $x$ has a neighbor in both the components of $u$ and $v$ in $G \backslash X$ respectively. call the neighbors $w_{u}$ and $w_{v}$. Then, we have a $uw_{u}$-path $P_{u}$ and $vw_{v}$-path $P_{v}$ that do not use any vertices in $X$. Hence, $P_{u}$, $P_{v}$ with $x$ forms a $uv$-path. This is a contradiction to $Y$ being separating. This proves the claim.

---
#### Problem 2

Let $G$ be a graph with $\left| V(G) \right|=: n\geq k+1$ and $\delta(G)\geq (n+k-2) / 2$. Assume that $G$ is not $k$-connected. Then, there exists $S\in {V(G) \choose k-1}$ s.t. $G \backslash S$ is not connected. Then, as $G \backslash S$ has $n-k+1$ vertices, the smallest component $C$ in $G \backslash S$ has at most $(n-k+1) / 2$ vertices. Now, for any $v\in C$, we have that: $$d(v)\leq \frac{n-k+1}{2}-1+k-1=\frac{n+k-3}{2}<\delta(G)$$which is a contradiction.

---
