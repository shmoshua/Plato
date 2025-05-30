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
	2. Let $1\leq i\leq k-1$. Notice that as soon as we have a cycle on $V(P)$ we have a contradiction as $v$ with the cycle contains a path longer than $P$. Hence, we first have $v_{0}v_{k}\notin E$. Further, by letting $S:= N(v_{0})$ and $T:=\{ v_{i+1}:v_{i}\in N(v_{k}) \}$, we have that $\left| S\cap T \right|=0$ as otherwise we have a cycle the same way for the proof for Dirac's theorem. Therefore: $$k\geq \left| S\cup T \right| =\left| S \right| +\left| T \right| \geq 2\delta$$This proves the statement.
2. Let $P:= v_{0}v_{1}\dots v_{k}$ be any longest path in $G$. If $P$ is not a Hamiltonian path, we have similarly as above $v\in V$ that is not on $P$ but adjacent to $v_{i}$. Then, for $S:= N(v_{0})$ and $T:=\{ v_{i+1}:v_{i}\in N(v_{k}) \}$, we have $\left| S\cup T \right|\leq n-2$ and: $$n-2+\left| S\cap T \right| \geq \left| S\cup T \right| +\left| S\cap T \right| =\left| S \right| +\left| T \right| \geq 2\delta\geq n-1$$It follows that $\left| S\cap T \right|\geq 1$. This shows that we can find a cycle on $V(P)$ and further a path of length $\left| P \right|+1$. This is a contradiction and $P$ is Hamiltonian. 

---
#### Problem 4
Let $n\geq 3$. Consider a graph $G=(V,E)$ on $n$ nodes where there exists $v\in V$ s.t. $d(v)=1$ and $G \backslash v\cong K_{n-1}$. Then, $G$ cannot be Hamiltonian due to $v$ and $\left| E \right|={n-1 \choose 2}+1$. 

Now, we will show that any graph $G$ on $n$ nodes with at least ${n-1 \choose 2}+2$ edges has to be Hamiltonian. Notice that: $${n \choose 2}-{n-1 \choose 2}-2=n-3$$and there are at most $n-3$ edges in the complement graph $\overline{G}$. Hence, for any $vw\notin E(G)$, we have that: $$d(v)+d(w)\geq (n-2)+(n-2)-(n-4)=n$$The statement then follows from Ore's theorem.

---
#### Problem 5
1. Let $n=2k$. If $n=2$ then the statement is trivial by considering an empty graph for $d=0$ and an edge for $d=1$. Hence, we may assume that $n\geq 3$. 
   
   We claim that if $G$ is a $d$-regular graph on $n$ nodes for $d\geq \frac{n}{2}$, then we have a $(d-2)$-regular graph $G'$ on $n$ nodes. As $G$ is $d$-regular, $\delta(G)\geq n /2$ and by Dirac, there exists a Hamiltonian cycle $H$ in $G$. Deleting this cycle from $G$ and calling the rest as $G'$, we have that every degree decreases exactly by 2 and we have a $(d-2)$-regular graph. This shows the claim. 
   
   Notice that we have $K_{n}$ as a $(n-1)$-regular graph and as $n$ is even we have a perfect matching $M$. by deleting $M$ from $K_{n}$, we have a $(n-2)$-regular graph. Therefore, using the claim we get the existence of a $d$-regular graph for all $n-1\geq d\geq \frac{n}{2}-2$. We conclude by noting that for any $d$-regular graph $G$, the complement $\overline{G}$ is a $(n-1-d)$-regular graph. 
   
   
   
2. Let $d$ be even. Then, on $V:=[n]$, we can define a graph $G$ s.t. each vertex $i$ is adjacent to exactly $S_{i}:=\{ i-d / 2, \dots, i-1, i+1,\dots,i+d / 2 \}$ modulo $n$. This is well-defined as this is a symmetric relation and as $\left| S_{i} \right|=d\leq n-1$ for all $i$, we have that $G$ is a $d$-regular graph.
   
---