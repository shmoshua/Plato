#Definition #ProbabilityTheory 

> [!definition]
> Let $X:\Omega\to \mathbb{R}$ be a real [[random variable]]. 
> 1. The ***$p$-th moment of $X$*** is given by $\mathbb{E}[X^p]$,  which exists only if $\mathbb{E}[\left| X \right|^p]<+\infty$. 
- **Remark**: The $1$st moment of $X$ is the [[expected value]] of $X$.
---
##### Properties

> [!lemma] Theorem 1
> Let $X_{1},\dots,X_{n}\sim \text{Ber}(p)$ for $p\geq 1/n$ be $4$-wise independent. Let $X:=\sum_{i=1}^{n}X_{i}$ and $\mu:=\mathbb{E}[X]=np$. Then, for any $d>0$, $$\mathbb{P}(\left| X-\mu \right| \geq d)\leq \frac{\mu+3\mu^{2}}{d^4}$$

^7763b9

> [!proof]-
> We have that by Markov: $$\mathbb{P}(\left| X-\mu \right| \geq d)=\mathbb{P}((X-\mu)^4\geq d^4)\leq \frac{\mathbb{E}[(X-\mu)^4]}{d^4 }$$We can write: $$\begin{align}\mathbb{E}[(X-\mu)^4]&=\sum_{i,j,k,\ell\in[n]}^{}\mathbb{E}[(X_{i}-p)(X_{j}-p)(X_{k}-p)(X_{\ell}-p)]\\&=\sum_{i\in[n]}^{}\mathbb{E}[(X_{i}-p)^4]+{4 \choose 2}\sum_{i<j}^{}\mathbb{E}[(X_{i}-p)^{2}(X_{j}-p)^{2}]\end{align}$$where the other terms are 0 by 4-independence. Then, 
> 1. As $-1\leq X_{i}-p\leq 1$, we have that $(X_{i}-p)^\ell\leq 1$ for all $\ell\geq 0$. Hence, $$\mathbb{E}[(X_{i}-p)^4]\leq \mathbb{E}[(X_{i}-p)^{2}]=p(1-p)^{2}+(1-p)\cdot p^2=p-p^{2}\leq p$$
> 2. By independence of $X_{i},X_{j}$, we have: $$\mathbb{E}[(Y_{i}-p)^{2}(Y_{j}-p)^{2}]=\mathbb{E}[(Y_{i}-p)^{2}]^{2}\leq p^{2}$$
>    
> Therefore, $$\mathbb{E}[(X-\mu)^{4}]\leq np+6 {n \choose 2} p^{2}<np+3p^2n^2=\mu+3\mu^{2}$$ 

^9da4fc

---
> [!lemma] Theorem 2
> Let $X_{1},\dots,X_{n}\sim \text{Ber}(p)$ be $k$-wise independent where $k$ is even. Let $X:=\sum_{i=1}^{n}X_{i}$ and $\mu:=\mathbb{E}[X]=np$. Then, for any $d>0$, $$\mathbb{P}(\left| X-\mu \right| >d\sqrt{ \mu })\leq O(k^k / (2d)^k)$$

> [!proof]-
> Let $j_{1},\dots,j_{c}$ be distinct indices in $[k]$. Let $m_{1},\dots,m_{c}$ denote their multiplicity, i.e. $\sum_{j}^{}m_{j}=k$. Then, 
> 1. if $c>k /2$, then there exists $h\in[c]$ with $m_{h}=1$. Hence, $$\begin{align}\mathbb{E}[(X_{j_{1}}-p)^{m_{1}}\dots(X_{j_{c}}-p)^{m_{c}}]&=\mathbb{E}[(X_{j_{h}}-p)]\mathbb{E}[(X_{j_{1}}-p)^{m_{1}}\dots \widehat{(X_{j_{h}}-p)^{m_{h}}}\dots(X_{j_{c}}-p)^{m_{c}}]\\&=0\end{align}$$
> 2. if $c\leq k / 2$, then: $$\mathbb{E}[(X_{j_{1}}-p)^{m_{1}}\dots(X_{j_{c}}-p)^{m_{c}}]\leq \prod_{i=1}^{c}\mathbb{E}[(X_{j_{i}}-p)^2]\leq p^c$$
> 
> Therefore, we have: $$\begin{align}\mathbb{P}(\left| X-\mu \right| >d\sqrt{ \mu })&=\mathbb{P}((X-\mu)^k>d^k \mu^{k / 2})\\&\leq \frac{\mathbb{E}[(X-\mu )^k]}{d^k \mu^{k / 2}}\\&\leq \frac{1}{d^k \mu^{k / 2}}\sum_{c=1}^{k/2}c^k{n \choose c}p^c\\&\leq\frac{1}{d^k\mu^{k /2 }}\sum_{c=1}^{k/2}c^k(np)^c\\&\leq \text{O}\left( \frac{1}{d^k\mu^{k/2}}\mu^{k / 2} (k / 2)^k \right)\\&=\text{O}\left( \frac{k^k}{(2d)^k} \right) \end{align}$$
---
\