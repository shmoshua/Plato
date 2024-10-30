#Definition #ProbabilityTheory 

> [!definition]
> Let $X:\Omega\to \mathbb{R}$ be a real [[random variable]]. 
> 1. The ***$p$-th moment of $X$*** is given by $\mathbb{E}[X^p]$,  which exists only if $\mathbb{E}[\left| X \right|^p]<+\infty$. 
- **Remark**: The $1$st moment of $X$ is the [[expected value]] of $X$.
---
##### Properties

> [!lemma] Theorem 1
> Let $X_{1},\dots,X_{n}\sim \text{Ber}(p)$ for $p\geq 1/n$ be $4$-wise independent. Let $X:=\sum_{i=1}^{n}X_{i}$ and $\mu:=\mathbb{E}[X]=np$. Then, for any $d>0$, $$\mathbb{P}(\left| X-\mu \right| >d\sqrt{ \mu })< \frac{4}{d^4}$$

> [!proof]-
> We have that: $$\mathbb{P}(\left| X-\mu \right| >d\sqrt{ \mu })=\mathbb{P}((X-\mu)^4>d^4\mu^2)\leq \frac{\mathbb{E}[(X-\mu)^4]}{d^4 \mu^2}$$We can write: $$\begin{align}\mathbb{E}[(X-\mu)^4]&=\sum_{i,j,k,\ell\in[n]}^{}\mathbb{E}[(X_{i}-p)(X_{j}-p)(X_{k}-p)(X_{\ell}-p)]\\&=\sum_{i\in[n]}^{}\mathbb{E}[(X_{i}-p)^4]+{4 \choose 2}\sum_{i<j}^{}\mathbb{E}[(X_{i}-p)^{2}(X_{j}-p)^{2}]\end{align}$$where the other terms are 0 by 4-independence. Then, 
> 1. As $-1\leq X_{i}-p\leq 1$, we have that $(X_{i}-p)^\ell\leq 1$ for all $\ell\geq 0$. Hence, $$\mathbb{E}[(X_{i}-p)^4]\leq \mathbb{E}[(X_{i}-p)^{2}]=p(1-p)^{2}+(1-p)\cdot p^2=p-p^{2}\leq p$$
> 2. By independence of $X_{i},X_{j}$, we have: $$\mathbb{E}[(Y_{i}-p)^{2}(Y_{j}-p)^{2}]=\mathbb{E}[(Y_{i}-p)^{2}]^{2}\leq p^{2}$$
>    
> Therefore, $$\mathbb{E}[(X-\mu)^{4}]\leq np+6 {n \choose 2} p^{2}<np+3p^2n^2\leq 4n^2p^2$$ Hence, $$\mathbb{P}(\left| X-\mu \right| >d\sqrt{ \mu })< \frac{4}{d^4}$$
---
> [!lemma] Theorem 2
> Let $X_{1},\dots,X_{n}\sim \text{Ber}(p)$ be $k$-wise independent where $k$ is even. Let $X:=\sum_{i=1}^{n}X_{i}$ and $\mu:=\mathbb{E}[X]=np$. Then, for any $d>0$, $$\mathbb{P}(\left| X-\mu \right| >d\sqrt{ \mu })\leq O(k^k / (2d)^k)$$