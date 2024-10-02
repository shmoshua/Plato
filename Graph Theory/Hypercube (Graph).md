#Definition #GraphTheory 

> [!definition]
> A ***hypercube*** of dimension $r$, denoted as $Q_{r}$, is a [[graph]] on $\{ 0,1 \}^r$ where: $$x \sim y \iff \left\| x-y \right\| _{0}=1$$
- **Remark**: $Q_{r}$ is bipartite and $r$-regular.
---
##### Properties
> [!lemma] Lemma 1
>  Let $H:=A\sqcup B$ be a bipartite graph where for all $x\in B$, $d(x)\leq \ell$ for some $\ell$. Then, given a graph $G$ and $U\subseteq V(G)$ s.t. 
>  1. $\left| U \right|\geq \left| A \right|$
>  2. any $\ell$ vertices in $U$ have at least $\left|H\right|$ common neighbors.
>  
>  Then, $H$ is contained in $G$.

> [!proof]-
> We first embed $A$ in $U$ anyway we want. Then, for $B=\{ v_{1},\dots,v_{b} \}$,  we can embed them in the order as follows. 
> 
> Any $N(v_{i})$ have at least $\left| H \right|$ common neighbors by assumption, there always exists a vertex that is not embedded yet.

---
> [!lemma] Theorem 1
> $R(Q_{r})\leq 2^{3r}$

> [!proof]+
> We have that:
> 

- **Conjecture**: $R(Q_{r})=O(2^r)$, i.e. it is linear in $n:=V(Q_{r})$. 