#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a simple [[Path|connected]] [[graph]].
> 1. A ***vertex cut*** is $S\subseteq V$ s.t. $G \backslash S$ is not connected.
> 2. $G$ is ***$k$-connected*** if:
> 	1. $\left| V \right|> k$ and:
> 	2. for any $S\in {V \choose k-1}$, $G \backslash S$ is connected.

- **Related definition**: The ***connectivity number*** $\kappa$ of $G$ is given by: $$\kappa(G):=\text{max }\{ k\in \mathbb{N} :G\text{ is }k\text{-connected}\}$$

---
##### Properties
> [!lemma] Proposition 1
> Let $G$ be a graph.
> 1. $\kappa(G)\leq \delta(G)$

> [!proof]-
> Let $k> \delta(G)$. Then, we show that $G$ cannot be $k$-connected. Assume that $\left| V \right|>k$. Let $v$ s.t. $d(v)=\delta(G)$. Then, $k-1\geq \delta(G)$ and 
> 1. if $N(v)=V \backslash \{ v \}$. Then, as $d(u)\geq \delta(G)=d(v)$, we have that $G$ is a complete graph on $\delta(G)+1$ vertices and we get that $\kappa(G)\leq \delta(G)$. 
> 2. otherwise, there exists $w\neq v$ that is not in $N(v)$. Hence, by deleting $N(v)$, we disconnect $v$ and $w$. 

---
> [!lemma] Theorem 2 (Mader)
> Let $G$ be a graph and $k\in \mathbb{N}$.
> 1. if $d(G)\geq 4k$, then $G$ has a $k$-connected subgraph.

> [!proof]+
> If $k\in \{ 0,1 \}$, then the statement is trivial. Hence, let $k\geq 2$. Let further $m:=e(G)$. 
> 
> Now, let $G$ be an arbitrary simple graph on $n$ vertices and $m$ edges s.t. $n\geq 2k-1$ and $m\geq (2k-3)(n-k+1)+1$. Then, we claim that $G$ has a $k$-connected subgraph.
> 
> If this claim holds, then we have that: $$n\geq \Delta(G)\geq d(G)\geq 4k\geq 2k-1,\quad e(G)=\frac{n}{2}d(G)\geq 2kn\geq (2k-3)(n-k+1)+1$$
> We claim that $G$ has $n$ vertices and $m$ edges 
> 
> We show this using induction over $n$.
> 
> Let $m:=e(G)$. 
> 1. Let $n=k+1$. 
---
##### Examples
> [!h] Example 1
> We have:
> 1. $\kappa(K_{n})=n-1$.
> 2. $\kappa(K_{r,s})=\min \{ r,s \}$.

> [!proof]-
> We have:
> 1. Obvious.
> 2. Let $V(K_{r,s})=A\sqcup B$. Assume wlog $\min \{ r,s \}=r$. Then, for any $S\in {V \choose r-1}$, there will be at least $u$