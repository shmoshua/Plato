#GraphTheory #Definition 

> [!definition]
> A ***tournament*** $T_{n}$ is a [[Graph|digraph]] obtained by orienting the edges of the [[Clique]] $K_{n}$. 

^d0027e

- **Related definition**: A tournament $T_{n}$ has a ***$S_{k}$-property*** if for all $S\subseteq V(T_{n})$ with $\left| S \right|\leq k$, there is a vertex in $T_{n}$ that dominates all vertices in $S$, i.e. there exists $v\in T_{n}$ s.t. $u\to v$ for all $u\in S$. ^00613b
- **Related definition**: Let $T_{n}$ be a tournament on $[n]$ and $\pi:[n]\to[n]$ a permutation. An edge $i\to j$ is ***consistent*** if $\pi ^{-1}(i)<\pi ^{-1}(j)$.  ^81ade0
- **Related definition**: A tournament $T_{n}$ is ***strongly connected*** if for all $u,v$ there is a directed $uv$-path. ^e772b5
---
##### Properties
> [!lemma] Theorem 1 (Erdös)
> If $n\geq 3k^22^k$, then there exists a tournament $T_{n}$ with the $S_{k}$-property.

^7efafb

> [!proof]-
> Consider $K_{n}$ and we will orient the edges uniformly at random with probability $\frac{1}{2}$ independently. Then, let $S$ be a set of vertices with size $k$. For a fixed vertex $v\notin S$, $P(v\text{ dominates }S)=2^{-k}$. Then, for a fixed $S$, the probability that there is no vertex that dominates all vertices in $S$ is given by $(1-2^{-k})^{n-k}$. 
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
> 3. otherwise, there exists $1\leq i\leq n-2$ s.t. $v_{i}\to v$ and $v \to v_{i+1}$. Hence, $v_{1},\dots,v_{i},v,v_{i+1},\dots,v_{n-1}$ is a Hamiltonian path. 

^64e966

---
> [!lemma] Theorem 3 (Strongly Connectedness and Hamiltonicity)
> Let $T$ be a tournament. TFAE:
> 1. $T$ is strongly connected.
> 2. $T$ is Hamiltonian.

^1b4740

> [!proof]-
> We have that:
> 1. (1=>2): Suppose $T$ is not Hamiltonian. Let $C$ be a longest cycle in $T$ and let $v\notin C$. As $C$ is the longest cycle, for every consecutive vertices $u,u^+$ on $C$, we have that either $v\to u$ or $u^+ \to v$. Therefore, all edges from $C$ to $v$ go in only one direction. Wlog we may assume this is the case for every vertex not on $C$. 
>    
>    Let $A$ be the set of $v\notin C$ s.t. edges go from $v$ to $C$. Let $B$ be the set of $v\notin C$ s.t. edges go from $C$ to $v$. Then, if one of $A$ or $B$ are empty, then it follows that $T$ is not strongly connected. 
>    
>    Assume that $A,B$ are both non-empty. There is no edge oriented from a vertex $b\in B$ to $a\in A$. Indeed, otherwise, we can extend $x\to y$ in $C$ into $x \to b\to a \to y$. Therefore, $T$ is not strongly connected.
> 2. (2=>1): Obvious as from the Hamiltonian cycle we have a $uv$-path for every $u,v$.

^b57839

---
> [!lemma] Theorem 4 (Szelle, 1943)
> There exists a tournament $T_{n}$ on $n$ vertices with at least $\frac{n!}{2^{n-1}}$ Hamiltonian paths.

^2cfb3a

> [!proof]-
> Take a tournament $T_{n}$ uniformly randomly. Then, for any $x,y\in V$, $\mathbb{P}(x\to y)=\mathbb{P}(y\to x)= \frac{1}{2}$ independently. 
> 
> Let $\sigma\in S_{n}$. Then, let $P_{\sigma}$ be the path induced by the permutation. Therefore, $$\mathbb{P}(T_{n}\text{ has }P_{\sigma})=\frac{1}{2^{n-1}}$$Therefore, $\mathbb{E}[\#\text{Hamiltonian Paths}]=\sum_{\sigma\in S_{n}}^{}\mathbb{P}(T_{n}\text{ has }P_{\sigma})=\frac{n!}{2^{n-1}}$.

^8f29dd

---
> [!lemma] Theorem 5 (Alon)
> Let $P(n)$ be the maximal number of Hamiltonian paths $T_{n}$ can have. Then, 
> 1. $P(n)\leq (1+\text{o}(1))\frac{\sqrt{ \pi }}{\sqrt{ 2 }e}n^{3/2}\frac{n!}{2^{n-1}}$

^64c36c

> [!proof]-
> We will define a matrix $A\in \text{Mat}_{n,n}(\{ 0,1 \})$ where: $$A_{ij}=1 \iff i\to j\in T_{n}$$Then, there are precisely ${n \choose 2}$ 1s. Now, for $\sigma\in S_{n}$, $$\prod_{i=1}^{n}A_{i,\sigma(i)}=\begin{cases}1&i\to\sigma(i)\text{ for all }i\in[n]\\0&\text{otherwise}\end{cases}$$Therefore, $\prod_{i=1}^{n}A_{i,\sigma(i)}=1$ if and only if $\sigma$ defines a Hamiltonian cycle. This means that: $$\text{Per }A=\text{HC}(T_{n})$$where $\text{HC}(T_{n})$ denotes the number of hamitonian cycles in $T_{n}$. Therefore, by [[Permanent|Bregman]], $$\text{HC}(T_{n})\leq \prod_{i=1}^{n}(r_{i}!)^{1/r_{i}}$$where $r_{i}:=\sum_{j=1}^{n}A_{ij}$. As we know that $\sum_{i=1}^{n}r_{i}=n(n-1) /2$, by [[Technical Lemmas|Lemma 1]], we have that $\prod_{i=1}^{n}(r_{i}!)^{1/r_{i}}$ is maximal if $r_{i}$ is as equal as possible. Hence, $$\text{HC}(T_{n})\leq \prod_{i=1}^{n}\left( \left( \frac{n-1}{2} \right)! \right) ^{\frac{2}{n-1}}$$
> 
> 
> By Stirling's formula, we have that: $$(k!)^{1/k}\sim\frac{k}{e},\quad \frac{(2k)!}{(k!)^2}\sim\frac{2^{2k}}{\sqrt{ \pi k }}$$
> 1. if $n$ is odd, i.e. $n=2k+1$: $$\text{HC}(T_{n})\leq(k!)^{(2k+1)/k}\sim \frac{k}{e}(k!)^2\sim\frac{k}{e} \frac{(2k)!}{2^{2k}} \sqrt{ \pi k }\leq\frac{\sqrt{ \pi }}{\sqrt{ 2 }e}n^{3/2}\frac{(n-1)!}{2^n}$$
> 2. if $n$ is even, i.e. $n=2k$, then: $$\begin{align}\text{HC}(T_{n})&\leq (k!)^{k/k}((k-1)!)^{k/(k-1)}\sim (k!)\left( \frac{k-1}{e} \right)((k-1)!)\leq \frac{(k!)^2}{e}\\&\sim\frac{(2k)!}{2^{2k}}\frac{\sqrt{ \pi k }}{e}\leq \frac{\sqrt{ \pi  }}{\sqrt{ 2 e}}n^{3/2}\frac{(n-1)!}{2^n}\end{align} $$
> 
> Now, we prove the following claim: for any tournament $T$ on $n$ vertices, there exists a tournament $T'$ on $n+1$ vertices s.t. $\text{HC}(T')\geq P(T) / 4$.
> 
> Let $T$ be a tournament and let $v$ a new node. We will uniformly randomly orient the edges between $v$ and the rest of the graph. For any Hamiltonian path $P=v_{1},\dots,v_{n}$ in $T$, the probability that this extends to a Hamiltonian cycle in $T'$ is $1/4$, as we need that $v\to v_{1}$ and $v_{n}\to v$. Further, every Hamiltonian path gives rise to a different Hamiltonian cycle. Hence, $\mathbb{E}[\text{HC}(T')]=P(T) / 4$ and this proves the claim. 
> 
> Finally, we have that for any tournament $T$ on $n$ nodes: $$P(T)\leq 4\text{HC}(T')\leq (1+\text{o}(1))\frac{\sqrt{ \pi }}{\sqrt{ 2 }e}n^{3 / 2}\frac{n!}{2^{n-1}}$$This proves the claim for $P(n)$.

^9e37ff

---
###### Consistent Edges

> [!lemma] Theorem 1
> Let $T$ be a tournament on $[n]$ and let $T_{n}$ be a random tournament. Then, 랙:$$f(T):=\max_{\pi\in S_{n}}\left( \#\text{consistent edges}-\#\text{inconsistent edges} \right) $$
> 1. $f(T)\geq 0$
> 2. $f(T_{n})\leq O(n^{3/2}\sqrt{ \log n })$ with high probability. 
> 3. (de la Vega) $f(T_{n})\leq O(n^{3/2})$

^e5cad1

> [!proof]-
> We have that:
> 1. If $f(T)<0$ with maximum $\pi$, we have that the reverse ordering $\pi'$ turns all consistent edges to inconsistent and vice versa. Therefore, $f(T)>0$, which is a contradiction.
> 2. Let $X_{ij}$ be a random variable taking a value in $\{ -1,+1 \}$ where: $$X_{ij}=\begin{cases}+1&i\text{ is left to  }j \text{ in ordering }\pi\\-1&\text{otherwise}\end{cases}$$Therefore, we have by Chernoff, $$\mathbb{P}\left( \sum_{i,j}^{}X_{ij}\geq n^{3/2} \sqrt{ \log n } \right)\leq e^{-n^3\log n/n^2}=e^{-n\log n}$$Hence, $$\mathbb{P}\left( f(T_{n})\geq n^{3/2}\sqrt{ \log n } \right)\leq n! e^{-n\log n}\lesssim \left( \frac{n}{e} \right) ^n e^{-n\log n}=e^{-n}\to 0$$
> 3. Assume $n=2^k$. We will define a partition where: $$V_{i,j}:=\{ \pi(a):2^{k-i}(j-1)<a\leq 2^{k-i}j \}$$Then, $\bigcup_{j}^{}V_{i,j}=V$ for all $i$. Let $E_{i,j}$ be the edges between $V_{i,2j-1}$ and $V_{i,2j}$. Further, let $E_{i}:=\bigcup_{j=1}^{2^{i-1}}E_{i,j}$. Then, $$\left| E_{i} \right| =\sum_{j=1}^{2^{i-1}}\left| E_{i,j} \right| =2^{i-1}2^{2(k-i)}=2^{2k-i-1}=n^22^{-i-1}$$
>    
>    Let $X_{i}$ be the number of inconsistent edges in $E_{i}$. Then, by Chernoff, $$\mathbb{P}(X_{i}\geq n^{3/2}2^{-i/2}\sqrt{ i })\leq e^{-ni}$$Hence, $$\mathbb{P}\left( \sum_{i=1}^{k}X_{i}\geq n^{3/2}\sum_{i=1}^{k}2^{-i/2}\sqrt{ i } \right)\leq \sum_{i=1}^{k}e^{-ni}$$

^8ad1a0

