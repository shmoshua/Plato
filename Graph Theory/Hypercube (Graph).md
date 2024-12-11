#Definition #GraphTheory 

> [!definition]
> A ***hypercube*** of dimension $r$, denoted as $Q_{r}$, is a [[graph]] on $\{ 0,1 \}^r$ where: $$x \sim y \iff \left\| x-y \right\| _{0}=1$$

^0ce392

- **Remark**: $Q_{r}$ is bipartite and $r$-regular. ^6fb7b0
---
##### Properties
> [!lemma] Lemma 1
>  Let $H:=A\sqcup B$ be a bipartite graph where for all $x\in B$, $d(x)\leq \ell$ for some $\ell$. Then, given a graph $G$ and $U\subseteq V(G)$ s.t. 
>  1. $\left| U \right|\geq \left| A \right|$
>  2. any $\ell$ vertices in $U$ have at least $\left|H\right|$ common neighbors.
>  
>  Then, $H$ is contained in $G$.

^7f6399

> [!proof]-
> We first embed $A$ in $U$ anyway we want. Then, for $B=\{ v_{1},\dots,v_{b} \}$,  we can embed them in the order as follows. 
> 
> Any $N(v_{i})$ have at least $\left| H \right|$ common neighbors by assumption, there always exists a vertex that is not embedded yet.

^da9439

---
> [!lemma] Theorem 2
> $R(Q_{r})\leq 2^{3r}$ where $R$ denotes the [[Ramsey Number]].

^d2c90f

> [!proof]-
> In any two-coloring of the edges of the complete graph on $N:=2^{3r}$ vertices, the denser of the two colors has at least $\frac{1}{2}{N \choose 2}>2^{-7/3}N^{2}$ edges. Let $G$ be the graph of the denser color, so $d(G)\geq 2^{-4/3}N$. 
> 
> Let $t=\frac{3}{2}r, m=2^r$ and $a=2^{r-1}$. We have that: $$\frac{d(G)^t}{N^{t-1}}-{N \choose r}\frac{m^t}{N^t}\geq 2^{-4t/3}N-N^{r-t}m^t=2^{r}-2^{3r^{2}-2rt}=2^r-1\geq 2^{r-1}$$ Therefore, applying [[Graph|Lemma]] we find in $G$ a subset $U$ of size $2^{r-1}$ such that every set of $r$ vertices in $U$ has at least $2^r$ common neighbors. Since $Q_{r}$ is an $r$-regular bipartite graph with $2^r$ vertices and parts of size $2^{r-1}$, Lemma 1 demonstrates that $Q_{r}$ is a subgraph of $G$.
> 

^e87ba0

- **Conjecture**: $R(Q_{r})=O(2^r)$, i.e. it is linear in $n:=V(Q_{r})$.  ^c5ab08
---

