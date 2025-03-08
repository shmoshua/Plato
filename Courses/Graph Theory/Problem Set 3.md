#Series #GraphTheory 

#### Problem 1
Assume $X$ is a minimal separating set. Fix $x\in X$ and define $Y:=X \backslash x$. Then, $X \backslash x$ is not separating and there is a $uv$-path  that does not contain a vertex in $Y$. However, this path has to cross a point in $X$. Hence, this path has to contain $x$ and no other vertex in $X$. Hence, we have that $x$ has a neighbor in both components of $u$ and $v$ in $G \backslash X$, given by the path.

Conversely, assume $X$ is not minimal, i.e. there exists $x\in X$ s.t. $Y:= X \backslash x$ is also separating. Assume however that $x$ has a neighbor in both the components of $u$ and $v$ in $G \backslash X$ respectively. call the neighbors $w_{u}$ and $w_{v}$. Then, we have a $uw_{u}$-path $P_{u}$ and $vw_{v}$-path $P_{v}$ that do not use any vertices in $X$. Hence, $P_{u}$, $P_{v}$ with $x$ forms a $uv$-path. This is a contradiction to $Y$ being separating. This proves the claim.

---
#### Problem 2

Let $G$ be a graph with $\left| V(G) \right|=: n\geq k+1$ and $\delta(G)\geq (n+k-2) / 2$. Assume that $G$ is not $k$-connected. Then, there exists $S\in {V(G) \choose k-1}$ s.t. $G \backslash S$ is not connected. Then, as $G \backslash S$ has $n-k+1$ vertices, the smallest component $C$ in $G \backslash S$ has at most $(n-k+1) / 2$ vertices. Now, for any $v\in C$, we have that: $$d(v)\leq \frac{n-k+1}{2}-1+k-1=\frac{n+k-3}{2}<\delta(G)$$which is a contradiction.

---
#### Problem 3
Assume that for any three vertices $x,y,z$ there is a $xz$-path containing $y$. If $G$ is not 2-connected, there exists $z\in V$ s.t. $G \backslash z$ is not connected. Let $x,y$ be two vertices that are not connected in $G \backslash z$. However, denote the $xz$-path containing $y$ as $P$. This clearly contains a subpath $Q$ from $x$ to $y$ that does not contain $z$. This is a contradiction to $x,y$ being disconnected in $G \backslash z$.

Conversely, let $G$ be 2-connected and $x,y\in V$ disjoint. Fix $z\in V \backslash \{ x,y \}$. Then, by definition, there exists a $xy$-path $P:=v_{1}\dots.v_{k}$ with $v_{1}=x$ and $v_{k}=y$ that doesn't contain $z$. Now, by Menger, there also exists two internally disjoint $yz$-paths $Q_{1}$ and $Q_{2}$. If either of the paths cross $P$ only at $y$, we have a $xz$-path containing $y$. Otherwise, both paths cross $P$ at some internal nodes. Wlog assume $P_{1}$ crosses $P$ "first", i.e. for $i_{1}:=\min \{j\in [k]:v_{j}\in P_{1} \}$ and similarly $i_{2}$, that $i_{1}<i_{2}$. (Notice that $i_{1}=i_{2}$ cannot happen as $P_{1},P_{2}$ are internally disjoint and $z\notin P$). Therefore, by taking $v_{1}\dots v_{i_{1}}$, $v_{i_{1}}$ to $y$ along $P_{1}$ and then to $z$ along $P_{2}$, we have a $xz$-path that contains $y$. 

---
#### Problem 4
Let $G$ be $k$-connected with $\left| V(G) \right|\geq 2k$. Let $C$ be a cycle of maximum length. Assume that $\left| C \right|\leq2k -1$. Then, there exists $v\in V$ that is not on the cycle, as $\left| V \right|\geq 2k$. 

Now, let $S:= \left| V(C) \right|$. Then, by Corollary 3.15, we have $k$ paths forming a $v$-$S$ fan in $G$, as $G$ is $k$-connected. However, as $\left| S\right|\leq 2k-1$, we have two vertices $u_{1},u_{2}$ that are adjacent in $C$ s.t. we have a $vu_{1}$-path and $vu_{2}$-path that only cross at $v$ (from the $v$-$S$ fan)

Hence, we can extend the cycle using the two paths instead of $u_{1}u_{2}$. This is a contradiction.

---
#### Problem 5
Let $G=(S\sqcup T, E)$ be a bipartite graph. Assume $G$ has no matching of size $k$. Then, the maximum number of vertex disjoint $S$-$T$ paths is $\leq k-1$. Hence, there exists a $S$-$T$ separating set $X$ of size $\leq k-1$. $X$ has to then intersect every edge, as every edge is a $S$-$T$-path. This proves the statement.

---
