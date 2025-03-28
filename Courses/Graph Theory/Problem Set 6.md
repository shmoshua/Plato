#Series #GraphTheory 

#### Problem 1
We have that $K_{3,3}$ is not planar. Therefore, if $3\leq r$ then $K_{r,s}$ contains $K_{3,3}$ and is not planar. 
1. Assume that $r=1$. Then, $K_{r,s}$ is a star and is planar for any $s$.
2. Assume that $r=2$. Then, $K_{r,s}=(A\cup B,E)$ is planar by having the $s$ nodes from $B$ between the two nodes from $A$ for any $s$. 

Therefore, $K_{r,s}$ with $r\leq s$ is planar if and only if $r\leq 2$.

---
#### Problem 2
1. Assume that $\delta(G)\geq 6$. Then, $$e(G)=\frac{\sum_{v\in V(G)}^{}d(v)}{2}\geq 3\left| G \right| > 3\left| G \right| -6 $$Therefore $G$ cannot be planar. Further, this gives us that any planar graph with $\delta(G)= 5$ needs to have at least $12$ vertices. In fact, there is one on exactly 12 vertices.
```tikz
\usepackage{tikz}
\usetikzlibrary{arrows}
\begin{document}

\begin{tikzpicture}[shorten >=1pt,->]
\tikzstyle{vertex}=[circle,fill=black,minimum size=6pt,inner sep=2pt]
\node[vertex] (G_1) at (0,0) {};
\node[vertex] (G_2) at (2,0)   {};
\node[vertex] (G_3) at (0,2)  {};
\node[vertex] (G_4) at (2,2)  {};
\node[vertex] (g_1) at (1,0.2) {};
\node[vertex] (g_2) at (0.2,1)   {};
\node[vertex] (g_3) at (1.8,1)  {};
\node[vertex] (g_4) at (1,1.8)  {};

\node[vertex] (H_1) at (0.55,0.55) {};
\node[vertex] (H_2) at (1.45,0.55)   {};
\node[vertex] (H_3) at (0.55,1.45)  {};
\node[vertex] (H_4) at (1.45,1.45)  {};

\node[vertex] (h_1) at (1,0.55) {};
\node[vertex] (h_2) at (1.45,1)   {};
\node[vertex] (h_3) at (1,1.45)  {};
\node[vertex] (h_4) at (0.55,1)  {};
\draw (G_1) -- (G_2) -- (G_4) -- (G_3) -- (G_1) -- cycle;
\draw (g_1) -- (H_1) -- (g_2) -- (H_3) -- (g_4) -- (H_4) -- (g_3) -- (H_2) --  (g_1) -- cycle;
\draw (h_1) -- (h_2) -- (h_3) -- (h_4) -- (h_1) -- cycle;
\draw (H_1) -- (H_2) -- (H_4) -- (H_3) -- (H_1) -- cycle;
\draw (H_1) -- (G_1) -- cycle;
\draw (H_2) -- (G_2) -- cycle;
\draw (H_3) -- (G_3) -- cycle;
\draw (H_4) -- (G_4) -- cycle;
\draw (G_1) -- (g_1) -- (G_2) -- cycle;
\draw (G_2) -- (g_3) -- (G_4) -- cycle;
\draw (G_3) -- (g_4) -- (G_4) -- cycle;
\draw (G_1) -- (g_2) -- (G_3) -- cycle;
\draw (g_1) -- (h_1) -- cycle;
\draw (g_2) -- (h_4) -- cycle;
\draw (g_3) -- (h_2) -- cycle;
\draw (g_4) -- (h_3) -- cycle;
\end{tikzpicture}\end{document} 
```
.
1. As $G$ is bipartite, it is triangle free. Assume $\delta(G)\geq 4$. Then, $$e(G)\geq 2\left| G \right| > 2\left| G \right| -4$$Hence, $G$ cannot be planar. However, for $\delta(G)=3$, we have that the following is a planar graph.
```tikz
\usepackage{tikz}
\usetikzlibrary{arrows}
\begin{document}

\begin{tikzpicture}[shorten >=1pt,->]
\tikzstyle{vertex}=[circle,fill=black,minimum size=6pt,inner sep=2pt]
\node[vertex] (G_1) at (0,0) {};
\node[vertex] (G_2) at (2,0)   {};
\node[vertex] (G_3) at (0,2)  {};
\node[vertex] (G_4) at (2,2)  {};
\node[vertex] (H_1) at (0.5,0.5) {};
\node[vertex] (H_2) at (1.5,0.5)   {};
\node[vertex] (H_3) at (0.5,1.5)  {};
\node[vertex] (H_4) at (1.5,1.5)  {};
\draw (H_1)--(G_1) -- (G_2) -- (G_4) -- (G_3) -- (G_1) -- cycle;
\draw (H_1) -- (H_2) -- (H_4) -- (H_3) -- (H_1) -- cycle;
\draw (H_2) -- (G_2) -- cycle;
\draw (H_3) -- (G_3) -- cycle;
\draw (H_4) -- (G_4) -- cycle;
\end{tikzpicture}\end{document} 
```

---
#### Problem 3
