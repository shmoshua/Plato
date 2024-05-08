#Definition #GraphTheory 

> [!definition]
> A ***graph*** is a pair $G:=(V,E)$ of disjoint sets s.t. $E\subseteq \{ \{ x,y \}:x,y\in V,x\neq y \}$, where
> 1.  $v\in V$ is called a ***vertex/node*** and $e\in E$ is called an ***edge***. The vertices and edges of a graph $G$ are often denoted as $V(G)$ and $E(G)$.
> 2. The ***order*** of a graph $G$ is given as $\left| V(G) \right|$.

- **Related definition**: $v\in V$ is ***incident*** to $e\in E$ if $v\in e$. $E(v)\subseteq E$ denotes the set of all edges incident to $v$.
- **Notation**: An edge $\{ x,y \}\in E$ are also written as $xy$ (or $yx$).
- **Related definition**: for $X,Y\subseteq V$, $xy\in E$ is an ***$X$-$Y$-edge*** if $x\in X$ and $y\in Y$ or vice versa. The set of all $X$-$Y$-edges are denoted as $E(X,Y)$. 
- **Related definition**: Two vertices $x,y\in V$ are ***adjacent*** if $\{ x,y \}\in E$. Two edges $e\neq f$ are ***adjacent*** if $e\cap f\neq \varnothing$.
- **Related definition**: $W\subseteq V$ or $F\subseteq E$ are ***independent/stable*** if no two of its elements are adjacent.
- **Related definition**: A subgraph $H\subseteq G$ is ***spanning*** if $V(H)=V(G)$.
- **Related definition**: The ***complement*** of graph $G=(V,E)$ is $\overline{G}:=(V,E^c)$
- **Related definition**: For $U\subseteq V$, the set of ***neighbors*** of $U$ is denoted as $N(U)\subseteq V \backslash U$. 
- **Related definition**: The ***degree*** is a map defined as: $$\begin{array}{cccc} {d:}&{V}&\to&{\mathbb{N}}\\&{v} &\mapsto & {\left| E(v) \right| } \end{array}{}$$if $d(v)=0$, $v$ is called ***isolated***. We have:
	1. $\delta(G)$ denotes the minimal degree of $G$.
	2. $\Delta(G)$ denotes the maximal degree of $G$.
	3. $d(G)$ denotes the average degree of $G$, i.e. $d(G)=\frac{1}{\left| V \right|}\sum_{v\in V}^{}d(v)$ if $G$ is finite.
- **Remark**: $\delta(G)\leq d(G)\leq\Delta(G)$
- **Related definition**: The ***edge density*** of a graph is $\varepsilon(G):=\left| E \right| / \left| V \right|$.
---
##### Properties
> [!lemma] Proposition 1
> For a graph $G$, 
> 1. $d(G)=2\varepsilon(G)$.
> 2. the number of vertices of odd degree is always even,

> [!proof]+
> We have that:
> 1. Observe that: $$\left| E \right| = \frac{1}{2}\sum_{v\in V}^{}d(v)=\frac{1}{2}d(G)\left| V \right| $$
> 2. As $\left| E \right|=$ is an 