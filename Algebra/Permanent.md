#Definition #Algebra 

>[!definition]
> Let $A\in \text{Mat}_{n,n}(K)$. 
> 1. The ***permanent*** of $A$ is defined as:$$\text{Per}(A):=\sum_{\sigma\in S_{n}}^{}\prod_{i=1}^{n}A_{i,\sigma(i)}$$
- **Remark**: Computing $\text{Per}(A)$ is $\#P$, i.e. harder than NP-hard problems.
- **Remark**: $\text{Per}(A)\leq \prod_{i=1}^{n}\sum_{j=1}^{n}a_{ij}$
---
##### Properties

> [!lemma] Lemma 1
> For any permutation matrix $P,Q\in \text{Mat}_{n,n}(K)$, 
> 1. $\text{Per}(A)=\text{Per}(PAQ)$.

> [!proof]-
> We have that:
> 1. Let $\pi,\rho$ denote the permutation of $P,Q$ respectively, i.e. $P_{i,j}=1$ if and only if $\pi(i)=j$ and similar. Then, notice that: $$\text{Per}(PAQ)=\sum_{\sigma\in S_{n}}^{}\prod_{i=1}^{n}(PAQ)_{i,\sigma(i)}=\sum_{\sigma\in S_{n}}^{}\prod_{i=1}^nA_{\pi(i),\rho ^{-1}(\sigma(i))}=\sum_{\sigma\in S_{n}}^{}\prod_{i=1}^nA_{i,\rho ^{-1}\sigma\pi ^{-1}(i)}$$
---
> [!lemma] Theorem 2 (Brégman)
> Let $A\in \text{Mat}_{n,n}(\mathbb{Z})$ with entries in $\{ 0,1 \}$. Then, for $r_{i}:=\sum_{j=1}^{n}a_{ij}$, $$\text{Per}(A)\leq \prod_{i=1}^{n}(r_{i}!)^{1 / r_{i}} \approx \frac{1}{e^n}\prod_{i=1}^{n}r_{i}$$

> [!proof]+
> Let $S$ be the set of permutations $\sigma\in S_{n}$ with $A_{i,\sigma(i)}=1$ for every $i\in[n]$. Then, $\text{Per}(A)=\left| S \right|$. Choose $\sigma\in S$ and $\tau\in S_{n}$ independently and uniformly at random.
> 
> Let $A^{(i)}$ be defined as $A$ with rows $\tau(1),\dots,\tau(i-1)$ and columns $\sigma \tau(1),\dots,\sigma \tau(i-1)$ deleted. Further, let $R_{\tau(i)}$ denote the number of ones in row $\tau(i)$ in $A^{(i)}$. As $A_{\tau(i),\sigma \tau(i)}=1$ from $\sigma\in S$, we have that $R_{\tau(i)}\geq 1$. 
> 
> Now, define $L:=\prod_{i=1}^{n}R_{\tau(i)}$. For a random variable $Y>0$ that takes values $a_{1},\dots,a_{s}$ with probability $p_{1},\dots,p_{s}$, we define its geometric mean $G[Y]:=\prod_{i\in[s]}^{}a_{i}^{p_{i}}=\exp \left(\mathbb{E}[\ln Y]\right)$. 
> 
> We claim that $\text{Per}(A)\leq G[L]$. Let $\tau$ be fixed. We use induction on the size of the matrix. By lemma 1, we may assume that $\tau(1)$ has ones in the first $r:=r_{1}$ columns. For $1\leq j\leq r$, let $t_{j}$ be defined as the permanent of $A$ with row $\tau(1)$ and $j$-th column removed. 

- **Remark**: This bound is tight. For $n=t_{1}+\dots+t_{k}$, consider $A$ be a diagonal block matrix $\text{diag}(M_{1},\dots,M_{k})$ where $M_{i}$ is a $t_{i}\times t_{i}$-matrix of ones. Then, $$\text{Per}(A)=\prod_{i=1}^{k}t_{i}!=\prod_{i=1}^{n}(r_{i}!)^{1/ r_{i}}$$

---
##### Examples
> [!h] Example 1 (Perfect Matchings)
> Let $G$ be a graph and $A$ its adjacency matrix. 
> 1. the number of perfect matchings on $G$ is given by $\text{Per}(A)$. 

> [!proof]+ (TODO)

---
