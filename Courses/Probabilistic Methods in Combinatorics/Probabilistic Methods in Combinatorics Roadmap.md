#Combinatorics #Roadmap 

### 1. The Basics
#### 1.1 Ramsey Numbers

![[Ramsey Number#^bf6551]]
![[Ramsey Number#^610a32]]

---
![[Ramsey Number#^ba602f]]
![[Ramsey Number#^13672b|p]]

---
![[Ramsey Number#^5ce7f6]]
![[Ramsey Number#^3cf037|p]]
![[Ramsey Number#^8e9a7c]]

---
![[Ramsey Number#^0bfef8]]
![[Ramsey Number#^9fbe8f|p]]

---
#### 1.2 Tournaments

![[Tournament#^d0027e]]
![[Tournament#^00613b]]

---
![[Tournament#^7efafb]]
![[Tournament#^67a465|p]]

---
#### 1.3 Hypergraph Coloring

![[Hypergraph#^9201b6]]
![[Hypergraph#^76aa99]]
![[Hypergraph#^edbb24|q]]
![[Hypergraph#^fd7276|q]]
![[Hypergraph#^68e4e2|q]]

---
![[Hypergraph#^3327ed]]
![[Hypergraph#^4bb28b|p]]

---
![[Hypergraph#^ce5313]]
![[Hypergraph#^f29f34|p]]
![[Hypergraph#^16c0c2]]

---

> [!lemma] Theorem 2 (Bollobás)
> Let $(A_{i},B_{i})$ be a family of pair of sets for $i\in[m]$ and $a,b\in \mathbb{Z}_{\geq 0}$ s.t.
> 1. $\left| A_{i} \right|=a$ and 
> 2. $\left| B_{i} \right|=b$ and
> 3. $A_{i}\cap B_{i}=\varnothing$ and $A_{i}\cap B_{j}\neq \varnothing$ for $i\neq j$.  
> 
> Then, $m\leq{a+b \choose a}$.

> [!proof]-
> Let $X:=\bigcup_{i}^{}A_{i}\cup B_{i}$ and put an order on $X$ randomly. Then, we define the event $E_{i}$ as the event where all elements of $A_{i}$ happens before $B_{j}$.  Then, 
> 1. **Claim 1: $E_{i}$ are disjoint.**
>    Suppose $E_{i}$ is true. Then, $A_{i}$ happens before $B_{i}$. However, $A_{j}$ intersects $B_{i}$ and $B_{j}$ intersects $A_{i}$. Therefore, it cannot happen that $A_{j}$ all happens before $B_{j}$ for any $j\neq i$.
> 
> Then, we have that: $$\mathbb{P}(E_{i})=\frac{ a !b !}{(a+b)!}={a+b \choose a}^{-1}$$Therefore, by the disjointness, $$1\geq \sum_{i=1}^{m}\mathbb{P}(E_{i})=\frac{m}{a+b \choose a}$$
- **Remark**: By considering $[a+b]$ as the ground set and choosing $A_{i}$ as the subsets ${a+b \choose a}$ and $B_i$ as the complement of $A_{i}$. Then, $\max m\geq {a+b \choose a}$.
---
### 2. Linearity of Expectation
#### 2.1 Max-Cut
![[Cut (Graph)#^27b1e1]]

![[Cut (Graph)#^b245ae]]
![[Cut (Graph)#^b83c9a|p]]

---
#### 2.2 Tournaments and Hamiltonian Path
![[Hamiltonian Path#^a7fcdb]]

---
![[Tournament#^d5682b]]
![[Tournament#^64e966|p]]

---
![[Tournament#^2cfb3a]]
![[Tournament#^8f29dd|p]]

---
#### 2.3 Combinatorial Number Theory
##### 2.3.1 Sum-Free Sets.
![[Sum-Free Set#^a38971]]

---
![[Sum-Free Set#^ae3312]]
![[Sum-Free Set#^c6f226|p]]
![[Sum-Free Set#^68b7e6]]

---
### 3. Permanents
![[Permanent#^cc906b]]
![[Permanent#^7904f8]]
![[Permanent#^f4f2dc|p]]

---
![[Permanent#^530cc3]]
![[Permanent#^63071a|p]]

---
![[Permanent#^eefbb0]]
![[Permanent#^a1cd36|p]]

---
![[Tournament#^64c36c]]
![[Tournament#^9e37ff|p]]

---

### 4. Methods of Alteration
##### 4.1 Dominating Set
> [!definition]
> For a graph $G$, $S\subseteq V(G)$ is called a ***dominating set*** if:
> 1. for all 

##### 4.2 High Girth and High Chromatic Number
![[Girth and Circumference#^803604]]

---
![[Girth and Circumference#^4ba9e0]]
![[Girth and Circumference#^819748|p]]

---
##### 4.3 Non-2-colorable $k$-uniform Hypergraphs
![[Hypergraph#^cbd750]]
![[Hypergraph#^a8679e|p]]

---
#### 4.4 Dependent Random Choice
![[Ramsey Number#^bf6551]]

---
##### 4.4.1 Ramsey Number of Hypercube

![[Hypercube (Graph)#^0ce392]]
![[Hypercube (Graph)#^6fb7b0|q]]

---
![[Hypercube (Graph)#^7f6399]]
![[Hypercube (Graph)#^da9439|p]]

---
![[Graph#^07cd66]]
![[Graph#^9e183d|p]]

---
![[Hypercube (Graph)#^d2c90f]]
![[Hypercube (Graph)#^e87ba0|p]]
![[Hypercube (Graph)#^c5ab08|q]]

---
