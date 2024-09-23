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

Consider the random variable $X(\sigma):=\left| \{ i\in[n]:\{ \sigma(1),\dots,\sigma(i) \}\in \mathcal{A} \} \right|$. Then, we can rewrite this into: $X(\sigma)=\sum_{i\in [n]}^{}\sum_{A\in \mathcal{A}}^{}1_{\{ \sigma(1),\dots,\sigma(i) \}=A}$. Therefore, 
$$\mathbb{E}(X)=\sum_{A\in \mathcal{A}}^{}\sum_{i\in [n]}^{}P(\{ \sigma(1),\dots,\sigma(i) \}=A)=\sum_{A\in \mathcal{A}}^{}P(\{ \sigma(1),\dots,\sigma(\left| A \right| ) \}=A)$$ Notice that $P(\{ \sigma(1),\dots,\sigma(\left| A \right|) \}=A)=\frac{\left| A \right|!(n-\left| A \right|)!}{n!}=1 / {n \choose\left| A \right|}\geq 1 / {n \choose \left\lfloor n / 2\right\rfloor}$ as there are $\left| A \right|!$ ways to choose the order of the first $\left| A \right|$ and then $(n-\left| A \right|)!$ for the rest. Therefore, $\mathbb{E}(X)\geq \left| \mathcal{A} \right|\frac{1}{n\choose \left\lfloor n / 2\right\rfloor}$. 

Conversely,  for any permutation $\sigma\in \Pi$, we have that $X(\sigma)\leq 1$. Assume that $X(\sigma)\geq 2$, i.e. $i<j$ s.t. $\{ \sigma(1),\dots,\sigma(i) \},\{ \sigma(1),\dots,\sigma(j) \}\in \mathcal{A}$.  Then, $\{ \sigma(1),\dots,\sigma(i) \}\subseteq \{ \sigma(1),\dots,\sigma(j) \}$ which is a contradiction. Therefore, if we choose the permutation uniformly randomly, $$\mathbb{E}(X)=\frac{1}{n!}\sum_{\sigma\in \Pi}^{}X(\sigma)\leq 1 $$Therefore, $\left| \mathcal{A} \right| \frac{1}{n \choose \left\lfloor n / 2\right\rfloor}\leq \mathbb{E}(X)\leq 1$ and this proves the statement.

---
