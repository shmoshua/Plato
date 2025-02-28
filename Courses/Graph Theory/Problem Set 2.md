#Series #GraphTheory 

#### Problem 1
Let $n$ be a number of vertices. Then, a tree has $n-1$ edges. If this is even, then $n$ is odd. Assume all vertices have an odd degree. Then, the sum of degree over all vertices is certainly odd, which cannot happen. 

---
#### Problem 2
Let $G$ be a connected graph on $n$ vertices. Then $G$ contains a spanning tree $T$ and as $n\geq 2$, $T$ has at least two leaves $u,v$ and by the spanning tree, we get that $G \backslash u$ and $G \backslash v$ are connected.

---
#### Problem 3
We show this using induction over $k$. 
1. Let $k=1$. Then, $T$ is a path. 
2. Let $k\geq 2$. Let $u\in T$ be a leaf. Let $P:=uv_{1}\dots v_{\ell}w$ be the maximal path s.t. $d(v_{1}),\dots,d(v_{\ell})\leq 2$. Notice that as it is a path, $d(v_{i})=2$ for all $i\in[\ell]$.
   
   Consider $T':= T \backslash P$ (viewing $P$ as a set of edges). Then, if $d(w)$ is odd, then $w$ has an even degree in $T'$ and $T'$ has now $2k-2$ odd vertices. Further, $T'$ is connected and acyclic, hence a tree. 
   
   If $d(w)$ is even, then 
   
	1. if $\ell=2k-2$, then $T=P$ and we are done by splitting the path into $k$ different paths. 
	2. if $\ell< 2k-2$, then $d(w)\geq 3$ and let $T':=T \backslash P$ (viewing $P$ as a set of edges). Notice that 
   
   Then, take the longest path $P$ in $T$. We see that the endpoints of $P$ have to be leaves, otherwise we can extend the path. Let $u,v$ be the endpoints of $P$. Consider $T':=T \backslash P$ (viewing $P$ as a set of edges). 
   
   We have that for any $x\in V(T) \backslash \{ u,v \}$, $$d_{T'}(x)=\begin{cases}d_{T}(x)-2&x\in P\\d_{T}(x)&x\notin P\end{cases}$$From this it follows that every connected component $C$ that is not a single point is a tree composed of exactly $2\ell\leq 2k-2$ odd-degree vertices. Therefore, by induction $C$ decomposes into $\ell$ different 

---
#### Problem 4
Let $G$ be a connected graph. If $G$ is not a tree, then $G$ contains a cycle $C$. This cycle can be decomposed into three paths $P_{1},P_{2},P_{3}$ of length $\geq 1$. Notice that they are pairwise intersecting, but they do not admit a common vertex. 

Conversely, let $G$ be a tree. Further, let $P_{1},\dots,P_{k}$ be a pairwise-intersecting family of paths. If $k\leq 2$, then by definition there exists a common vertex. If $k\geq 3$, consider $P_{1},P_{2}$. We claim that $P_{1}\cap P_{2}$ is a path (possibly of length 0 if there is no common edge). Otherwise, we can easily create a cycle as we get two internally disjoint $uv$-paths between some $u,v\in P_{1}\cap P_{2}$. 

Therefore, let $Q:=P_{1}\cap P_{2}$. Now, assume we don't have a common vertex for $P_{1},\dots,P_{k}$. If every path $P_{3},\dots,P_{k}$ passes through $Q$, then we have two different paths $P_{i},P_{j}$ s.t. $P_{i}\cap P_{j}\cap Q=\varnothing$. But as $P_{i}\cap P_{j}\neq \varnothing$, $P_{i}\cup P_{j}\cup Q$ contains a cycle, which is a contradiction. Therefore, there exists a path $P_{i}$ that doesn't go through $Q$. However, then $P_{i}$ intersects with $P_{1}$ and $P_{2}$ at two different points $u,v$ and as $P_{1}\cup P_{2}$ is connected and contains a $uv$-path that cross $Q$, we have that $P_{i}\cup P_{1}\cup P_{2}$ contains a cycle, which is also a contradiction.

---
#### Problem 5 
1. Let $f(T)$ be the Prüfer code of a labelled tree $T$. We have shown that $f$ forms a bijection between labelled trees on $[n]$ and $[n]^{n-2}$. We will now show that $f$ restricts to a bijection: $$\{ \text{stars on }[n] \}\to \{ i\dots i\in [n]^{n-2} \}_{i\in [n]},\quad T\mapsto f(T)$$For $i\dots i$ we have that every other node $j\neq i$ is a leaf. Therefore, $i\dots i$ corresponds to a star with $i$ as the center node. As both sets have size $n$, we have our statement.
2. Firstly, if there are exactly two different values in the Prüfer code, we have that there are $n-2$ leaves. Hence, it corresponds to a tree $T$ that has an edge $uv$ where $u,v\in f(T)$ and every other node is attached to either $u$ or $v$. 
---
#### Problem 6
We will show this by induction. 
1. Let $r=1$. Then, $T=T_{1}$ is a tree on $[n]$ and there exists exactly one spanning tree containing $T$, as all trees have exactly $n-1$ edges. The statement holds as $n^{-1}\left| T_{1} \right|=1$.
2. Let $r\geq 2$. 

