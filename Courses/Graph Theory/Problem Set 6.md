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
Let $G$ be a connected bipartite plane graph. Then, $G$ contains no odd cycles. If the outer face is of odd length, we have an odd cycle after removing all edges that are not contained in the boundary of any other faces, as they contribute only an even number to the length. Similarly, for any other inner face, if the length is odd, we can find an odd cycle. 

Assume now that all the faces have even length. If $G$ is not bipartite, then there exists an odd cycle and consider an odd cycle $C$ with the minimum number of faces inside. Then, by assumption $C$ cannot be a face boundary and $C$ contains at least 2 faces. 
1. if there exists a face $f$ in $C$ whose boundary contains $C$, as there exists another face contained in $C$, we have a cycle $C'$ contained entirely in $f$. Now, as $l(f)$ is even, $C'$ is an odd cycle. However as $C'$ has strictly fewer faces inside than $C$, this is a contradiction to the minimality of $C$.
2. otherwise, there has to exist a "diagonal" path in $C$ from one point in $C$ to another point in $C$ that is contained in the interior of $C$. This gives us two cycles $D,D'$ and as by the minimality of $C$, we have that both are even. This is a contradiction as $C$ is odd and we have that: $$\left| D \right| +\left| D' \right| -2k=\left| C \right| $$where $k$ is the number of interior nodes on the diagonal path.
   
This shows that $G$ is bipartite.

---
#### Problem 4
Assume that there exists a drawing of $G$ with $\ell\leq k-1$ crossing pairs of edges. Then, we can delete at most $\ell$ edges from $G$ and obtain a drawing of a graph on $n$ vertices with more than $3n-6$ edges but with no crossings, i.e. the new graph $G'$ is planar. This is a contradiction. 

---
#### Problem 5
Let $k$ be the number of faces with all three colors. For a face $f$ let $c(f)$ be the number of bichromatic edges in its triangular boundary. Then, we notice that $c(f)=1$ is impossible as we cannot have only one bichromatic edge in a triangle. Hence, we have that: $$2\cdot\#\text{bichromatic edges}=\sum_{f\text{ face}}^{}c(f)=3k+\text{even}$$
Therefore, $3k$ is even and this shows that $k$ is even.

---
#### Problem 6
We draw a graph $G$ on the $n$ points where $uv\in E(G)$ if $d(u,v)=1$. Now assume that there exists a crossing between $uv$ and $wz$. Let $p$ denote the intersection between the two edges. Wlog we may assume that $d(u,p)\leq d(v,p)$ and $d(w,p)\leq d(z,p)$. Then, $d(u,p),d(w,p)\leq 1 /2$.
1. If either $d(u,p)$ or $d(w,p)$ is strictly less than $1 / 2$, wlog assume $d(u,p)<  1 / 2$. As we also have $d(w,p)\leq 1 / 2$, by triangle inequality, $$d(u,w)\leq d(u,p)+d(w,p)< 1$$which is a contradiction.
2. Otherwise both $d(u,p)=d(w,p)= 1/ 2$ and the two edges form the two diagonals of a rectangle. This is again a contradiction as the side lengths cannot be larger than the length of a diagonal. 

Therefore, this graph is planar and there are at most $3n-6$ edges, i.e. pairs with distance exactly 1 between them.

---

#### Problem 7
We have that:$$M:=D-A$$
where $D$ is the degree matrix and $A$ is the adjacency matrix. More concretely, $$M=\begin{bmatrix} sI_{r}&0\\0&rI_{s}\end{bmatrix}-\begin{bmatrix}0&1_{r \times s}\\1_{ s \times r}&0\end{bmatrix}=\begin{bmatrix}sI_{r}&-1_{r \times s}\\-1_{ s \times r}&rI_{s}\end{bmatrix}$$
Then, $$M_{11}=\begin{bmatrix}sI_{r-1}&-1_{(r-1) \times s}\\-1_{ s \times (r-1)}&rI_{s}\end{bmatrix}$$Therefore, $$$$