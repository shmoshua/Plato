#ProbabilisticMethods #Roadmap 

### 1. The Basics
#### 1.1 Ramsey Numbers

![[Ramsey Number#^bf6551]]

---
![[Ramsey Number#^ba602f]]
![[Ramsey Number#^13672b|p]]

---
![[Ramsey Number#^5ce7f6]]
![[Ramsey Number#^3cf037|p]]
![[Ramsey Number#^8e9a7c|q]]

---
![[Ramsey Number#^0bfef8]]
![[Ramsey Number#^9fbe8f|p]]

---
#### 1.2 Tournaments

![[Tournament#^d0027e]]
![[Tournament#^00613b|q]]
---
![[Tournament#^7efafb]]
![[Tournament#^67a465|p]]
---

![[Hypergraph#^9201b6]]
![[Hypergraph#^76aa99|q]]
![[Hypergraph#^edbb24|q]]
![[Hypergraph#^fd7276|q]]
![[Hypergraph#^68e4e2|q]]

---
![[Hypergraph#^3327ed]]

---
![[Hypergraph#^ce5313]]
![[Hypergraph#^f29f34|p]]
![[Hypergraph#^16c0c2|q]]
---

> [!lemma] Theorem 2 (Bollobás)
$(A_{i},B_{i})$ where $1\leq i\leq m$ where $\left| A_{i} \right|=a$ and $\left| B_{i} \right|=b$ s.t. $A_{i}\cap B_{i}=\varnothing$ and $A_{i}\cap B_{j}\neq \varnothing$ for $i\neq j$.  Then, $m\leq{a+b \choose a}$

> [!proof]-
> Let $X:=\bigcup_{i}^{}A_{i}\cup B_{i}$ and put an order on $X$ randomly. Then, we define the event $E_{i}$ as the event where all elements of $A_{i}$ happens before $B_{j}$.  Then, 
> 1. **Claim 1: $E_{i}$ are disjoint.**
>    Suppose $E_{i}$ is true. Then, $A_{i}$ happens before $B_{i}$. However, $A_{j}$ intersects $B_{i}$ and $B_{j}$ intersects $A_{i}$. Therefore, it cannot happen that $A_{j}$ all happens before $B_{j}$.  
> 
> Then, we have that: $$\mathbb{P}(E_{i})=\frac{ a !b !}{a+b!}={a+b \choose a}^{-1}$$Therefore, by the disjointness, $$1\geq \sum_{i=1}^{m}\mathbb{P}(E_{i})=\frac{m}{a+b \choose a}$$
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
![[Sum-Free Set#^68b7e6|q]]

---
### 3. Methods of Alteration

##### 3.1 High Girth and High Chromatic Number
![[Girth#^803604]]

---
![[Girth#^4ba9e0]]
![[Girth#^819748|p]]

---
##### 3.2 Non-2-colorable $k$-uniform Hypergraphs
![[Hypergraph#^cbd750]]
![[Hypergraph#^a8679e|p]]
---
##### 3.3 Dependent Random Choice
![[Ramsey Number#^bf6551]]
