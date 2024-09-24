#ProbabilisticMethods #Series 


> [!def] Problem 1
> Prove that: 
> 1. if there exists a real $0\leq p\leq 1$ s.t. $${n\choose s}p^{s\choose 2}+{n\choose t}(1-p)^{t\choose 2}<1$$then $R(s,t)>n$.
> 2. Using this, show that the following holds for some constant $c$: $$R(4,t)\geq c\cdot  \frac{t^{3 / 2}}{(\log t)^{3/2}}$$

We have:
1. we will consider a coloring on $K_{n}$ where the colors are assigned randomly as follows: each edge is given the color red with the probability $p$ independently and otherwise blue. Now, notice that there are $n \choose s$ copies of $K_{s}$ and $n \choose t$ copies of $K_{t}$ in $K_{n}$. Let $A_{i}$ denote the event that the $i$-th $K_{s}$ is red and let $B_{j}$ denote the event that the $j$-th $K_{t}$ is blue. Then, $\mathbb{P}(A_{i})=p^{s\choose_{2}}$ and $\mathbb{P}(B_{j})=(1-p)^{t \choose 2}$ for all $i,j$. 
   
   Then, $$\mathbb{P}(\exists \text{red }K_{s}\text{ or blue }K_{t})\leq \mathbb{P}\left( \bigcup_{i}^{}A_{i}\cup \bigcup_{j}^{}B_{j} \right)\leq{n \choose s}p^{s \choose 2}+{n \choose t}(1-p)^{t \choose 2}<1$$Therefore, there is a coloring on $K_{n}$ that doesn't contain a red $K_{s}$ or a blue $K_{t}$. This shows that $R(s,t)>n$.
2. Consider $p = \log t / t$ and $n\leq t^{3/2} / \log^{3 /2}t$. 
   
   
   Then, 
   
   $$\begin{align}{n \choose 4}p^6+{n \choose t}(1-p)^{t \choose_{2}}&\leq \frac{n^4\cdot p^6}{24}+\left( \frac{en}{t} \right)^te^{-\frac{(t-1)\log t}{2}}\\&\leq \frac{1}{24}+  \frac{e^tt^{t/2}}{\log^{3t/2}t} t^{-(t-1)/2} \\&\leq \frac{1}{24}+  \frac{e^tt^{1/2}}{\log^{3t/2}t} <1 \end{align}$$Therefore, $R(4,t)=\Omega(t^{3/2} / \log^{3 /2} t)$
---

> [!def] Problem 2
> Let $\mathcal{A}$ be a family of subsets of $[n]$ such that there are no distinct $A,B\in \mathcal{A}$ with $A\subseteq B$. Prove that $$\left| \mathcal{A} \right|\leq{n \choose \left\lfloor n /2\right\rfloor}$$

Consider the random variable $X(\sigma):=\left| \{ i\in[n]:\{ \sigma(1),\dots,\sigma(i) \}\in \mathcal{A} \} \right|$. Then, we can rewrite this into: $X(\sigma)=\sum_{i\in [n]}^{}\sum_{A\in \mathcal{A}}^{}1_{\{ \sigma(1),\dots,\sigma(i) \}=A}$. Therefore, 
$$\mathbb{E}(X)=\sum_{A\in \mathcal{A}}^{}\sum_{i\in [n]}^{}P(\{ \sigma(1),\dots,\sigma(i) \}=A)=\sum_{A\in \mathcal{A}}^{}P(\{ \sigma(1),\dots,\sigma(\left| A \right| ) \}=A)$$ Notice that $P(\{ \sigma(1),\dots,\sigma(\left| A \right|) \}=A)=\frac{\left| A \right|!(n-\left| A \right|)!}{n!}=1 / {n \choose\left| A \right|}\geq 1 / {n \choose \left\lfloor n / 2\right\rfloor}$ as there are $\left| A \right|!$ ways to choose the order of the first $\left| A \right|$ and then $(n-\left| A \right|)!$ for the rest. Therefore, $\mathbb{E}(X)\geq \left| \mathcal{A} \right|\frac{1}{n\choose \left\lfloor n / 2\right\rfloor}$. 

Conversely,  for any permutation $\sigma\in \Pi$, we have that $X(\sigma)\leq 1$. Assume that $X(\sigma)\geq 2$, i.e. $i<j$ s.t. $\{ \sigma(1),\dots,\sigma(i) \},\{ \sigma(1),\dots,\sigma(j) \}\in \mathcal{A}$.  Then, $\{ \sigma(1),\dots,\sigma(i) \}\subseteq \{ \sigma(1),\dots,\sigma(j) \}$ which is a contradiction. Therefore, if we choose the permutation uniformly randomly, $$\mathbb{E}(X)=\frac{1}{n!}\sum_{\sigma\in \Pi}^{}X(\sigma)\leq 1 $$Therefore, $\left| \mathcal{A} \right| \frac{1}{n \choose \left\lfloor n / 2\right\rfloor}\leq \mathbb{E}(X)\leq 1$ and this proves the statement.

---
> [!def] Problem 3
> We have that:
> 1. $f(k)\geq 2^{k+1}-1$ for any $k\in \mathbb{N}$.
> 2. $f(k)=\Omega(k2^k)$

We have that:
1. Firstly, let $T_{n}$ be a tournament with $S_{k}$-property. Then, add a new vertex $v$ to $T_{n}$ where $u\to v$ for all $u\in V(T_{n})$. This is a new tournament with $S_{k}$-property. Therefore, this tells us it suffices to show that there is no tournament with $S_{k}$-property when $n=2^{k+1}-2$ to show the statement.
   
   We will proceed with induction over $k$. If $k=1$, Then, for any tournament $T_{2}$, there exists one edge between the two nodes and it trivially cannot have $S_{k}$-property. Now, let $k>1$ and $n=2^{k+1}-2$. Fix a $T_{n}$. By the handshaking lemma and the pigeonhole principle, there exists a vertex $v$ with out-degree at least $\left\lfloor \frac{(n-1)}{2}\right\rfloor=\left\lfloor \frac{2^{k+1}-3}{2}\right\rfloor=2^k-1$. Now, remove $v$ and $2^k-1$ arbitrarily chosen vertices $w$ for which $v \to w$. Then, we end up with a tournament of size $(2^{k+1}-2)-1-(2^k-1)=2^k-2$. This tournament cannot have $S_{k-1}$-property by induction hypothesis. Let $S$ be a set of $k-1$ nodes in this tournament that is not dominated. Then, $S\cup \{ v \}$ is a set in the original tournament that is not dominated. Indeed, by assumption it is not dominated by any in the smaller tournament and it cannot be dominated by any of the removed vertices as they are all dominated by $v$. This proves the statement.
2. If $S_{k}$, then every $k-1$ vertex are dominated by $\geq k+1$ vertices.
---
