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

> [!proof]-
> We have that:
> 1. Observe that: $$\left| E \right| = \frac{1}{2}\sum_{v\in V}^{}d(v)=\frac{1}{2}d(G)\left| V \right| $$
> 2. As $\left| E \right|= \frac{1}{2}\sum_{v\in V}^{}d(v)$ is an integer, $\sum_{v\in V}^{}d(v)$ is even.
---
> [!lemma] Proposition 2
> Every graph $G$ with $\left| E \right|\geq 1$ has a subgraph $H$ s.t. $\varepsilon(G)\leq \varepsilon(H)<\delta(H)$.

> [!proof]-
> We construct a sequence of subgraphs as follows. Let $G_{0}:=G$. 
> 1. if $G_{i}$ has a vertex $v_{i}$ with $d(v_{i})\leq \varepsilon(G_{i})$, then $G_{i+1}:=G_{i} -v_{i}$.
> 2. otherwise, let $H:=G_{i}$.
>    
>  Then, we see that $\varepsilon(G_{i+1})\geq \varepsilon(G_{i})$ and $\varepsilon(H)\geq \varepsilon(G)$. As $\varepsilon(G)>0$, we have that $\delta(H)>\varepsilon(H)$.
---
> [!lemma] Lemma 
> Let $G:=(V,E)$ be a graph with $\left| V \right|=n$ vertices. For $m,r,a>0$, if there exists $t\in \mathbb{Z}_{> 0}$ s.t. $$\frac{d(G)^t}{n^{t-1}}-{n \choose r}\frac{m^t}{n^t}\geq a$$then there exists $U\subseteq V$ with $\left| U \right|\geq a$ such that every $r$ vertices in $U$ have at least $m$ common neighbors.

> [!proof]+
> For a vertex set $T$, let $N(T):=\bigcap_{x\in T}^{}N(x)$. Pick a set of $t$ vertices $T$ uniformly at random with repetition. Set $A:=N(T)$. Let $X$ be the random variable for the cardinality of $A$. Then, $$\mathbb{E}[X]=\sum_{v\in V}^{}\left( \frac{d(v)}{n} \right)^t $$