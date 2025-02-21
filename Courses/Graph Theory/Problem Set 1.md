#GraphTheory #Series 

#### Problem 1
1. There is no such graph as there is an odd number of vertices of odd degree.
2. As there are 7 vertices in total and three vertices with degree 6, the minimum degree is 3. Hence, such a graph doesn't exist.
3. Assume $G$ is such a graph with $v_{1},\dots,v_{8}$ as the vertices in order of the degree sequence. Let $S:=\{ v_{1},\dots,v_{5} \}$ and we notice that as each vertex $v\in S$ can have at most $4$ neighbors in $S$, $$e(S,V \backslash S)\geq \sum_{v\in S}^{}d(v)-4=9$$This is a contradiction as $e(S , V\backslash S)\leq \sum_{v\in V \backslash S}^{}d(v)=7$.
6. We have: 
```tikz
\usepackage{tikz}
\usetikzlibrary{arrows}
\begin{document}

\begin{tikzpicture}[shorten >=1pt,->]
  \tikzstyle{vertex}=[circle,fill=black,minimum size=6pt,inner sep=2pt]
  \node[vertex] (G_1) at (-0.5,-0) {};
  \node[vertex] (G_2) at (0.5,-0)   {};
  \node[vertex] (G_3) at (-1.2,-0.8)  {};
  \node[vertex] (G_4) at (1.2,-0.8)  {};
  \node[vertex] (G_5) at (-0.9,-1.67)  {};
  \node[vertex] (G_6) at (0.9,-1.7)  {};
  \node[vertex] (G_7) at (0,-2.2)  {};
  \draw (G_5)--(G_1) -- (G_6) -- cycle;
  \draw (G_5)--(G_2) -- (G_6) -- cycle;
  \draw (G_5)--(G_3) -- (G_6) -- cycle;
  \draw (G_5)--(G_4) -- (G_6) -- cycle;
  \draw (G_5)--(G_5) -- (G_6) -- cycle;
  \draw (G_5)--(G_7) -- (G_6) -- cycle;
  \draw (G_7)--(G_1) -- cycle;
  \draw (G_7)--(G_2) -- cycle;
  \draw (G_7)--(G_3) -- cycle;
  \draw (G_7)--(G_4) -- cycle;
  \draw (G_3)--(G_4) -- cycle;
  
\end{tikzpicture}
\end{document} 
```
.

---
#### Problem 2
1. Notice that the first two graphs are bipartite as they contain no odd cycles. However, the third graph is not with a cycle of length 5. Hence, Graph 3 cannot be isomorphic to Graph 1 or 2. 
   
   The first two graphs are indeed isomorphic given by: 
```tikz
\usepackage{tikz}
\usetikzlibrary{arrows}
\begin{document}

\begin{tikzpicture}[shorten >=1pt,->]
  \tikzstyle{vertex}=[circle,draw,fill=white,minimum size=6pt,inner sep=2pt]
  \node[vertex] (G_1) at (0,0) {1};
  \node[vertex] (G_2) at (0,-0.7) {2};
  \node[vertex] (G_3) at (0,-1.4) {3};
  \node[vertex] (G_4) at (0,-2.1) {4};
  \node[vertex] (G_5) at (1.5,0) {5};
  \node[vertex] (G_6) at (1.5,-0.7) {6};
  \node[vertex] (G_7) at (1.5,-1.4) {7};
  \node[vertex] (G_8) at (1.5,-2.1) {8};
	\draw (G_1) -- (G_7) -- (G_2) -- (G_5) -- (G_4) -- (G_6) -- (G_1) -- cycle;
	\draw (G_1) -- (G_8) -- (G_2) -- cycle;
	\draw (G_6) -- (G_3) -- (G_5) -- cycle;
	\draw (G_7) -- (G_4) -- cycle;
	\draw (G_8) -- (G_3) -- cycle;

\hfill 
\end{tikzpicture}
\begin{tikzpicture}[shorten >=1pt,->]
  \tikzstyle{vertex}=[circle,draw,fill=white,minimum size=6pt,inner sep=2pt]
  \node[vertex] (G_1) at (2.5,0) {1};
  \node[vertex] (G_2) at (3,-1.6) {2};
  \node[vertex] (G_3) at (4.1,-0.5) {3};
  \node[vertex] (G_4) at (4.6,-2.1) {4};
  \node[vertex] (G_5) at (4.1,-1.6) {5};
  \node[vertex] (G_6) at (4.6,0) {6};
  \node[vertex] (G_7) at (2.5,-2.1) {7};
  \node[vertex] (G_8) at (3,-0.5) {8};
	\draw (G_1) -- (G_7) -- (G_2) -- (G_5) -- (G_4) -- (G_6) -- (G_1) -- cycle;
	\draw (G_1) -- (G_8) -- (G_2) -- cycle;
	\draw (G_6) -- (G_3) -- (G_5) -- cycle;
	\draw (G_7) -- (G_4) -- cycle;
	\draw (G_8) -- (G_3) -- cycle;

  
\end{tikzpicture}

\end{document} 
```
    
2. The two graphs cannot be isomorphic. On the right graph, notice that the every second node around the outer octagon forms a $K_{4}$ s.t. there are four edges in the $K_{4}$ that form of a triangle with a node that is not part of the $K_{4}$. 
   
   However, notice that in the left graph, every subgraph isomorphic to $K_{4}$ has only two edges that form a triangle with a node not in the subgraph. 

---
#### Problem 3

Assume that $G$ is not connected. Let $v,w\in V(G)$. 
1. if $vw\notin G$, then $vw\in \overline{G}$ and there is a $(v,w)$-path in $\overline{G}$.
2. if $vw\in G$, then $v,w$ belong to the same connected component and as $G$ is not connected, there exists $u\in V(G)$ s.t. $uv,uw\notin G$, i.e. $uv,uw\in \overline{G}$. Hence, $vuw$ is a $(v,w)$-path in $\overline{G}$.
   
Therefore, $\overline{G}$ is connected.

---
#### Problem 4
Let $G$ be a simple graph on $n$ vertices. Notice that for any $v\in V(G)$, $d(v)\in \{ 0,1,\dots, n-1 \}$. However, 
1. if there is a vertex with degree 0, then there is no vertex with degree $n-1$. Hence, $d(v)\in \{ 0,1,\dots, n-2 \}$ for all $v\in V(G)$.
2. if there is no vertex with degree 0, then $d(v)\in \{ 1,\dots,n-1 \}$ for all $v\in V(G)$.

Hence, in both cases there are $n-1$ possible options for $n$ values and we conclude the claim via pigeonhole principle. 

---
#### Problem 5
We show this via induction. 
1. For $n=7$, then $5n-14=21={7 \choose 2}$. Hence, any graph with more than $5n-14$ edges is exactly $K_{7}$. In this case, $K_{7}$ is the desired subgraph.
2. Let $n\geq 8$. If $\delta(G)\geq 6$ then we are done. Otherwise, there exists $v\in V(G)$ with $d(v)\leq 5$. Then, consider $G':=G  \backslash \{ v \}$. Then, $\left| E(G') \right|=\left| E(G) \right|-d(v)\geq 5n-14-5=5(n-1)-14$. Hence, by induction there exists a subgraph in $G'$ with minimal degree 6 and of course this is a subgraph in $G$ as well.

---
#### Problem 6
Assume that there exists two paths $P_{1},P_{2}$ of maximal length that do not share any vertex. Then, as $G$ is connected, there exists a $(u,v)$-path $Q$ where $u$ is on $P_{1}$ and $v$ is on $P_{2}$. Modulo taking a subpath, we may assume that $Q$ is edge disjoint from $P_{1},P_{2}$. 

Let $k$ be the length of $P_{1}$ and $P_{2}$. Let $P'_{1}$ and $P_{2}'$ be the longer subpath of $P_{1},P_{2}$ that starts in an endpoint and ends in $u,v$ respectively. More formally, for $P_{1}:=v_{0}v_{1}\dots v_{k}$, $$P_{1}':=\begin{cases}v_{0}\dots u&\text{if }u=v_{i}\text{ with }i\geq \frac{k}{2}\\v_{k}\dots u&\text{otherwise}\end{cases}$$and similarly for $P'_{2}$. Then, $P'_{1}+Q+P'_{2}$ is a path of length $\geq \frac{k}{2}+1+\frac{k}{2}>k$. This is a contradiction to the fact that $P_{1},P_{2}$ are paths of maximal length.

---
#### Problem 7
Let $G=(V,E)$ be bipartite. Assume there is a cycle of odd length $v_{1}\dots v_{k}v_{1}$. Then, 

Let $G$ contain only even cycles. Fix a vertex $v_{0}$ and define: $$A:=\{ v\in V: d(v,v_{0})\text{ is even} \}$$and $B:= V \backslash A$. Then, 

 

