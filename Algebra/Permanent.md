#Definition #Algebra 

>[!definition]
> Let $A\in \text{Mat}_{n,n}(K)$. 
> 1. The ***permanent*** of $A$ is defined as:$$\text{Per}(A):=\sum_{\sigma\in S_{n}}^{}\prod_{i=1}^{n}A_{i,\sigma(i)}$$
- **Remark**: Computing $\text{Per}(A)$ is $\#P$, i.e. harder than NP-hard problems.
- **Remark**: $\text{Per}(A)\leq \prod_{i=1}^{n}\sum_{j=1}^{n}a_{ij}$
---
##### Properties

> [!lemma] Theorem 1 (Brégman)
> Let $A\in \text{Mat}_{n,n}(\mathbb{Z})$ with entries in $\{ 0,1 \}$. Then, for $r_{i}:=\sum_{j=1}^{n}a_{ij}$, $$\text{Per}(A)\leq \prod_{i=1}^{n}(r_{i}!)^{1 / r_{i}} \approx \frac{1}{e^n}\prod_{i=1}^{n}r_{i}$$

> [!proof]+
> Let $S$ be the set of permutations $\sigma\in S_{n}$ with $A_{i,\sigma(i)}=1$ for every $i\in[n]$. Then, $\text{Per}(A)=\left| S \right|$. Choose $\sigma\in S$ and $\tau\in S_{n}$ independently and uniformly at random.
> 
> Let $A^{(1)}:=A$. . Delete row $\tau(1)$ and column $\sigma \tau(1)$ from $A^{(1)}$ to give $A^{(2)}$. Inductively, let $A^{(i)}$ be defined as $A$ with rows $\tau(1),\dots,\tau(i-1)$ and columns $\sigma \tau(1),\dots,\sigma \tau(i-1)$ deleted. Further, let $R$

- **Remark**: This bound is tight. For $n=t_{1}+\dots+t_{k}$, consider $A$ be a diagonal block matrix $\text{diag}(M_{1},\dots,M_{k})$ where $M_{i}$ is a $t_{i}\times t_{i}$-matrix of ones. Then, $$\text{Per}(A)=\prod_{i=1}^{k}t_{i}!=\prod_{i=1}^{n}(r_{i}!)^{1/ r_{i}}$$

---
##### Examples
> [!h] Example 1 (Perfect Matchings)
> Let $G$ be a graph and $A$ its adjacency matrix. 
> 1. the number of perfect matchings on $G$ is given by $\text{Per}(A)$. 

> [!proof]+ (TODO)

---
