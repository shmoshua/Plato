#Algorithms #Roadmap 

### 1. Basics of Approximation Algorithms
In trying to approximate an algorithm there are two approaches: Greedy and Rounding

---

#### 1.1 Greedy Algorithms
![[Minimum Set Cover#^2ed1e3]]
![[Minimum Set Cover#^0eb03c|q]]
---
![[Minimum Set Cover#^eb92be]]
![[Minimum Set Cover#^d320dd|p]]
![[Minimum Set Cover#^4d9187|q]]

---
#### 1.2 Approximation Schemes
![[Knapsack#^fca662]]
- **Remark**: As any $i\in \mathcal{S}$ with $s_{i}>B$ cannot be chosen, wlog we assume that $s_{i}\leq B$.  
- **Remark**: It is clear that $\max_{i}p_{i}\leq p(\text{OPT}(I))\leq n\cdot \max_{i}p_{i}$. 
---
![[Knapsack#^13ab4a]]

---
![[Knapsack#^532344]]
![[Knapsack#^c811f3|p]]

---


##### 1.2.1 PTAS and FPTAS
![[PTAS#^968d36]]

---
![[FPTAS#^a99681]]

---

##### 1.2.2 Knapsack

![[Knapsack#^675511]]
![[Knapsack#^13ab4a]]

---
![[Knapsack#^532344]]
![[Knapsack#^c811f3|p]]

---
##### 1.2.3 Bin-Packing
![[Bin-Packing#^06f901]]
![[Bin-Packing#^d65196|q]]
![[Bin-Packing#^a84502|q]]
---
![[Bin-Packing#^769d08]]
![[Bin-Packing#^db3116|p]]
---
![[Bin-Packing#^c04d44]]
![[Bin-Packing#^3e5c2c|p]]
---
##### 1.2.3.1 Bin-Packing FPTAS
![[Bin-Packing#^62d5f8]]
![[Bin-Packing#^5e1d26|p]]

---
![[Bin-Packing#^cb3b26]]
![[Bin-Packing#^697fb8|p]]

---
![[Bin-Packing#^58af47]]
![[Bin-Packing#^4776b1|p]]

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
#### 2.1 Online Algorithms
##### 2.1.1 Ski Rental Problem
> [!outlook] Ski Rental Problem
> For $k\in \mathbb{Z}_{> 1}$, let $1$ be the cost for renting a ski one day and $k$ for buying.a ski. When we don't know how many days we are going to ski, what is our strategy?
> 1. Consider renting for $k$ days and buying the ski after. 
> 2. Let $D$ be the number of days (which is unknown). We have that: 
> 	1. if $D\leq k$, then the cost is $D$ whereas the optimal cost in hindsight is $D$.
> 	2. if $D> k$, then the cost is $2k$ whereas the optimal cost in hindsight is $k$.
> 
> Therefore, we have a $2$-competitive online algorithm.