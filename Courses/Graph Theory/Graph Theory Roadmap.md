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
- **Related definition**: An edge $e\in E$ is a ***cut edge*** if $G$ is connected and $G \backslash e$ is disconnected.

---
![[Path (Graph)#^9e5831]]
![[Path (Graph)#^bab021|p]]


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
![[k-Connected Graph#^02bda0]]
![[k-Connected Graph#^ad9edc|p]]
- **Remark**: If $G$ is $k$-connected, then there is no cut of size $\leq k-1$. Conversely, if there is a cut of size $k$, then $\kappa(G)\leq k$.
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
#### 3.1 2-Connected Graphs
![[k-Connected Graph#^28e12b]]
![[k-Connected Graph#^0c50c8|p]]

---
#### 3.2 Menger's Theorem
![[k-Connected Graph#^45540e]]
![[k-Connected Graph#^3f234e|p]]
![[k-Connected Graph#^ec2611]]

---
![[Line Graph#^d19d22]]

---
![[k-Connected Graph#^8d2396]]
![[k-Connected Graph#^e1a83d|p]]

---
![[k-Connected Graph#^8ee159]]
![[k-Connected Graph#^22c9c4|p]]

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
![[Hamiltonian Path#^7a36d1]]
![[Hamiltonian Path#^e3866f|p]]
![[Hamiltonian Path#^7fb646]]

---
![[Hamiltonian Path#^29e18f]]
![[Hamiltonian Path#^3f2859|p]]

---
##### 4.2.1 Tough Graphs
![[Tough Graph#^a45246]]

---
##### 4.2.2 Dirac's Theorem
![[Hamiltonian Path#^e8af36]]
![[Hamiltonian Path#^afd4a9|p]]

---
### 5. Matchings
![[Matching#^ba7938]]
![[Matching#^32ed75]]
![[Matching#^cf73c8|p]]
![[Matching#^3aa979|p]]

---
![[Matching#^ef41f6]]

---
#### 5.1 Vertex Cover

![[Vertex Cover#^63a2ab]]
![[Vertex Cover#^32ed75]]
![[Vertex Cover#^cf73c8|p]]

---
![[Vertex Cover#^fd5d85]]


---
![[Vertex Cover#^31a060]]
![[Vertex Cover#^5c6854|p]]

---
#### 5.2 Hall's Theorem
![[Matching#^cbfcfe]]
![[Matching#^f6ad99|p]]

---
![[Matching#^d7be1f]]
![[Matching#^4415a5|p]]

---
![[Matching#^2257d4]]
![[Matching#^002a60|p]]

---
![[Matching#^0988a7]]
![[Matching#^1c07c9|p]]

---
![[Vertex Cover#^c720dd]]
![[Vertex Cover#^c36b60|p]]


---
#### 5.3 Tutte's Theorem
![[Matching#^00d539]]
![[Matching#^9c3dcb|p]]

---
![[Matching#^267005]]
![[Matching#^0a251c|p]]

---
![[Matching#^6fe048]]
![[Matching#^af47cc|p]]

---
### 6. Planar Graphs
![[Planar Graph#^49eb13]]
![[Planar Graph#^06ee29]]

---
![[Euler Characteristic#^43d133]]
![[Euler Characteristic#^020d4e|p]]

---
![[Planar Graph#^f8d45e]]
![[Planar Graph#^227361|p]]
![[Planar Graph#^ec1ae0]]

---
### 7. Graph Colorings
#### 7.1 Vertex Colorings
![[Graph Coloring#^53c7b1]]
![[Graph Coloring#^ffa3f0]]
![[Graph Coloring#^ed777c|p]]
![[Graph Coloring#^e0f661|p]]

---
![[Graph Coloring#^abb949]]

---
![[Graph Coloring#^8d0143]]
![[Graph Coloring#^762596|p]]

---
#### 7.2 Greedy Coloring
![[Graph Coloring#^3e4dc5]]
![[Graph Coloring#^eac393|p]]

---
![[Degenerate Graph#^3c0f00]]
![[Degenerate Graph#^fc6ad2]]
![[Degenerate Graph#^014b1a|p]]

---
![[Degenerate Graph#^d1084b]]
![[Degenerate Graph#^94a402|p]]

---
![[Degenerate Graph#^8e8dc9]]
![[Degenerate Graph#^35abc8|p]]
![[Degenerate Graph#^fde1a9]]

---
![[Graph Coloring#^d683c4]]
![[Graph Coloring#^a331ec|p]]

---

#### 7.3 Coloring Planar Graphs
![[Degenerate Graph#^03cc32]]
![[Degenerate Graph#^d44b60|p]]
![[Degenerate Graph#^b5e633]]

---
![[Planar Graph#^cae3cc]]
![[Planar Graph#^daeea0|p]]
![[Planar Graph#^f3acf4]]

---

#### 7.4 The Art Gallery Theorem
![[Planar Graph#^85aaad]]
![[Planar Graph#^41a1fc|p]]

---
![[Planar Graph#^53547d]]
![[Planar Graph#^c8dc3b|p]]

---
#### 7.5 Gallai-Roy Theorem
![[Graph Coloring#^a4803a]]
![[Graph Coloring#^3f1e51|p]]

---
### 8. More Coloring Results
#### 8.1 Triangle-Free Graph with Large Chromatic Number
![[Graph Coloring#^5fba0a]]
![[Graph Coloring#^f0afbe|p]]

---
#### 8.2 Large Chromatic Number and Large Girth
![[Girth and Circumference#^4ba9e0]]
![[Girth and Circumference#^819748|p]]

---
#### 8.3 Chromatic Number and Clique Minors
![[Minor#^62cd1d]]

---
![[Minor#^6747a7]]
![[Minor#^85861b|p]]

---
#### 8.4 Edge Colorings
![[Graph Coloring#^53c7b1]]
![[Graph Coloring#^ee3771]]
![[Line Graph#^fede6a|p]]


---
![[Graph Coloring#^b7f423]]
![[Graph Coloring#^b563b6|p]]

---
![[Graph Coloring#^41f7e8]]
![[Graph Coloring#^a8a1c7|p]]

---

#### 8.5 List Coloring
![[List Coloring#^5f6b51]]
![[List Coloring#^a18db3]]

---
![[List Coloring#^9f9f8b]]
![[List Coloring#^f2813a|p]]

---
![[List Coloring#^5be692]]
![[List Coloring#^b06959|p]]
![[List Coloring#^f50ba4]]

---
![[Kernel (Graph Theory)#^026183]]
![[Kernel (Graph Theory)#^5edd07]]

---
![[Kernel (Graph Theory)#^5a90a3]]
![[Kernel (Graph Theory)#^0338c7|p]]

---
![[List Coloring#^3dac14]]
![[List Coloring#^f0574e|p]]

---
### 9. The Matrix Tree Theorem
#### 9.1 Lattice Paths and Determinants
![[Directed Acyclic Graph (DAG)#^ae6dfd]]
![[Directed Acyclic Graph (DAG)#^fdc042|p]]

---
![[Determinant#^cdfa8e]]
![[Determinant#^23ad94|p]]

---
#### 9.2 The Matrix Tree Theorem
![[Tree#^cc4b3d]]
![[Tree#^b01695|p]]

---
![[Tree#^5bf805]]
![[Tree#^435330|p]]

---
### 10. More Theorems on Hamiltonicity

#### 10.1 Graph Closure
![[Closure (Graph Theory)#^56af79]]

---
![[Closure (Graph Theory)#^0d8c43]]
![[Closure (Graph Theory)#^2e374d|p]]

---
![[Closure (Graph Theory)#^654eca]]
![[Closure (Graph Theory)#^d75485|p]]

---
![[Closure (Graph Theory)#^b0e3a6]]
![[Closure (Graph Theory)#^070269|p]]

---
![[Closure (Graph Theory)#^3ed9fa]]
![[Closure (Graph Theory)#^b220de|p]]

---
#### 10.2 Pósa's Lemma

![[Path (Graph)#^c5ca8a]]
![[Path (Graph)#^276eab|p]]

---
![[Path (Graph)#^821639]]
![[Path (Graph)#^6f796d|p]]


---
#### 10.3 Tournaments
![[Tournament#^d0027e]]
![[Tournament#^e772b5]]

---
![[Tournament#^d5682b]]
![[Tournament#^64e966|p]]

---
![[Tournament#^1b4740]]
![[Tournament#^b57839|p]]

---
### 11. Ramsey Theory
![[Ramsey Number#^bf6551]]

---
![[Ramsey Number#^ba602f]]
![[Ramsey Number#^13672b|p]]

---
![[Ramsey Number#^5ce7f6]]
![[Ramsey Number#^3cf037|p]]

---
![[Ramsey Number#^6540ef]]
![[Ramsey Number#^ad1c73|p]]

---
![[Ramsey Number#^fc3c57]]
![[Ramsey Number#^788618|p]]

---
#### 11.1 Bounds on Ramsey Number
![[Ramsey Number#^0bfef8]]
![[Ramsey Number#^9fbe8f|p]]

---
![[Ramsey Number#^acc2ba]]
![[Ramsey Number#^5c6e81|p]]

---
#### 11.2 Ramsey Theory for Integers
![[Ramsey Number#^7dab71]]
![[Ramsey Number#^e32306|p]]

---
#### 11.3 Graph Ramsey Numbers
![[Ramsey Number#^9a3af2]]

---
![[Ramsey Number#^ea67e3]]
![[Ramsey Number#^e96d61|p]]

---
### 12. Extremal Graph Theory
