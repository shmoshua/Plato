#ProbabilityTheory 

#### 1. Variance
1. $\text{Var}(X)=\mathbb{E}[(X-\mathbb{E}[X])^{2}]$
2. $\text{Var}(X)=\mathbb{E}[X^{2}]-\mathbb{E}[X]^{2}$
3. $\text{Var}(\lambda X)=\lambda^{2} \text{Var}(X)$
4. $\text{Var}(X+Y)=\text{Var}(X)+\text{Var}(Y)$
5. $\text{Cov}(X,Y)=\mathbb{E}[XY]-\mathbb{E}[X]\mathbb{E}[Y]$

6. $X\sim \text{Ber}(p)$ then $\text{Var}(X)=p(1-p)$.
7. $X\sim \text{Bin}(n,p)$ then $\text{Var}(X)=np(1-p)$.
8. $X\sim \text{Geo}(p)$, then: $$\begin{aligned}\mathbb{E}[X(X-1)]&=p\sum_{k=1}^{\infty}k(k-1)(1-p)^{k-1}\\&=p \frac{d}{dq}\left( \sum_{k=1}^{\infty}(k-1)q^k \right)\\&=p \frac{d}{dq}\left( q^2 \sum_{k=2}^{\infty}(k-1)q^{k-2} \right)\\&=p \frac{d}{dq}\left( q^2 \frac{d}{dq}\left( \sum_{k=2}^{\infty}q^{k-1} \right) \right) \\&=p \frac{d}{dq}\left( q^2 \frac{d}{dq}\left( \sum_{k=1}^{\infty}q^{k} \right) \right)\\&=p \frac{d}{dq}\left( q^2 \frac{d}{dq}\left( \frac{q}{1-q}\right) \right) \\&=p\frac{d}{dq}\left(  \frac{q^{2}}{(1-q)^{2}} \right) \\&=p \frac{-2q^{2}-2q(1-q)}{(1-q)^3}\\&=p\left( \frac{2q}{(1-q)^3} \right) \\&= \frac{2(1-p)}{p^{2}}\end{aligned}$$Hence, $$\mathbb{E}[X^{2}]-\mathbb{E}[X]^{2}=\mathbb{E}[X(X-1)]+\mathbb{E}[X]-\mathbb{E}[X]^{2}=\frac{2(1-p)}{p^{2}}+\frac{p}{p^{2}}-\frac{1}{p^{2}}=\frac{1-p}{p^{2}}$$
9. $X\sim \text{Poisson}(\lambda)$, $$\begin{aligned}\mathbb{E}[X^{2}]&=\sum_{k\geq 1}^{}k \cdot  \frac{1}{(k-1)!}\cdot \lambda^k e^{-\lambda}\\&=\lambda e^{-\lambda}\left( \sum_{k\geq 1}^{}\frac{k-1}{(k-1)!}\lambda^{k-1}+\sum_{k\geq 1}^{}\frac{1}{(k-1)!}\lambda^{k-1} \right)\\&=\lambda e^{-\lambda}\left( \lambda\sum_{k\geq 2}^{}\frac{1}{(k-2)!}\lambda^{k-2}+\sum_{k\geq 1}^{}\frac{1}{(k-1)!}\lambda^{k-1} \right)\\&=\lambda e^{-\lambda}(\lambda e^{\lambda}+e^{\lambda})=\lambda^{2}+\lambda\end{aligned}$$Hence $\text{Var}(X)=\lambda$.
10. $X\sim \mathcal{N}(\mu,\sigma^{2})$. Let $Y:=X-\mu$. Then, $$\text{Var}(X)=\mathbb{E}[Y^{2}]$$ where: $$\mathbb{E}[Y^{2}]=\frac{1}{\sqrt{ 2\pi \sigma^{2} }}\int_{-\infty}^{\infty}y^2  \exp \left( -\frac{y^{2}}{2\sigma^{2}} \right) \, dy $$
11. $X\sim \text{Uni}([a,b])$ Then, $$\mathbb{E}[X^{2}]=\frac{1}{b-a}\int_{a}^{b} x^{2} \, dx=\frac{b^3-a^3}{3(b-a)}=\frac{b ^{2}+ab+a^{2}}{3} $$Therefore, $$\text{Var}(X)=\mathbb{E}[X^{2}]-\mathbb{E}[X]^{2}=\frac{b^2+ab+a^{2}}{3}-\frac{(b+a)^{2}}{4}=\frac{4b ^{2}+4ab+4 a^{2}-3b ^{2}-6ab-3 a^{2}}{12}=\frac{(b-a)^{2}}{12}$$
12. $X\sim \text{Exp}(\lambda)$, we have: $$\begin{aligned}\mathbb{E}[X^{2}]&=-\int_{0}^{\infty} x^{2} (-\lambda\exp(-\lambda x)) \, dx\\&=-[x^{2} \exp(-\lambda x)]^\infty_{0}- \frac{2}{\lambda}\int_{0}^{\infty} x (-\lambda\exp(-\lambda x) )\, dx\\&=-[x^{2} \exp(-\lambda x)]^\infty_{0}- \frac{2}{\lambda}[x\exp(-\lambda x)]^\infty_{0}+ \frac{2}{\lambda}\int_{0}^{\infty} \exp(-\lambda x) \, dx\\&=-[x^{2} \exp(-\lambda x)]^\infty_{0}- \frac{2}{\lambda}[x\exp(-\lambda x)]^\infty_{0}+ \frac{2}{\lambda}\int_{0}^{\infty} \exp(-\lambda x) \, dx \end{aligned}$$
---
#### 2. Joint and Marginal Distributions

1. 