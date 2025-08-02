#Definition #GraphTheory 

> [!definition]
> Let $G$ be a [[graph]] and $\{ L(v) \}_{v\in V(G)}$ be a set.
> 1. A ***list coloring*** $c$ w.r.t. $L$ is a [[Graph Coloring|proper coloring]] s.t. $c(v)\in L(v)$ for all $v\in V(G)$.
> 2. A ***list edge coloring*** $c$ w.r.t. $L$ is a [[Graph Coloring|proper edge coloring]] s.t. $c(e)\in L(e)$ for all $e\in E(G)$.
> 3. $G$ is $k$-***chooseble/list-colorable*** if there exists a list coloring for any $L$ with $\left| L(v) \right|=k$. 
> 4. $G$ is $k$-***edge-chooseble/list edge-colorable*** if there exists a list edge coloring for any $L$ with $\left| L(e) \right|=k$. 
> 5. $G$ is $f$-***choosable*** for $f:V(G)\to \mathbb{N}$ if there exists a list coloring for any $L$ with $\left| L(v) \right|\geq f(v)$.
- **Related definition**: the ***list/list-edge chromatic number*** is given by $\chi_{l}(G),\chi_{l}'(G)$. 
---
##### Properties
> [!lemma] Proposition 1
> Let $G$ be a graph. 
> 1. $\chi(G)\leq \chi_{\ell}(G)$.
> 2. $\chi_{\ell}(G)\leq \Delta(G)+1$.
> 3. $\chi_{\ell}'(G)=\chi_{\ell}(L(G))$

> [!proof]-
> We have that:
> 4. We can choose $L$ with $L(v)=[k]$. 
> 5. By [[Graph Coloring|Greedy coloring]].
---
> [!lemma] Theorem 2 (Erdös, Rubin, Taylor 1979)
> For $m:={2k-1 \choose k}$,
> 1. $K_{m,m}$ is not $k$-choosable.

> [!proof]-
> We have that:
> 1. Let $K_{m,m}=(A\sqcup B, E)$. For $A,B$, let $L(v)$ be a different $k$-element subset of $[2k-1]$ over $v\in A$. Similarly for $v\in B$. Let $c$ be a choice function. Then, 
> 	1. If $c$ uses less than $k$ colors for $A$, then there is a $k$-element set $K\subseteq [2k-1]$ that is not used. In other words, for the vertex $v$ in $A$ with $L(v)=K$, no color was chosen, contradiction.
> 	2. If $c$ uses at least $k$ colors for $A$, then there is a $k-$element set $K\subseteq[2k-1]$ that is used. Then, no color can be chosen for $v\in B$ with $L(v)=K$. Contradiction.

- **Remark**: The above theorem can be generalized: $\chi_{\ell}(G)\geq (1-\text{o}(1))\log_{2}d(G)$.

---
> [!lemma] Theorem 3 (Galvin 1995)
> $\chi'_{\ell}(K_{n,n})=n$. 