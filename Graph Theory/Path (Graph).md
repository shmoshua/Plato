#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a [[graph]].
> 1. A ***path*** is a [[walk]] $W=(v_{1},\dots,v_{k})$ s.t. $v_{i}\neq v_{j}$ for all $i\neq j$.
> 2. A **cycle** is a walk $W=(v_{1},\dots,v_{k})$ where $v_{1}=v_{k}$ and $(v_{1},\dots,v_{k-1})$ is a path.

^9274a2

- **Related Notation**: The ***length*** of a walk $W$ is given by the number of edges in $W$. ^14b918
- **Related Notation**: For $u,v\in V$, a $(u,v)$-***path*** is a path $(v_{1},\dots,v_{k})$ s.t. $u=v_{1}$ and $v=v_{k}$.  ^150295
- **Related Definition**: A graph $G$ is ***connected*** if for every $v,w\in G$, there exists a $(v,w)$-path. ^0c6bd0
- **Related Definition**: Two paths are ***independent*** if they do not share an inner node.
- **Related Definition**: For $s,t\in V$, the ***distance*** $d_{G}(s,t)$ is the length of the shortest $(s,t)$-path in $G$. If such path doesn't exist, $d_{G}(s,t)=\infty$.
- **Related Definition**: The ***diameter*** of a graph is $\text{diam}(G):= \max_{s,t\in V}d_{G}(s,t)$.
---
##### Properties
> [!lemma] Proposition 1
> Let $G$ be a graph and $u,v\in V$. 
> 1. any $(u,v)$-walk contains a $(u,v)$-path. 

^82af28

> [!proof]-
> Let $(v_{1},\dots,v_{k})$ be a $(u,v)$-walk. We show by induction over $k$. 
> 1. if $k=2$, then the walk is also a path.
> 2. if $k\geq 3$, then if there is no $i\neq j$ with $v_{i}=v_{j}$, then we have a path and we're done. Suppose otherwise. Then, wlog assume $i<j$ and: $$(v_{1},\dots,v_{i-1},v_{j},\dots,v_{k})$$ is a $(u,v)$-walk and by induction we have a $(u,v)$-path. 

^4d3705

---
> [!lemma] Proposition 2
> For a finite graph $G$ with $\delta(G)\geq 2$,
> 1. $G$ has a path of length $\delta(G)$. 
> 2. $G$ has a cycle of length at least $\delta(G)+1$.

^4e3ecc

> [!proof]-
> We have:
> 1. Let $x_{0}\dots x_{k}$ be the longest path in $G$. Then, all the neighbors of $x_{k}$ are on the path. Hence, $k\geq d(x_{k})\geq\delta(G)$.
> 2. Further, with $x_{k}$, we get a cycle of length at least $\delta(G)+1$.

^ccedf3

- **Remark**: This result is tight! Consider $K_{\delta+1}$ for any $\delta\geq 2$. ^590fcb
---
> [!lemma] Proposition 3
> Let $G$ be a $n$-vertex graph with $m$ edges. Then, 
> 1. $G$ has at least $n-m$ connected components. 

^aec20e

> [!proof]-
> Delete all edges and get empty graph. Put edges back one by one and track the number of components. 
> 
> Then, for all $m$, the number of connected components can decrease by at most 1. As we have $n$ connected components in the beginning, we have the claim. 

^0d4367

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
