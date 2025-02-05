#Definition #Algebra 

>[!definition]
> Let $A\in \text{Mat}_{n,n}(K)$. 
> 1. The ***permanent*** of $A$ is defined as:$$\text{Per}(A):=\sum_{\sigma\in S_{n}}^{}\prod_{i=1}^{n}A_{i,\sigma(i)}$$

^cc906b

- **Remark**: Computing $\text{Per}(A)$ is $\#P$, i.e. harder than NP-hard problems. ^7904f8
- **Remark**: $\text{Per}(A)\leq \prod_{i=1}^{n}\sum_{j=1}^{n}a_{ij}$ ^f4f2dc
---
##### Properties

> [!lemma] Lemma 1
> For any permutation matrix $P,Q\in \text{Mat}_{n,n}(K)$, 
> 1. $\text{Per}(A)=\text{Per}(PAQ)$.

^530cc3

> [!proof]-
> We have that:
> 1. Let $\pi,\rho$ denote the permutation of $P,Q$ respectively, i.e. $P_{i,j}=1$ if and only if $\pi(i)=j$ and similar. Then, notice that: $$\text{Per}(PAQ)=\sum_{\sigma\in S_{n}}^{}\prod_{i=1}^{n}(PAQ)_{i,\sigma(i)}=\sum_{\sigma\in S_{n}}^{}\prod_{i=1}^nA_{\pi(i),\rho ^{-1}(\sigma(i))}=\sum_{\sigma\in S_{n}}^{}\prod_{i=1}^nA_{i,\rho ^{-1}\sigma\pi ^{-1}(i)}$$

^63071a

---
> [!lemma] Theorem 2 (Brégman)
> Let $A\in \text{Mat}_{n,n}(\mathbb{Z})$ with entries in $\{ 0,1 \}$. Then, for $r_{i}:=\sum_{j=1}^{n}a_{ij}$, $$\text{Per}(A)\leq \prod_{i=1}^{n}(r_{i}!)^{1 / r_{i}} \approx \frac{1}{e^n}\prod_{i=1}^{n}r_{i}$$

^eefbb0

> [!proof]-
> By induction over $n$.
> 1. if $n=1$, then the statement is trivial. 
> 2. Assume $n\geq 2$. As both sides of the inequality are positive, it suffices to show that: $$\text{Per}(A)^{n \text{Per}(A)}\leq \left( \prod_{i=1}^{n}(r_{i}!)^{1 / r_{i}} \right) ^{n\text{Per}(A)} $$
> 
> 	Let $S$ be the set of permutations $\sigma\in S_{n}$ with $A_{i,\sigma(i)}=1$ for every $i\in[n]$. Then, $\text{Per}(A)=\left| S \right|$ and we have that: $$\begin{align}\text{Per}(A)^{n \text{Per}(A)}=\prod_{i=1}^{n}\text{Per(A)}^{\text{Per}(A)}\end{align}$$
> 	
> 	Fix $i\in[n]$. We introduce the notation $A^{ik}\in \text{Mat}_{n-1,n-1}(\mathbb{Z})$ where $A^{ik}$ is $A$ without row $i$ and column $k$. Then, 
> 	1. **Claim 1**: $\text{Per}(A)=\sum_{k:A_{i,k}=1}^{}\text{Per}(A^{ik})$. We have: $$\begin{align}\text{Per}(A)&=\sum_{\sigma\in S_{n}}^{}\prod_{j=1}^{n}A_{j,\sigma(j)}\\&=\sum_{k\in[n]}^{}\sum_{\sigma\in S_{n}:\sigma(i)=k}^{}\prod_{j=1}^{n}A_{j,\sigma(j)}=\sum_{k:A_{i,k}=1}^{}\sum_{\sigma\in S_{n}:\sigma(i)=k}^{}\prod_{j\neq i}A_{j,\sigma(j)}=\sum_{k:A_{i,k=1}}^{}\text{Per}(A^{ik})\end{align}$$
> 
> 	Therefore, by [[Technical Lemmas|Lemma for Bregman]], $$\text{Per}(A)^{\text{Per}(A)}\leq\prod_{k:A_{i,k}=1}^{}(r_{i}\text{Per}(A_{ik}))^{\text{Per}(A_{ik})}$$and $$\begin{align}\text{Per}(A)^{n \text{Per}(A)}&\leq \prod_{i=1}^{n}r_{i}^{\text{Per}(A)}\prod_{k:A_{ik}=1}^{}\text{Per}(A_{ik})^{\text{Per}(A_{ik})}=\prod_{\sigma\in S}\left( \prod_{i=1}^{n}r_{i}\cdot \prod_{j=1}^{n}\text{Per}(A_{j\sigma(j)}) \right)\\&\leq\prod_{\sigma\in S}\left( \prod_{i=1}^{n}r_{i}\cdot \prod_{j=1}^{n}\text{Per}(A_{j\sigma(j)}) \right)\end{align}$$

^a1cd36


- **Remark**: This bound is tight. For $n=t_{1}+\dots+t_{k}$, consider $A$ be a diagonal block matrix $\text{diag}(M_{1},\dots,M_{k})$ where $M_{i}$ is a $t_{i}\times t_{i}$-matrix of ones. Then, $$\text{Per}(A)=\prod_{i=1}^{k}t_{i}!=\prod_{i=1}^{n}(r_{i}!)^{1/ r_{i}}$$

---
##### Examples
> [!h] Example 1 (Perfect Matchings)
> Let $G$ be a graph and $A$ its adjacency matrix. 
> 1. the number of perfect matchings on $G$ is given by $\text{Per}(A)$. 

> [!proof]+ (TODO)

---
