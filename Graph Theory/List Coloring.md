#Definition #GraphTheory 

> [!definition]
> Let $G$ be a [[graph]] and $\{ L(v) \}_{v\in V(G)}$ be a set.
> 1. A ***list coloring*** $c$ w.r.t. $L$ is a [[Graph Coloring|proper coloring]] s.t. $c(v)\in L(v)$ for all $v\in V(G)$.
> 2. $G$ is $k$-***chooseable/list-colorable*** if there exists a list coloring for any $L$ with $\left| L(v) \right|=k$. 
- **Related definition**: the ***list chromatic number*** is given by $\chi_{l}(G)$. 
---
##### Properties
> [!lemma] Proposition 1
> Let $G$ be a graph. 
> 1. $\chi(G)\leq \chi_{\ell}(G)$.
> 2. $\chi_{\ell}(G)\leq \Delta(G)+1$.

> [!proof]-
> We have that:
> 1. We can choose $L$ with $L(v)=[k]$. 
> 2. By [[Graph Coloring|Greedy coloring]].
---
> [!lemma] Theorem 2 (Erdös, Rubin, Taylor 1979)
> For $m:={2k-1 \choose k}$,
> 1. $K_{m,m}$ is not $k$-choosable.

> [!proof]-
> We have that:
> 1. Let $K_{m,m}=(A\sqcup B, E)$. For $A,B$, let $L(v)$ be a different $k$-element subset of $[2k-1]$ over $v\in A$. Similarly for $v\in B$. Let $c$ be a choice function. Then, 
> 	1. If $c$ uses less than $k$ colors for $A$, then there is a $k$-element set $K\subseteq [2k-1]$ that is not used. In other words, for the vertex $v$ in $A$ with $L(v)=K$, no color was chosen, contradiction.
> 	2. If $c$ uses at least $k$ colors for $A$, then there is a $k-$element set $K\subseteq[2k-1]$ that is used. Then, no color can be chosen for $v\in B$ with $L(v)=K$. Contradiction.