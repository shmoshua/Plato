#Series #GraphTheory 

#### Problem 1
Let $a_{1},\dots,a_{k}$ and $b_{1},\dots,b_{k}$ be an arbitrary ordering on the odd vertices. Now, let $G'$ be the graph constructed by adding $a_{i}b_{i}$ to $G$ for all $i\in[k]$. Then, $G'$ is an even graph and therefore has an Eulerian tour $T$. Hence, $T \backslash \{ a_{i}b_{i} \}_{i\in[k]}$ decomposes into $k$ edge-disjoint trails, which make up the whole set of edges $E(G)$. 

---
#### Problem 2
1. This statement is true. As $G$ has an Eulerian tour, $G$ is even. Then, for $V(G)=A\sqcup B$, we have that: $\left| E(G) \right| =\sum_{v\in A}^{}d(v)$ is even as $d(v)$ is even for all $v\in V(G)$.
2. False. The following graph is clearly has a Eulerian tour with even number of vertices. However, there are 7 edges.
```tikz
\usepackage{tikz}
\usetikzlibrary{arrows}
\begin{document}

\begin{tikzpicture}[shorten >=1pt,->]
\tikzstyle{vertex}=[circle,fill=black,minimum size=6pt,inner sep=2pt]
\node[vertex] (G_1) at (0,0) {};
\node[vertex] (G_2) at (1.5,0)   {};
\node[vertex] (G_3) at (3,0)  {};
\node[vertex] (G_4) at (0,-1.5)  {};
\node[vertex] (G_5) at (1.5,-1.5)  {};
\node[vertex] (G_6) at (3,-1.5)  {};
\draw (G_1) -- (G_2) -- (G_5) -- (G_4) -- (G_1) -- cycle;
\draw (G_2) -- (G_3) -- (G_6) -- (G_2)  --cycle;
\end{tikzpicture}\end{document} 
```
1. False. Consider the same counterexample as above. Let $v$ be the vertex in both the $4$-cycle and $3$-cycle. Then, the two edges in $3$-cycle incident to $v$ cannot appear consecutively in any Eulerian tour. 

---
#### Problem 3

1. Let $P:=v_{0}v_{1}\dots.v_{k}$ be any longest path in $G$. If $k=n-1$, then $G$ has a path of length $2\delta\leq n-1$ and we are done. Assume $k\leq n-2$. As $G$ is connected, there exists $v\in V$ s.t. $v$ is not on $P$ but is adjacent to $v_{i}$. 
	1. If $i\in \{ 0,k \}$ then we can extend the path which is a contradiction. 
	2. 