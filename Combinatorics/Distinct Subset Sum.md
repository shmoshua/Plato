#Definition #Combinatorics 

> [!definition]
> A subset $A\subseteq [n]$ has ***distinct subset sums*** if:
> 1. $\left\{  \sum_{a\in S}^{}a  \right\}_{S\subseteq A}$ has cardinality $2^{\left| A \right|}$, i.e. the subset sums are all distinct.
- **Related definition**: $f(n):=\max \{ k\geq  0: \left| A \right|=k, A\subseteq [n] \text{ has distinct subset sums}\}$.
- **Remark**: If $A$ has distinct subset sums, we have that $2^{\left| A \right|}\leq \left| A \right|\cdot n$. Hence, $f(n)<\log_{2}n+\log_{2}\log_{2}n+O(1)$.
---
##### Properties
> [!lemma] Theorem 1
> We have that:
> 1. $f(n)<\log_{2}n+\frac{1}{2}\log_{2}\log_{2}n+O(1)$.

---
##### Examples
> [!h] Example 1
> $\{ 2^i:i\in[\left\lfloor\log_{2}n\right\rfloor] \}$ has distinct subset sum. 