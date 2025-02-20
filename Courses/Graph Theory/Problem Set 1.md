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