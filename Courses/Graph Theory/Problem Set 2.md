#Series #GraphTheory 

#### Problem 1
Let $n$ be a number of vertices. Then, a tree has $n-1$ edges. If this is even, then $n$ is odd. Assume all vertices have an odd degree. Then, the sum of degree over all vertices is certainly odd, which cannot happen. 

---
#### Problem 2
Let $G$ be a connected graph on $n$ vertices. Then $G$ contains a spanning tree $T$ and as $n\geq 2$, $T$ has at least two leaves $u,v$ and by the spanning tree, we get that $G \backslash u$ and $G \backslash v$ are connected.

---
#### Problem 3
We show this using induction over $k$. 
1. Let $k=1$. Then, $T$ is an edge and this is indeed a path.
2. Let $k\geq 2$. Let $u\in T$ be a leaf. Let $uv_{1}\dots v_{\ell}w$ be the maximal path 
   
   Then, take the longest path $P$ in $T$. We see that the endpoints of $P$ have to be leaves, otherwise we can extend the path. Let $u,v$ be the endpoints of $P$. Consider $T':=T \backslash P$ (viewing $P$ as a set of edges). 
   
   We have that for any $x\in V(T) \backslash \{ u,v \}$, $$d_{T'}(x)=\begin{cases}d_{T}(x)-2&x\in P\\d_{T}(x)&x\notin P\end{cases}$$From this it follows that every connected component $C$ that is not a single point is a tree composed of exactly $2\ell\leq 2k-2$ odd-degree vertices. Therefore, by induction $C$ decomposes into $\ell$ different 
