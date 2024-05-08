#Definition #GraphTheory 

> [!definition]
> A ***graph*** is a pair $G:=(V,E)$ of disjoint sets s.t. $E\subseteq \{ \{ x,y \}:x,y\in V,x\neq y \}$. 
- **Remark**: $v\in V$ is called a ***vertex/node*** and $e\in E$ is called an ***edge***. The vertices and edges of a graph $G$ are often denoted as $V(G)$ and $E(G)$.
- **Related definition**: The ***order*** of a graph $G$ is given as $\left| V(G) \right|$.
- **Related definition**: $v\in V$ is ***incident*** to $e\in E$ if $v\in e$. $E(v)\subseteq E$ denotes the set of all edges incident to $v$.
- **Notation**: An edge $\{ x,y \}\in E$ are also written as $xy$ (or $yx$).
- **Related definition**: for $X,Y\subseteq V$, $xy\in E$ is an ***$X$-$Y$-edge*** if $x\in X$ and $y\in Y$ or vice versa. The set of all $X$-$Y$-edges are denoted as $E(X,Y)$. 
- **Related definition**: Two vertices $x,y\in V$ are ***adjacent*** if $\{ x,y \}\in E$. Two edges $e\neq f$ are ***adjacent*** if $e\cap f\neq \varnothing$.
- **Related definition**: $W\subseteq V$ or $F\subseteq E$ are ***independent/stable*** if no two of its elements are adjacent.
- **Related definition**: A subgraph $H\subseteq G$ is ***spanning*** if $V(H)=V(G)$.
