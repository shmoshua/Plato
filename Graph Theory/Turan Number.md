#Definition #GraphTheory 

> [!definition]
> Let $H$ be a [[graph]]. 
> 1. the ***Turan number*** $\text{ex}(n,H)$ of $H$ and $n$ is given by: $$\text{ex}(n,H):=\max_{\begin{array}\ \left| G \right| =n\\ H\not\leq G\end{array}}e(G)$$

- **Related definition**: The graph $K_{n_{1},..,n_{r}}$ with $\left| n_{i}-n_{j} \right|\leq 1$is called the ***Turan graph*** $T_{n,r}$.
---
##### Properties
> [!lemma] Theorem 1 (Turan 1941)
> We have that: $$\text{ex}(n,K_{r+1})=e(T_{n,r})$$where $T_{n,r}$ is the unique graph giving the maximum. 

> [!proof]+ 
> Let $G:=(V,E)$ be the maximizer of $\text{ex}(n,K_{r+1})$. Let $v_{m}\in V$ be the vertex of maximal degree. Let further $S:=N(v_{m})$ with $\left| S \right|=d(v_{m})=:d_{m}$. Set $T:= V \backslash S$. As $G$ contains no $K_{r+1}$ and $v_{m}$ is adjacent to every node in $S$, $S$ contains no $r$-clique. 
> 
> Let $H$ be another graph on $V$ where it is given from $G$ by deleting all edges in $E(T)$ and adding every possible edge between $S$ and $T$. Then, of course $H$ also doesn't contain any $K_{r+1}$. 
> 
> If $v\in S$, then we certainly have that $d_{H}(v)\geq d_{G}(v)$ and for $v\in T$, $$d_{H}(v)=\left| S \right| =\Delta(G)\geq d_{G}(v)$$Therefore, we infer that $e(H)\geq e(G)$ and by the maximality, there should be a maximizer of the form $H$. 