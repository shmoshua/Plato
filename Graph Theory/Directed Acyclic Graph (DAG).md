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

^ae6dfd

> [!proof]-
> We have that: $$\begin{aligned} \det M&=\sum_{\sigma\in S_{n}}^{}\text{sgn}(\sigma)\prod_{i\in[n]}^{}\left( \sum_{P:a_{i}\to b_{\sigma(i)}}^{} w(P)\right)\\&=\sum_{{\sigma\in S_{n}}}^{}\text{sgn}(\mathcal{\sigma})\sum_{P_{i}:a_{i}\to b_{\sigma(i)}}^{}\prod_{i}^{}w(P_{i})\\&=\sum_{\mathcal{P}}^{}\text{sgn}(\mathcal{P})w(\mathcal{P})\end{aligned}$$Therefore, it suffices to show that $\sum_{\mathcal{P}\in N}^{}\text{sgn}(\mathcal{P})w(\mathcal{P})=0$ where $N$ is the set of non vertex disjoint path systems. 
> 
> We define an involution $\pi:\mathcal{N}\to N$ as follows: Let $\mathcal{P}:=(P_{1},\dots,P_{n})\in N$. By definition some paths will intersect. 
> 1. Let $i_{0}$ be the minimal index s.t. $P_{i_{0}}$ shares some vertex with some other path.
> 2. Let $x$ be the first common vertex $P_{i_{0}}$ with some other path.
> 3. Let $j_{0}$ be the minimal index $i_{0}<j_{0}$ s.t. $P_{j_{0}}$ has $x$.
> 
> Then, we define $\pi \mathcal{P}:=(P'_{1},\dots,P_{n}')$ as follows: $P'_{i_{0}}$ and $P'_{j_{0}}$ are given by switching the paths at $x$ from $P_{i_{0}}$ and $P_{j_{0}}$ respectively. For every other index $P'_{i}:= P_{i}$. 
> 
> Notice that $\pi(\pi \mathcal{P}) =\mathcal{P}$ as $i_{0},x,j_{0}$ will be chosen the same for $\pi \mathcal{P}$. Also as $\pi \mathcal{P}$ and $\mathcal{P}$ use the same edges, $w(\pi \mathcal{P})=w(\mathcal{P})$. Lastly, we get that $\text{sgn}(\pi \mathcal{P})=-\text{sgn}(\mathcal{P})$ as the permutation for $\pi \mathcal{P}$ is mutliplied with a transposition from the permutation for $\mathcal{P}$.
> 
> Further, $\pi$ has no fixed point. Therefore, $\sum_{\mathcal{P}\in N}^{}\text{sgn}(\mathcal{P})w(\mathcal{P})=0$.

^fdc042
