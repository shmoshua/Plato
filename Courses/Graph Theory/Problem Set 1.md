#GraphTheory #Series 

#### Problem 1
1. there is no such graph as there is an odd number of vertices of odd degree.
2. as there are 7 vertices in total and three vertices with degree 6, the minimum degree is 3. Hence, such a graph doesn't exist.
3. Assume $G$ is such a graph with $v_{1},\dots,v_{8}$ as the vertices in order of the degree sequence. Let $S:=\{ v_{1},\dots,v_{5} \}$ and we notice that as 
4. 
5. we have: 
```tikz
\usepackage{tikz}
\usetikzlibrary{arrows}
\begin{document}

\begin{tikzpicture}[shorten >=1pt,->]
  \tikzstyle{vertex}=[circle,fill=black,minimum size=6pt,inner sep=2pt]
  \node[vertex] (G_1) at (-0.5,0) {};
  \node[vertex] (G_2) at (0.5,0)   {};
  \node[vertex] (G_3) at (-1.2,-0.8)  {};
  \node[vertex] (G_4) at (1.2,-0.8)  {};
  \node[vertex] (G_5) at (-0.8,-1.6)  {};
  \node[vertex] (G_6) at (0.8,-1.6)  {};
  \node[vertex] (G_7) at (0,-2.2)  {};
  \draw (G_5)--(G_1) -- (G_6) -- cycle;
  \draw (G_5)--(G_2) -- (G_6) -- cycle;
  \draw (G_5)--(G_3) -- (G_6) -- cycle;
  \draw (G_5)--(G_4) -- (G_6) -- cycle;
  \draw (G_5)--(G_5) -- (G_6) -- cycle;
  \draw (G_5)--(G_7) -- (G_6) -- cycle;
  
\end{tikzpicture}
\end{document} 
```
3. 