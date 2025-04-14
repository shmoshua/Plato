#ProbabilityTheory 

#### 1. Variance
1. $\text{Var}(X)=\mathbb{E}[(X-\mathbb{E}[X])^{2}]$
2. $\text{Var}(X)=\mathbb{E}[X^{2}]-\mathbb{E}[X]^{2}$
3. $\text{Var}(\lambda X)=\lambda^{2} \text{Var}(X)$
4. $\text{Var}(X+Y)=\text{Var}(X)+\text{Var}(Y)$
5. $\text{Cov}(X,Y)=\mathbb{E}[XY]-\mathbb{E}[X]\mathbb{E}[Y]$

6. $X\sim \text{Ber}(p)$ then $\text{Var}(X)=p(1-p)$.
7. $X\sim \text{Bin}(n,p)$ then $\text{Var}(X)=np(1-p)$.
8. $X\sim \text{Geo}(p)$, then: $$\mathbb{E}[X(X-1)]=p\sum_{k=1}^{\infty}k(k-1)(1-p)^{k-1}=p \frac{d}{dq}\left( \sum_{k=1}^{\infty}(k-1)q^k \right) $$
---
#### 2. Joint and Marginal Distributions

1. 