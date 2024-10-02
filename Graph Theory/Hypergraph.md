#Definition #GraphTheory 

> [!definition]
> A ***hypergraph*** $G=(V,E)$ is a set of vertices $V$ with a set of edges $E$ where every edge is a subset of $V$. 

^9201b6

- **Related definition**: A hypergraph $(V,E)$ is ***$k$-uniform*** if $\left| e \right|=k$ for all $e\in E$. ^76aa99
- **Remark**: A standard graph is a $2$-uniform hypergraph. ^edbb24
- **Related definition**: A $k$-coloring of the vertices of a hypergraph $G$ is called ***proper***, if no edge in $G$ is monochromatic. ^fd7276
- **Related definition**: $m(k)$ is the smallest integer $m$ s.t. there exists a $k$-uniform hypergraph with $m$ edges for which there is no proper 2-coloring. ^68e4e2
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $m(2)=3$
> 2. for $k\geq 2$, $2$-colorability is NP-complete.

^3327ed

---
> [!lemma] Proposition 2 (Erdös)
> $2^{k-1}< m(k)\leq ck^{2}2^k$ for some large constant $c>0$.

^ce5313

> [!proof]-
> We have that:
> 1. (Lower bound) Let $m\leq 2^{k-1}$ and $G=(V,E)$ be a $k$-uniform hypergraph with $m$ edges. Let us color its vertices uniformly at random with 2 colors. For an edge $e\in E$, let $A_{e}$ denote the event that $e$ is monochromatic. Then, we have that $\mathbb{P}(A_{e})=2\cdot 2^{-k}$. Therefore, $$\mathbb{P}(\exists \text{monochromatic edge})=\mathbb{P}\left( \bigcup_{e\in E}^{} A_{e}\right)< m\cdot 2\cdot 2^{-k} =\frac{m}{2^{k-1}}$$where the last inequality is strict as there are events that are not disjoint. Therefore, there exists a monochromatic edge with probability $<1$. 
> 2. (Upper bound) We may assume that $k\geq 10$, because we can easily choose a constant $c$ so that $m(k)\leq ck^{2} 2^k$ holds for all $k<10$. Now, we will find a $k$-uniform hypergraph with $m=3k^22^k$ edges which is not 2-colorable. 
>    
>    Let $V:=[k^2]$ and we draw $m$ $k$-element subsets of $V$ with repetitions. Then, fix any 2-coloring on $G$. Then, there exists a subset of vertices of size at least $k^2 /2$ with the same color. The probability that a randomly chosen subset of size $k$ is contained in this subset is: $$\begin{align} \frac{{k^2/2 \choose k}}{k^{2} \choose k}=\prod_{i=0}^{k-1} \frac{\frac{k^2}{2}-i}{k^2-i}&=\frac{1}{2^k}\prod_{i=0}^{k-1} \frac{k^2-2i}{k^2-i}=\frac{1}{2^k}\prod_{i=0}^{k-1} \left( 1-\frac{i}{k^2-i} \right)\\&>\frac{1}{2^k}\prod_{i=0}^{k-1}\exp \left( -\frac{2i}{k^2-i} \right)  >\frac{1}{2^k}\exp \left( -\frac{2\sum_{i=0}^{k-1}i}{k^2-k} \right)  =2^{-k}e^{-1}\end{align}$$Therefore, the probability that an edge is not monochromatic is at most $1-2^{-k}e^{-1}$ and the probability that none of them are monochromatic is at most: $$(1-2^{-k}e^{-1})^m\leq \exp \left( -\frac{m}{e 2^k} \right) <e^{-k^{2}}$$Using this a union bound over all coverings $V(G)$, we get that the probability that there is a proper coloring is at most $e^{-k^{2}}2^{k^2}<1$, so there exists a hypergraph with $m$ edges with no proper 2-coloring.

^f29f34

- **Remark**: The best known lower bound is $c\sqrt{ k / \log k } \cdot 2^k\leq m(k)$. ^16c0c2
---
> [!lemma] Theorem 3
> $2^{k-2}\sqrt{ \frac{k}{\log k} }\leq m(k)$ 

> [!proof]+
> Let $H:=(V,E)$ be a $k$-uniform hypergraph. Then, for every $v\in V$, we draw $x_{v} \sim \mathcal{U}([0,1])$ and sort the vertices into $v_{1},\dots,v_{n}$. We follow the algorithm: 
> 1. Color $v$ red whenever possible.
> 2. Color $v$ blue if coloring $v$ red would make some edge incident to $v$ monochromatic red.
>   
> Notice that by construction we have no blue edge. Assume there exists a blue edge. Then, on the first node in the blue edge, a ***conflicting pair*** is a pair of the edge it would have given a monochromatic red and the blue edge. Therefore, for any blue edge a conflicting pair exists and conversely, absence of a conflicting pair would imply that $H$ is $2$-colorable.
> 
> Let $R:=\left[ 0, \frac{1-p}{2} \right]$, $P:=\left[ \frac{1-p}{2},\frac{1+p}{2} \right]$, $B=\left[ \frac{1+p}{2},1 \right]$
> 1. **Claim 1**: $\mathbb{P}(\exists e\in E:x_{v}\in R, \text{for all }v\in e)=\left( \frac{1-p}{2} \right)^k=2^{-k}(1-p)^k\leq 2^{-k}e^{-pk}$
> 2. **Claim 2**: $\mathbb{P}(\exists e\in E:x_{v}\in B, \text{for all }v\in e)\leq 2^{-k}e^{-pk}$ by symmetry.
>    
>  Now, let $(e,f)$ be a conflicting pair on node $v$. Then, $$\begin{align}\mathbb{P}((e,f))\end{align}$$
>    