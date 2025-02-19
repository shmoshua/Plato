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