#Definition #Algebra 

>[!definition]
> Let $A\in \text{Mat}_{n,n}(K)$. 
> 1. The ***permanent*** of $A$ is defined as:$$\text{Per}(A):=\sum_{\sigma\in S_{n}}^{}\prod_{i=1}^{n}A_{i,\sigma(i)}$$
- **Remark**: $\text{Per}(A)\leq \prod_{i=1}^{n}\sum_{j=1}^{n}a_{ij}$
---
##### Properties
> [!lemma] Theorem 1 (Brégman)
> Let $A\in \text{Mat}_{n,n}(\mathbb{Z})$ with entries in $\{ 0,1 \}$. Then, for $r_{i}:=\sum_{j=1}^{n}a_{ij}$, $$\text{Per}(A)\leq \prod_{i=1}^{n}(r_{i}!)^{1 / r_{i}} \approx \frac{1}{e^n}\prod_{i=1}^{n}r_{i}$$

- **Remark**: This bound is tight. For $n=t_{1}+\dots+t_{k}$, consider $A$ be a diagonal block matrix $\text{diag}()$

---
##### Examples
> [!h] Example 1 (Perfect Matchings)
> Let $G$ be a graph and $A$ its adjacency matrix. 
> 1. the number of perfect matchings on $G$ is given by $\text{Per}(A)$. 

> [!proof]+ (TODO)

---
