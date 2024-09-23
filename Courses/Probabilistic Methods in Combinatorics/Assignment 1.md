#ProbabilisticMethods #Series 


> [!def] Problem 1
> Prove that: 
> 1. if there exists a real $0\leq p\leq 1$ s.t. $${n\choose s}p^{s\choose 2}+{n\choose t}(1-p)^{t\choose 2}<1$$then $R(s,t)>n$.
> 2. Using this, show that the following holds for some constant $c$: $$R(4,t)\geq c\cdot  \frac{t^{3 / 2}}{(\log t)^{3/2}}$$

We have:
1. we will consider a coloring on $K_{n}$ where the colors are assigned randomly as follows: each edge is given the color red with the probability $p$ independently and otherwise blue. Now, notice that there are $n \choose s$ copies of $K_{s}$ and $n \choose t$ copies of $K_{t}$ in $K_{n}$. Let $A_{i}$ denote the event that the $i$-th $K_{s}$ is red and let $B_{j}$ denote the event that the $j$-th $K_{t}$ is blue. Then, $\mathbb{P}(A_{i})=p^{s\choose_{2}}$ and $\mathbb{P}(B_{j})=(1-p)^{t \choose 2}$ for all $i,j$. 
   
   Then, $$\mathbb{P}(\exists \text{red }K_{s}\text{ or blue }K_{t})\leq \mathbb{P}\left( \bigcup_{i}^{}A_{i}\cup \bigcup_{j}^{}B_{j} \right)\leq{n \choose s}p^{s \choose 2}+{n \choose t}(1-p)^{t \choose 2}<1$$Therefore, there is a coloring on $K_{n}$ that doesn't contain a red $K_{s}$ or a blue $K_{t}$. This shows that $R(s,t)>n$.
2. Let $n:=$
---

> [!def] Problem 2
> Let $\mathcal{A}$ be a family of subsets of $[n]$ such that there are no distinct $A,B\in \mathcal{A}$ with $A\subseteq B$. Prove that $$\left| \mathcal{A} \right|\leq{n \choose \left\lfloor n /2\right\rfloor}$$

