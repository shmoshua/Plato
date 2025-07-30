#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a [[graph]].
> 1. A ***Hamiltonian path*** is a [[Path (Graph)|path]] which contains all vertices in the $V$. 
> 2. A ***Hamiltonian cycle*** is a cycle which contains all vertices in the $V$. 
> 3. $G$ is ***Hamiltonian*** if it has a Hamiltonian cycle.

^a7fcdb

- **Remark**: Finding Hamiltonian path is NP-hard.

---
##### Properties
> [!lemma] Proposition 1
> Let $G=(V,E)$ be a graph.
> 1. If $G$ is Hamiltonian, then $G$ is $1$-[[Tough Graph|tough]], i.e. for any $S\subseteq V$, $G \backslash S$ has at most $\left| S \right|$ connected components.  

^7a36d1

> [!proof]-
> Let $S\subseteq V$ and let $C_{1},\dots,C_{k}$ be the components of $G \backslash S$. Imagine that we are moving along a Hamilton cycle in some order, vertex-by-vertex. We must visit each component of $G \backslash S$ at least once; when we leave $C_{i}$ for the first time, let $v_{i}$ be the subsequent vertex visited, which must be in $S$. Each $v_{i}$ must be distinct because a cycle cannot intersect itself. Hence, $S$ must have at least as many vertices as the number of connected components of $G \backslash S$.

^e3866f

- **Remark**: The converse is not true. Consider the graph: 
	```tikz
	\usepackage{tikz}
	\usetikzlibrary{arrows}
	\begin{document}
	
	\begin{tikzpicture}[shorten >=1pt,->]
	  \tikzstyle{vertex}=[circle,fill=black,minimum size=3pt,inner sep=0pt]
	  \node[vertex] (G_1) at (0,0) {};
	  \node[vertex] (G_2) at (2,0) {};
	  \node[vertex] (G_3) at (1,1.73) {};
	  \node[vertex] (G_4) at (1,0.6) {};
	  \node[vertex] (G_5) at (1.2,1.15) {};
	  \node[vertex] (G_6) at (0.4,0.47) {};
	  \node[vertex] (G_7) at (1.4,0.17) {};
	  \draw (G_1)--(G_2) -- (G_3) -- (G_1) -- cycle;
	  \draw (G_4)--(G_5) -- (G_3) -- (G_4) -- cycle;
	  \draw (G_1)--(G_4) -- (G_6) -- (G_1) -- cycle;
	  \draw (G_2)--(G_4) -- (G_7) -- (G_2) -- cycle;
	  
	\end{tikzpicture}
	\end{document} 
	```
	This is 1-tough but not Hamiltonian.  ^7fb646

---
> [!lemma] Corollary 2
> Let $G=(A\sqcup B,E)$ be a bipartite graph. 
> 1. if $G$ is Hamiltonian, $\left| A \right|=\left| B \right|$.

^29e18f

> [!proof]-
> We have that:
> 1. As $G$ is Hamiltonian by Proposition 1, $G$ is 1-tough. Hence, $G \backslash A$ has at most $\left| A \right|$ connected components. Hence, $\left| B \right|\leq \left| A \right|$. By symmetry, we have $\left| A \right|=\left| B \right|$.

^3f2859

---
> [!lemma] Theorem 3 (Dirac/Ore, 1952)
> Let $G$ be a simple graph with $n\geq 3$ vertices.
> 1. if $\delta(G)\geq n / 2$, then $G$ is Hamiltonian.
> 2. if $d(u)+d(v)\geq n$ for all $u,v\in V$ with $uv\notin E$, then $G$ is Hamiltonian

^e8af36

> [!proof]-
> We have:
> 1. Let $G$ be a non-Hamiltonian graph with $\delta(G)\geq n / 2$. We may assume wlog that $G$ is maximal, i.e. if we add any edge $e$ to $G$, then $G\cup e$ is Hamiltonian. 
> 
> 	By maximality, we have that $G$ has a Hamiltonian path $v_{1}\dots v_{n}$from $u=v_{1}$ to $v=v_{n}$. Let 
> 	1. $S:=\{ i:(u,v_{i+1})\in E \}$ and
> 	2. $T:=\{ i:(v,v_{i})\in E \}$. 
>    
> 	  Then, we have that: $$\left| S\cap T \right| +\left| S\cup T \right|=\left| S \right| +\left| T \right| =d(u)+d(v)\geq n $$However, as $n\notin S\cup T$, we have that $\left| S\cup T \right|<n$ and $\left| S\cap T \right|\geq 1$. Hence, there exists $i\in S\cap T$ and we have that: $$uv_{i+1}\dots v_{n-1}vv_{i}v_{i-1}\dots v_{2}u$$is a Hamiltonian cycle, which is a contradiction. 
> 1. Analogous to above.

^afd4a9

---
