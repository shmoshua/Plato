#Definition #Combinatorics 

> [!definition]
> A subset $A\subseteq [n]$ has ***distinct subset sums*** if:
> 1. $\left\{  \sum_{a\in S}^{}a  \right\}_{S\subseteq A}$ has cardinality $2^{\left| A \right|}$, i.e. the subset sums are all distinct.

^4b6a69

- **Related definition**: $f(n):=\max \{ k\geq  0: \left| A \right|=k, A\subseteq [n] \text{ has distinct subset sums}\}$. ^56fed9
- **Remark**: If $A$ has distinct subset sums, we have that $2^{\left| A \right|}\leq \left| A \right|\cdot n$. Hence, $f(n)<\log_{2}n+\log_{2}\log_{2}n+O(1)$. ^995b65
---
##### Properties
> [!lemma] Theorem 1
> We have that:
> 1. $f(n)<\log_{2}n+\frac{1}{2}\log_{2}\log_{2}n+O(1)$.

^1939e0

> [!proof]-
> Let $A=\{ a_{1},\dots,a_{k} \}\subseteq [n]$ have distinct subset sums of size $k=f(n)$. Let $\varepsilon_{1},\dots,\varepsilon_{k}$ be independent random variables taking $\{ 0,1 \}$ as values with probability $1 / 2$. 
> 
> Let $X=\sum_{i}^{}\varepsilon_{i}a_{i}$. Then, $$\mathbb{E}[X]=\frac{1}{2}\sum_{i}^{}a_{i},\quad \text{Var}(X)=\frac{1}{4}\sum_{i}^{}a_{i}^{2}\leq \frac{1}{4}kn^{2}$$Therefore, by Chebyshev, $$\mathbb{P}(\left| X-\mathbb{E}[X] \right| \geq n\sqrt{ k })\leq \frac{1}{4}$$However, note that $\mathbb{P}(\left| X-\mathbb{E}[X] \right|\geq n\sqrt{ k })=\frac{N}{2^k}$ where $N$ is the number of subset sums with $\left| \sum_{a\in S}^{}a - \mathbb{E}[X] \right|\geq n\sqrt{ k }$. Therefore, the number of subset sums with $\left| \sum_{a\in S}^{}a-\mathbb{E}[X] \right|< n\sqrt{ k }$ is given by at least $2^k \frac{3}{4}$. However, as each of these values are different. We have: $$\frac{3}{4}2^k\leq 2n\sqrt{ k }$$and we get $2^k\leq \frac{8}{3}n\sqrt{ k }$ with: $$\begin{align}k&\leq \log n+\frac{1}{2}\log k + O(1)\\&\leq \log n+\frac{1}{2}\log \log n+O(1)\end{align}$$

^7bd15b

---
##### Examples
> [!h] Example 1
> $\{ 2^i:i\in[\left\lfloor\log_{2}n\right\rfloor] \}$ has distinct subset sum. 