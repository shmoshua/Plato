#Algorithms #Roadmap 

### 1. Basics of Approximation Algorithms

![[Approximation Algorithm#^b7dd2f]]

---

#### 1.1 Greedy Algorithms
##### 1.1.1 Minimum Set Cover
![[Minimum Set Cover#^2ed1e3]]
![[Minimum Set Cover#^0eb03c|q]]

---
![[Minimum Set Cover#^eb92be]]
![[Minimum Set Cover#^d320dd|p]]
![[Minimum Set Cover#^4d9187|q]]

---
#### 1.2 Approximation Schemes

##### 1.2.1 PTAS and FPTAS

![[PTAS#^968d36]]

---
![[FPTAS#^a99681]]

---
##### 1.2.2 Knapsack

![[Knapsack#^fca662]]
- **Related notation**: In ILP it can be written as: 
  $$\begin{array}{rl}\text{max}&\sum_{i\in [n]}^{}p_{i}x_{i}\\\text{subject to}&\sum_{i\in[n]}^{} s_{i}x_{i}\leq B\\&x_{i}\in \{ 0,1 \}&\forall i\in[n]\end{array}$$
- **Remark**: As any $i\in [n]$ with $s_{i}>B$ cannot be chosen, wlog we assume that $s_{i}\leq B$.  
- **Remark**: It is clear that $\max_{i}p_{i}\leq p(\text{OPT}(I))\leq n\cdot \max_{i}p_{i}$. 
---
![[Knapsack#^13ab4a]]
![[Knapsack#^f19e50|p]]

---
![[Knapsack#^532344]]
![[Knapsack#^c811f3|p]]


---
##### 1.2.3 Bin-Packing
![[Bin Packing#^06f901]]
![[Bin Packing#^d65196|q]]
![[Bin Packing#^a84502|q]]
---
![[Bin Packing#^769d08]]
![[Bin Packing#^db3116|p]]
---
![[Bin Packing#^c04d44]]
![[Bin Packing#^3e5c2c|p]]
---
![[Bin Packing#^62d5f8]]
![[Bin Packing#^5e1d26|p]]

---
![[Bin Packing#^cb3b26]]
![[Bin Packing#^697fb8|p]]

---
![[Bin Packing#^58af47]]
![[Bin Packing#^4776b1|p]]

---
#### 1.3 Randomized Approximation Schemes

##### 1.3.1 PRAS and FPRAS

![[PRAS#^fecdc3]]
![[FPRAS#^a1e36b|p]]

---
![[PRAS#^7bca5c]]
![[PRAS#^9346bc|p]]

---
![[PRAS#^858f88]]
![[PRAS#^bf590a|p]]

---
##### 1.3.2 DNF Counting

![[DNF Counting#^d2f429]]
![[DNF Counting#^684725|q]]

---
![[DNF Counting#^44eec7]]
![[DNF Counting#^600789|p]]

---
![[DNF Counting#^8222ce]]

---
#### 1.4 Rounding Linear Programming Solutions
![[Linear Programming#^4d8220|q]]

---
##### 1.4.1 Minimum Vertex Cover
![[Minimum Vertex Cover#^37c645]]

- **Remark**: In ILP, the problem can be formulated as: $$\begin{array}{rl}\text{min}&\sum_{v\in V}x_{v}c_{v}\\\text{subject to}&x_{u}+x_{v}=1&\forall \{ u,v \}\in E\\&x_{v}\in \{ 0,1 \}&\forall v\in V\end{array}$$

---
![[Minimum Vertex Cover#^bfb726]]
![[Minimum Vertex Cover#^af947a|p]]

---
##### 1.4.2 Minimum Set Cover
![[Minimum Set Cover#^2ed1e3]]

---
![[Minimum Set Cover#^e18582]]
![[Minimum Set Cover#^20f82b|p]]

---
##### 1.4.3 Minimum Congestion Multi-Commodity Routing Problem
![[Multi-Commodity Routing#^986c64]]

---
![[Multi-Commodity Routing#^f82556]]
![[Multi-Commodity Routing#^d49992|p]]

---
![[Multi-Commodity Routing#^1afa3b]]

---
### 2. Online Algorithms and Competitive Analysis
#### 2.1 Online Algorithms
![[Competitive Online Algorithm#^9352d2]]

---
##### 2.1.1 Ski Rental Problem
> [!outlook] Ski Rental Problem
> For $k\in \mathbb{Z}_{> 1}$, let $1$ be the cost for renting a ski one day and $k$ for buying.a ski. When we don't know how many days we are going to ski, what is our strategy?
> 1. Consider renting for $k$ days and buying the ski after. 
> 2. Let $D$ be the number of days (which is unknown). We have that: 
> 	1. if $D\leq k$, then the cost is $D$ whereas the optimal cost in hindsight is $D$.
> 	2. if $D> k$, then the cost is $2k$ whereas the optimal cost in hindsight is $k$.
> 
> Therefore, we have a $2$-competitive online algorithm.
---
##### 2.1.2 Paging Problem
![[Paging#^8651de]]
![[Paging#^8c42a1|q]]

---
![[Paging#^7371ed]]
![[Paging#^0e131a|p]]

---
![[Paging#^4e0de5]]
![[Paging#^547661|p]]

---
![[Paging#^0ffb3f]]
![[Paging#^7391c2|p]]

---

![[Paging#^d6ecda]]
![[Paging#^9aa545|p]]

---
### 3. Hashing, Streaming and Sparsification

#### 3.1 Advanced Hashing Algorithms

![[k-wise Independent Hash Function#^a7c7d2]]
![[k-wise Independent Hash Function#^c24dfd|q]]

---
![[k-wise Independent Hash Function#^8f5cf5]]
![[k-wise Independent Hash Function#^e73efd|p]]

---
![[k-wise Independent Hash Function#^01f92a]]
![[k-wise Independent Hash Function#^8cb2fe|p]]

---
![[k-wise Independent Hash Function#^43fcd1]]
![[k-wise Independent Hash Function#^cf7bff|p]]

---
##### 3.1.1 Linear Probing

![[Linear Probing#^ccfb2c]]

---
![[Moment#^7763b9]]
![[Moment#^9da4fc|p]]

---


![[Linear Probing#^279bcf]]
![[Linear Probing#^2204d7|p]]

---

#### 3.2 Streaming Algorithms: Frequency Moments

![[Streaming Algorithm#^b3edf5]]
![[Streaming Algorithm#^5e97b2|q]]

---
![[Streaming Algorithm#^38b8d5]]
![[Streaming Algorithm#^eb91b6|p]]

---
![[Streaming Algorithm#^c2b6ca]]
![[Streaming Algorithm#^8eb98b|p]]

---
##### 3.2.1 Estimating the First Moment of the Stream
![[Streaming Algorithm#^9a34f6]]
![[Streaming Algorithm#^1f7d2d|p]]
![[Streaming Algorithm#^39fa84|q]]

---
##### 3.2.2 Estimating the Zeroth Moment of the Stream
![[Streaming Algorithm#^399e1c]]
![[Streaming Algorithm#^894eb0|p]]
![[Streaming Algorithm#^001d15|q]]
---
![[Streaming Algorithm#^273243]]
![[Streaming Algorithm#^4ea1a3|p]]
![[Streaming Algorithm#^a9914b|q]]

---
##### 3.2.3 Estimating the 2nd Moment of the Stream
![[Streaming Algorithm#^f94d70]]
![[Streaming Algorithm#^f15f0b|p]]
![[Streaming Algorithm#^90acce|q]]

---
#### 3.3 Streaming Algorithms: Graph Connectivity
##### 3.3.1 Finding a Single Cut Edge
![[Streaming Algorithm#^f050f5]]
![[Streaming Algorithm#^4ba20e|p]]

---
![[Streaming Algorithm#^0918e4]]
![[Streaming Algorithm#^533710|p]]
![[Streaming Algorithm#^7ce55e|q]]

---
![[Streaming Algorithm#^88bddb]]
![[Streaming Algorithm#^50642b|p]]
![[Streaming Algorithm#^511eae|q]]

---
#### 3.4 Graph Sparsification: Preserving Distances and Cuts
##### 3.4.1 Distance Preserving Sparsifiers
![[Spanner#^c6a9ed]]

---

![[Spanner#^1b3b1b]]
![[Spanner#^20abf3|p]]

---
![[Girth and Circumference#^cc9933]]
![[Girth and Circumference#^dd797b|p]]

---
##### 3.4.2 Cut Preserving Sparsifiers
![[Cut Sparsifier#^31fd8c]]

---
![[Cut Sparsifier#^2b64cc]]
![[Cut Sparsifier#^7e47a0|p]]

---
###### 3.4.2.1 Expanders
![[Expander#^fb21f9]]
![[Expander#^7eada3|q]]
![[Expander#^477930|q]]

---
![[Expander#^807967]]
![[Expander#^11188b|p]]

---
![[Expander#^652214]]
![[Expander#^66131c|p]]

---
![[Expander#^c0d48a]]
![[Expander#^2b6c8c|p]]
![[Expander#^b7104c|q]]

---
![[Expander#^7b2b27]]
![[Expander#^4eea47|p]]

---
![[Expander#^f5340c]]

---
![[Expander#^edc1f0]]

---
![[Expander#^8a9e7c]]
![[Expander#^21d1d7|p]]

---
![[Cut Sparsifier#^1b4fab]]
![[Cut Sparsifier#^1855a6|p]]

---
![[Cut Sparsifier#^aa67f0]]
![[Cut Sparsifier#^b5e439|p]]

---
### 4 Selected Topics in Approximation Algorithms
#### 4.1 Distance Preserving Tree Embeddings
![[Tree Embedding#^4915f3]]

---
![[Tree Embedding#^15e851]]
![[Tree Embedding#^a6ffa8|p]]

---
![[Tree Embedding#^639521]]
![[Tree Embedding#^39ea03|p]]

---
![[Tree Embedding#^92e278]]
![[Tree Embedding#^b4c3c8|p]]

---
##### 4.1.2 Buy-At-Bulk Network Design
![[Buy-At-Bulk Network Design#^a1f6f3]]

---
![[Buy-At-Bulk Network Design#^2e1b3e]]

---
#### 4.2 L1 Metric Embeddings
##### 4.2.1 Sparsest Cut
![[Sparsest Cut#^02a58c]]
![[Sparsest Cut#^9966da|q]]

---
![[Sparsest Cut#^292a9d]]
![[Sparsest Cut#^9d40c1|p]]
