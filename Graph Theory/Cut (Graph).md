#Definition #GraphTheory 

> [!definition]
> Let $G:=(V,E)$ be a [[graph]]. Then, 
> 1. A ***cut*** is $(A,B)$ s.t. $A\sqcup B=V$. Then, the set of edges that have endpoints both in $A$ and $B$ is called the ***cut set***.

^27b1e1

---
##### Properties
> [!lemma] Theorem 1 (Max-cut)
> Let $G:=(V,E)$ be a graph with $m$ edges. Then
> 1. $\max_{(A,B),A\sqcup B = V}e(A,B)\geq m / 2$.

^b245ae

> [!proof]-
> We will assign the vertices into $A$ and $B$ uniformly randomly independently. Then, 
> 1. **Claim 1: $\mathbb{E}[X] = m / 2$**
>    Let $X=\sum_{e\in E}^{}\mathbb{1}_{\{ \left| e\cap A \right|=1\lor \left| e\cap B \right|=1 \}}$. Then, $\mathbb{P}(\left| e\cap A \right|=1\lor \left| e\cap B \right|=1)=\frac{1}{2}$. Therefore, $\mathbb{E}[X]=\sum_{e\in E}^{} \frac{1}{2}=\frac{m}{2}$. 
>    
>  Or one can simply make sure that we move the vertices until they have more than half of its neighbors on the other side.

^b83c9a

- **Remark**: Maxcut $\geq m / 2+c\sqrt{ m }$. 
---

> [!lemma] Theorem (Karger)
> Let $s$ be the size of the minimal cut set. Then, for all $\alpha\geq 1$, 
> 1. the number of cut set of size $\leq\alpha s$ is $\leq n^{2\alpha}$
---
