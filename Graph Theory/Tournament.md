#GraphTheory #Definition 

> [!definition]
> A ***tournament*** $T_{n}$ is a directed graph obtained by orienting the edges of the [[complete graph]] $K_{n}$. 

^d0027e

- **Related definition**: A tournament $T_{n}$ has a ***$S_{k}$-property*** if for all $S\subseteq V(T_{n})$ with $\left| S \right|= k$, there is a vertex in $T_{n}$ that dominates all vertices in $S$.  ^00613b
---
##### Properties
> [!lemma] Theorem 1 (Erdös)
> If $n\geq 3k^22^k$, then there exists a tournament $T_{n}$ with the $S_{k}$-property.

^7efafb

> [!proof]-
> Consider $K_{n}$ and we will orient the edges uniformly independently at random with probability $\frac{1}{2}$. Then, let $S$ be a set of vertices with size $k$. For a fixed vertex $v\notin S$, $P(v\text{ dominates }S)=2^{-k}$. Then, for a fixed $S$, the probability that there is no vertex that dominates all vertices in $S$ is given by $(1-2^{-k})^{n-k}$. 
> 
> Since there are $n \choose k$ such sets $S$, $$P(\exists S\text{ not dominated}) \leq {n \choose k}(1-2^{-k})^{n-k}\leq n^ke^{-(n-k)/2^k}=e^{k\ln n-(n-k) / 2^k}<1$$

^67a465

---
> [!lemma] Proposition 2 (Hamiltonian Paths)
> Let $T_{n}$ be a tournament. 
> 1. $T_{n}$ has a Hamiltonian path.

^d5682b

> [!proof]-
> We prove this by induction. For $n=1$ it is clear. For $n>1$, choose $v\in V(T_{n})$ and we acquire from induction that there exists a Hamiltonian path $v_{1},\dots,v_{n-1}$in $T_{n} \backslash\{ v \}$.  Now, 
> 1. if $v\to v_{1}$, then $v,v_{1},\dots,v_{n-1}$ is a Hamiltonian path.
> 2. if $v_{n-1}\to v$, then $v_{1},\dots,v_{n-1},v$ is a Hamiltonian path.
> 3. 

^64e966

---
> [!lemma] Theorem 3 (Szelle, 1943)
> There exists a tournament $T_{n}$ on $n$ vertices with at least $\frac{n!}{2^{n-1}}$ Hamiltonian paths.

^2cfb3a

> [!proof]-
> Take a tournament $T_{n}$ uniformly randomly. Then, for any $x,y\in V$, $\mathbb{P}(x\to y)=\mathbb{P}(y\to x)= \frac{1}{2}$ independently. 
> 
> Let $\sigma\in S_{n}$. Then, let $P_{\sigma}$ be the path induced by the permutation. Therefore, $$\mathbb{P}(T_{n}\text{ has }P_{\sigma})=\frac{1}{2^{n-1}}$$Therefore, $\mathbb{E}[\#\text{Hamiltonian Paths}]=\sum_{\sigma\in S_{n}}^{}\mathbb{P}(T_{n}\text{ has }P_{\sigma})=\frac{n!}{2^{n-1}}$.

^8f29dd

---
> [!lemma] Theorem 4 (Alon)
> Let $P(n)$ be the maximal number of Hamiltonian paths $T_{n}$ can have. Then, 
> 1. $P(n)\leq cn^{3/2}\frac{n!}{2^{n-1}}$
> 