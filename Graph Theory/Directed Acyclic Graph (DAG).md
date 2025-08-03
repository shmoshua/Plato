#Definition #GraphTheory 

> [!definition]
> A ***DAG*** is a directed acyclic [[graph]].

---
##### Properties

> [!lemma] Theorem (Gessel-Viennot)
> Let $G$ be a weighted DAG and $A:=\{ a_{1},\dots,a_{n} \},B:=\{ b_{1},\dots,b_{n} \}\subseteq V(G)$. 
> 1. the ***path matrix*** $M$ is defined as $M_{ij}:=\sum_{P:a_{i}\to b_{j}} w(P)$ where $w(P):=\prod_{e\in P}^{}w(e)$.
> 2. a ***path system*** $\mathcal{P}$ from $A$ to $B$ is given by $\sigma\in S_{n}$ and $n$ paths $P_{i}:a_{i}\to b_{\sigma(i)}$ with $w(\mathcal{P}):=\prod_{i}^{}w(P_{i})$. Further, a path system $\mathcal{P}$ is ***vertex-disjoint*** if the paths are pairwise vertex disjoint. 
>  
>  Then, $$\det M=\sum_{\begin{array} \ \mathcal{P} \text{ vertex-disjoint}\\\text{path system}\end{array}}^{}\text{sgn}(\mathcal{P})w(\mathcal{P})$$
