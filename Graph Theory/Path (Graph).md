#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a [[graph]] and $s,t\in V$.
> 1. A ***path*** is a $(s,t)$-[[walk]] $W=(v_{1},\dots,v_{k})$ s.t. $v_{i}\neq v_{j}$ for all $i\neq j$.
> 2. A **cycle** is a walk $W=(v_{1},\dots,v_{k})$ where $v_{1}=v_{k}$ and $(v_{1},\dots,v_{k-1})$ is a path.

^9274a2

- **Related Notation**: For an edge $e\in E$ and a walk $W$, $e\in W$ if $e=(v_{i},v_{i+1})$ for some $i$. The ***length*** of $W$ is given by the number of edges in $W$.
- **Related Definition**: A graph $G$ is ***connected*** if for every $v,w\in G$, there exists a $(v,w)$-path.
- **Related Definition**: Two paths are ***independent*** if they do not share an inner node.
- **Related Definition**: For $s,t\in V$, the ***distance*** $d_{G}(s,t)$ is the length of the shortest $(s,t)$-path in $G$. If such path doesn't exist, $d_{G}(s,t)=\infty$.
- **Related Definition**: The ***diameter*** of a graph is $\text{diam}(G):= \max_{s,t\in V}d_{G}(s,t)$.
---
##### Properties
> [!lemma] Proposition 1
> For a finite graph $G$ with $\delta(G)\geq 2$,
> 1. $G$ has a path of length $\delta(G)$. 
> 2. $G$ has a cyclic of length at least $\delta(G)+1$.

> [!proof]-
> We have:
> 1. Let $x_{0}\dots x_{k}$ be the longest path in $G$. Then, all the neighbors of $x_{k}$ are on the path. Hence, $k\geq d(x_{k})\geq\delta(G)$.
---

> [!lemma] Theorem (Cycles in Digraphs)
> Let $k\in \mathbb{Z}_{\geq 1}$ and $D=(V,E)$ a finite digraph with $\Delta^-$ and $\delta^+$ as the maximal in-degree and minimal out-degree. 
> 1. If it holds that: $$e((\delta^++1)\Delta^-+1)\left( 1-\frac{1}{k} \right) ^{\delta^+}\leq 1$$then $D$ contains a directed cycle of length divisible by $k$.

^eb646f

> [!proof]-
> Let's first remove edges until there are exactly $\delta^+$ out-neighbors for each node. Then, $\delta^+$ stays the same and $\Delta^-$ decreases but the condition still holds. Further, any circle in the new digraph is also one in the old one. 
> 
> Let $c:V\to[k]$ be a random uniform coloring with $\mathbb{P}(c(v)=i)=1 / k$ for all $v\in V$ and $i\in[k]$. For any vertex $v\in V$, let $B_{v}$ be the event that there is no $u$ s.t. $v\to u\in E$ and $c(u)\equiv_{k}c(v)+1$
> 
> We now use the [[Independence|Lovász Local Lemma]].
> 1. $\mathbb{P}(B_{v})= (1-\frac{1}{k})^{\delta^+}$
> 2. $B_{v}$ only depends on the colors of the out-neighbors $N^+(v)$. Therefore, $B_{v}$ is mutually disjoint from all events $B_{u}$ where $\{ v \}\cup N^+(v)$ and $\{ u \}\cup N^+(u)$ are disjoint. This happens exactly when $u$ is either in $\{ v \}\cup N^+(v)$ or is an in-neighbor of one of the vertices. 
>    
>    For each $x\in N^+(v)$, there are at most $\Delta^-$ vertices $u\neq v$ that could be either $u=x$ or $u\to x\in E$. Hence, the total number of vertices $u\neq v$ s.t. $\{ u \}\cup N^+(u)$ intersects $\{ v \}\cup N^+(v)$ is at most $(\delta^++1)\Delta^-$.
> 
> Therefore, by the local lemma, $\mathbb{P}\left( \bigcap_{v\in V}^{}B_{v}^c \right)>0$. 

^c1e54e

---
