#Roadmap #GraphTheory

### 1. Graph Theory Basics
#### 1.1 Definitions

![[Graph#^ad9bfd]]

---
![[Graph Homomorphism#^46553c]]
![[Graph Homomorphism#^facdab]]

---
##### 1.1.1 Degree
![[Graph#^9e7f50]]
![[Graph#^c41238|q]]

---
![[Graph#^9b4417]]
![[Graph#^deb149|p]]

---
##### 1.1.2 Adjacency and Incidence Matrix
- **Related definition**: For a simple graph $G$, 
	1. the ***adjacency matrix*** of $G$ is a $\{ 0,1 \}$-matrix $(a_{uv})_{u,v\in V}$ given by $a_{uv}:=\mathbb{1}_{u\sim v}$.
	2. the ***incident matrix*** of $G$ is a $\{ 0,1 \}$-matrix $(b_{ve})_{v\in V,e\in E}$ given by $a_{ve}:=\mathbb{1}_{v\in e}$.
- **Remark**: As the adjacency matrix is a symmetric matrix, it admits a real [[spectrum]].

> [!lemma] Proposition 1
> Let $G$ be a simple graph. Let $A$ and $B$ be the adjacency and incident matrices of $G$. Then, $$BB^\top=\text{diag}(d(v_{1}),\dots,d(v_{n}))+A$$

> [!proof]-
> We have that: 
> 1. if $u=v$, we have: $$(BB^\top)_{uv}=\sum_{e\in E}^{}\mathbb{1}_{v\in e}=d(v)$$ and for $u\neq v$,  $$(BB^\top)_{uv}=\sum_{e\in E}^{}\mathbb{1}_{u,v\in e}=\mathbb{1}_{\{ u,v \}\in E}$$
---
##### 1.1.3 Subgraphs
![[Induced Graph#^834ef5]]

---
##### 1.1.4 Special Graphs
![[Graph#^0e6c3d]]

---
##### 1.1.5 Walks, Paths, Cycles
![[Walk#^84cbe5]]

---
![[Path (Graph)#^9274a2]]
![[Path (Graph)#^14b918]]
![[Path (Graph)#^150295|q]]

---
![[Path (Graph)#^82af28]]
![[Path (Graph)#^4d3705|p]]

---
![[Path (Graph)#^4e3ecc]]
![[Path (Graph)#^ccedf3|p]]
![[Path (Graph)#^590fcb]]

---
##### 1.1.6 Independence Number
![[Independence and Clique#^28742d]]
![[Independence and Clique#^01670d]]

---
![[Independence and Clique#^a259ae]]
![[Independence and Clique#^644b07|p]]

---
##### 1.1.7 Connectivity
![[Path (Graph)#^0c6bd0]]

---
![[Path (Graph)#^aec20e]]
![[Path (Graph)#^0d4367|p]]

---
### 2. Trees and Forests

![[Tree#^6a6272]]
![[Tree#^8551a4]]

---
![[Tree#^8ecefa]]
![[Tree#^cffecf|p]]

---
![[Tree#^481b12]]
![[Tree#^7a33da|p]]

---
![[Tree#^ce4662]]

---
![[Tree#^848d8c]]
![[Tree#^ded13e|p]]

---
#### 2.1 Cayley's Formula

> [!definition]
> Let $T$ be a [[tree]] on an ordered set $S$ of $n$ vertices. The ***Prüfer code*** $f(T)$ of $T$ is given by the following process:
> 1. iteratively delete the leaf with the smallest label
> 2. append the label of its neighbour to the sequence. 
> 3. After $n-2$ iterations a single edge remains and we have produced a sequence $f(T)$ of length $n-2$.

---
> [!lemma] Proposition 1
> Let $T$ be a tree and $f(T)$ the Prüfer code. 
> 1. $x\in T$ appears in $f(T)$ if and only if $x$ is not a leaf.

> [!proof]-
> If $x$ is a leaf, by construction $x$ cannot appear in $f(T)$.
> 
> Conversely, if $x$ is not a leaf, there exists $\{ u,v \}\subseteq N(x)$. As only leaves can be deleted, either $u$ or $v$ will be deleted before $x$. Hence, $x$ appears in $f(T)$.

---
> [!lemma] Theorem 2
> Let $S$ be an ordered set of $n$ vertices. The following map is a bijection: $$\{ \text{Trees on }S \}\to S^{n-2},\quad T\mapsto f(T)$$

> [!proof]-
> We prove this by induction over $n$. 
> 1. If $n=2$, then there exists only one tree on $S$ and this is uniquely given.
> 2. If $n\geq 3$, we know that $f(T)$ has length $n-2$ for all $f$. To show that it is a bijection, let $s_{1},\dots,s_{n-2}\in S$ be a sequence. 
>    
>    Let $s^{*}$ be the smallest element in $S$ s.t. it does not appear in $s_{1},\dots,s_{n-2}$. Then, by induction there exists a unique tree $T$ on $S \backslash \{ s^{*} \}$ s.t. $f(T)=(s_{2},\dots,s_{n-2})$. Now, consider $T':=T\cup \{ s^{*}s_{1} \}$. Then, $$f(T')=(s_{1},\dots,s_{n-2})$$Hence, there exists a unique tree $T'$ on $S$ with $f(T')=(s_{1},\dots,s_{n-2})$.
- **Corollary: (Cayley)** There are $n^{n-2}$ different labelled trees on $n$ vertices.
---
> [!lemma] Corollary 3 (Cayley's Formula)
> There are $n^{n-2}$ different labelled trees on $n$ vertices.

> [!proof]- Proof (Prüfer code)
> Follows from Theorem 2.

> [!proof]+ Proof (Joyal, 1981)
> Let $\mathcal{F}$ be a set of tuples $(T,\ell,r)$ where $T$ is a labelled tree on $n$ vertices and $\ell$ and $r$ are two vertices. Then, it suffices to show that: $$\left| \mathcal{F} \right| =n^n$$
> 
> Consider the digraph $G=(V,E)$ on $n$ vertices. 
