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
![[Tree#^7e2ec4]]

---
![[Tree#^97eff3]]
![[Tree#^0b054b|p]]

---
![[Tree#^fa0d83]]
![[Tree#^6c8dad|p]]

---
![[Tree#^5bf805]]
![[Tree#^8ff773|p]]
![[Tree#^1fd061|p]]

---
### 3. Connectivity
![[k-Connected Graph#^203f06]]
![[k-Connected Graph#^cc03cf]]

---
![[k-Connected Graph#^4e811f]]
![[k-Connected Graph#^049821|p]]

---
![[k-Connected Graph#^b902c3]]
![[k-Connected Graph#^d93829|p]]

---
![[k-Connected Graph#^dd00c3]]
![[k-Connected Graph#^ab76d0|p]]

---
### 4. Eulerian Tours and Hamiltonian Cycles

#### 4.1 Eulerian Tours and Eulerian Trails
![[Eulerian Trail#^af172c]]

---
![[Eulerian Trail#^bb32a6]]
![[Eulerian Trail#^bdc3a8|p]]

---
![[Eulerian Trail#^b2ca6d]]
![[Eulerian Trail#^59ce63|p]]

---
#### 4.2 Hamiltonian Paths and Hamiltonian Cycles
![[Hamiltonian Path#^a7fcdb]]

---
