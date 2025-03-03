#Series #GraphTheory 

#### Problem 1
Let $n$ be a number of vertices. Then, a tree has $n-1$ edges. If this is even, then $n$ is odd. Assume all vertices have an odd degree. Then, the sum of degree over all vertices is certainly odd, which cannot happen. 

---
#### Problem 2
Let $G$ be a connected graph on $n$ vertices. Then $G$ contains a spanning tree $T$ and as $n\geq 2$, $T$ has at least two leaves $u,v$ and by the spanning tree, we get that $G \backslash u$ and $G \backslash v$ are connected.

---
#### Problem 3
We show this for all forests instead, i.e. if $F$ is a forest with exactly $2k$ odd degree vertices, then it decomposes into $k$ paths. Consider the following induction over $k$. 
1. Let $k=1$. Then, $F$ is a path. Hence, the statement holds.
2. Let $k\geq 2$. As we have more than $2k$ odd degree vertices, there exists a connected component $T$ in $F$ that is not a single point. Then, $T$ is a tree and as $\left| T \right|\geq 2$, there exists leaves $u,v$ with $u\neq v$ in $T$. Let $P$ be the unique $uv$-path. 
   
	Consider $F':=F \backslash P$ (treating $P$ as a set of edges). Then, for $u,v$, $d_{F'}(u)=d_{F'}(v)=0$. Further, for all internal vertices on $P$, we decrease the degree by 2, the parity stays the same. Hence, the number of odd degree vertices decreases exactly by 2 and $F'$ is a forest with exactly $2k-2$ odd degree vertices. By induction, it decomposes into $k-1$ paths. Therefore, with $P$, $F$ decomposes into $k$ paths. 

---
#### Problem 4
Let $G$ be a connected graph. If $G$ is not a tree, then $G$ contains a cycle $C$. This cycle can be decomposed into three paths $P_{1},P_{2},P_{3}$ of length $\geq 1$. Notice that they are pairwise intersecting, but they do not admit a common vertex. 

Conversely, let $G$ be a tree on $n$ nodes. Let $P_{1},\dots,P_{k}$ be the pairwise-intersecting family of paths. Firstly, assume that there exists a path of length 0 in $P_{1},\dots,P_{k}$, i.e. a single vertex. Then, by pairwise intersecting property, this vertex must be common.

Hence, we can assume that the paths are all at least of length 1. We will prove the statement using induction on $n$. 
1. Let $n=2$. Then, there exists only one path $P$ of length $\geq 1$, which is a single edge. Hence, the statement holds.
2. Let $n\geq 3$. Further, As $G$ is a tree, there exists a leaf $v\in V(G)$. Consider $G':= G \backslash v$. Then, $G'$ is a tree on $n-1$ nodes. Further, as $v$ is a leaf in $G$, it cannot appear as an inner node of any path $P_{1},\dots,P_{k}$. Therefore, by denoting $P'_{i}:=P_{i} \backslash v$, we have that $P'_{i}$ is a path for all $i\in[k]$. Further, if $P_{i},P_{j}$ have $v$ as common node, then as $\deg(v)=1$, $P_{i}$ and $P_{j}$ also have $u$ as a common vertex where $u$ is the unique neighbor of $v$. Hence, $P'_{1},\dots,P'_{k}$ is also a pairwise-intersecting family of paths. By induction, this shows that there exists a common vertex for $P'_{1},\dots,P'_{k}$ in $G'$ and so does it in $G$.  

---
#### Problem 5 
1. Let $f(T)$ be the Prüfer code of a labelled tree $T$. We have shown that $f$ forms a bijection between labelled trees on $[n]$ and $[n]^{n-2}$. We will now show that $f$ restricts to a bijection: $$\{ \text{stars on }[n] \}\to \{ i\dots i\in [n]^{n-2} \}_{i\in [n]},\quad T\mapsto f(T)$$For $i\dots i$ we have that every other node $j\neq i$ is a leaf. Therefore, $i\dots i$ corresponds to a star with $i$ as the center node. As both sets have size $n$, we have our statement.
2. Firstly, if there are exactly two different values in the Prüfer code, we have that there are $n-2$ leaves. Hence, it corresponds to a tree $T$ that has an edge $uv$ where $u,v\in f(T)$ and every other node is attached to either $u$ or $v$. 
---
#### Problem 6
We will show this by induction. 
1. Let $r=1$. Then, $T=T_{1}$ is a tree on $[n]$ and there exists exactly one spanning tree containing $T$, as all trees have exactly $n-1$ edges. The statement holds as $n^{-1}\left| T_{1} \right|=1$.
2. Let $r\geq 2$. Let $i,j\in [r]$ s.t. $i\neq j$. Then, there are $e(T_{i},T_{j})=\left| T_{i} \right|\left| T_{j} \right|$. Let $e\in E(T_{i},T_{j})$. Then, $T_{ij}:=T_{i}\cup \{ e \}\cup T_{j}$ forms a tree and $T_{1},\dots,T_{r}$, where we replace $T_{i},T_{j}$ with $T_{ij}$, forms a forest $T'$ on $[n]$ with $r-1$ components. Hence, by induction, we get $$n^{r-3}(\left| T_{i} \right| +\left| T_{j} \right| )\prod_{k\neq i,j}^{}\left| T_{k} \right| $$different spanning trees containing $T'$. As there are $\left| T_{i} \right|\left| T_{j} \right|$ different edges we can choose between $T_{i},T_{j}$, there are $n^{r-3}(\left| T_{i} \right|+\left| T_{j} \right|)\prod_{k}^{}\left| T_{k} \right|$ spanning trees containing $T$ s.t. it contains an edge between $T_{i}$ and $T_{j}$. 
   
   Therefore, we have that: $$\sum_{(i,j)\in{ [r] \choose 2}}^{}n^{r-3}(\left| T_{i} \right|+\left| T_{j} \right|)\prod_{k}^{}\left| T_{k} \right|=(r-1)n^{r-2}\prod_{k}^{}\left| T_{k} \right| $$We conclude by noting that the same spanning tree is counted exactly $r-1$ times as there are $r-1$ edges between some two trees $T_{i},T_{j}$. 

To deduce Cayley's formula, let the forest be the empty graph on $[n]$. Then, we get that the number of spanning trees on $[n]$ is given by $n^{n-2}$.

---
#### Problem 7
1. The Prüfer code is given by: $16144611$. For left $4$ and right $5$, we have: $$f\downarrow\begin{bmatrix}1&4&5&6\\4&6&1&5\end{bmatrix}$$as the bijection nodes. Therefore, we get: $$f\downarrow\begin{bmatrix}1&2&3&4&5&6&7&8&9&10\\4&1&6&6&1&5&4&4&1&1\end{bmatrix}$$
2. We have:
```tikz
\usepackage{tikz-cd}
\usetikzlibrary{arrows}

\begin{document}
\begin{tikzcd} 2 & 5 & 7 & 1 & 4 \\ & 8 & 6 & 3 \arrow[no head, from=1-1, to=1-2] \arrow[no head, from=1-2, to=1-3] \arrow[no head, from=1-2, to=2-2] \arrow[no head, from=1-3, to=1-4] \arrow[no head, from=1-3, to=2-3] \arrow[no head, from=1-4, to=1-5] \arrow[no head, from=1-4, to=2-4] \end{tikzcd}
\end{document} 
```

---
   
