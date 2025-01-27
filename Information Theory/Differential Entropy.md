#Definition #InformationTheory 

> [!definition]
> We have that: 
> 1. ***Differential entropy*** if given by: $$h(X):=\mathbb{E}_{X}[\log f(X)]$$
---
##### Properties
> [!lemma] Proposition 
> Let $X\in \mathbb{R}^n$ with density $f$. Then, for $A\in \text{GL}(n,\mathbb{R})$, 
> 1. $h(AX)=h(X)+\log \left| \det A \right|$

> [!proof]-
> We have that:
> 1. Let $Y:= AX$. Then, $$f_{Y}(y)=\frac{1}{\left| \det A \right| }f_{X}(A^{-1}y)$$Hence, $$\begin{align}h(Y)&=\int_{\mathbb{R}^n} \frac{1}{\left| \det A \right| }f_{X}(A^{-1}y)\left( \log \left| \det A \right| -\log f_{X}(A^{-1}y) \right)  \, dy\\&=\int_{\mathbb{R}^n} f_{X}(x)\left( \log \left| \det A \right| -\log f_{X}(x) \right)  \, dx\\&=h(X)+\log \left| \det A \right| \end{align} $$
---
> [!lemma] Theorem (AEP)

> [!proof]-
> We have that: $$\begin{align}Y&:=-\frac{1}{n}\log f(X_{1},\dots,X_{n})-h(X)\\&=-\frac{1}{n}\sum_{i=1}^{n}\left( -\frac{1}{2}\log 2\pi\sigma^{2}-\frac{(X_{i}-\mu)^{2}}{2\sigma^{2}} \right)- \frac{1}{2}(\log 2\pi e\sigma^{2})\\&=-\frac{1}{2}+\frac{1}{2n}\sum_{i=1}^{n}\left( \frac{X_{i}-\mu}{\sigma} \right)^{2}\\&=\frac{1}{2n}\left( \sum_{i=1}^{n}\left( \frac{X_{i}-\mu}{\sigma} \right) ^{2}-n \right) \end{align}$$By noting $Z_{i}:=(X_{i}-\mu) / \sigma$, we have: $$Y=\frac{1}{2n}\left( \sum_{i=1}^{n}Z_{i}^{2}-n \right)=\frac{1}{2n}\left( \chi^2_{n}-n \right)$$Hence, $$f_{Y}(y)=2nf_{\chi^2_{n}}(n(2y+1))$$
---
> [!lemma] Theorem (Fano's Inequality)
> Let $X$ be a random variable. Let $\tau^{2}:=\mathbb{E}[(X-\widehat{X})^{2}]$ where $\widehat{X}$ is some estimate of $X$. 
> 1. if $X,\widehat{X}$ are independent, then: $\tau^{2}\geq \frac{1}{2\pi e}2^{2h(X)}$.
> 2. if $\widehat{X}$ depends on some side information $Y$, then: $\tau^{2}\geq \frac{1}{2\pi e}2^{2h(X|Y)}$.

> [!proof]-
> We have that: 
> 1. Notice: $$\begin{align}\tau^{2}&=\mathbb{E}[(X-\widehat{X})^{2}]\\&=\mathbb{E}[(X-\mu -(\widehat{X}-\mu))^{2}]\\&=\mathbb{E}[(X-\mu)^{2}]-2\mathbb{E}[(X-\mu)(\widehat{X}-\mu)]+\mathbb{E}[(\widehat{X}-\mu)^{2}]\\&=\text{Var}(X)+\mathbb{E}[(\widehat{X}-\mu)^{2}]\\&\geq \text{Var}(X)\end{align}$$Since Gaussian RVs maximize the differential entropy among all RV with the same variance, $$h(X)\leq \frac{1}{2}\log_{2}(2\pi e\text{Var}(X))$$Hence, $2^{2h(X)}\leq 2\pi e \text{Var}(X)$ and: $$\tau^{2}\geq \frac{1}{2\pi e}2^{2h(X)}$$
> 2. We have: $$\begin{align}\tau^{2}&=\mathbb{E}[(X-\widehat{X})^{2}]\\&=\mathbb{E}_{Y}[\mathbb{E}[(X-\widehat{X})^{2}|Y]]\\&\geq \frac{1}{2\pi e}\mathbb{E}_{Y}[2^{2h(X|Y)}]\\&\geq \frac{1}{2\pi e}2^{2\mathbb{E}_{Y}[h(X|Y)]}\\&=\frac{1}{2\pi e}2^{2h(X|Y)}\end{align}$$
---
##### Examples

> [!h] Example 1
> We have that:
> 1. for $X\sim \text{Exp}(\lambda)$, $h(X)=-\log\lambda+1$.
> 2. for $X\sim \text{Laplace}(\lambda)$, $h(X)=\log \frac{2e}{\lambda}$.

> [!proof]-
> We have: 
> 1. Notice that: $$\begin{align}h(X)&=-\int_{[0,\infty)}\lambda e^{-\lambda x} (\log \lambda-\lambda x) \, dx \\&=-\lambda\log \lambda \int_{0}^{\infty} e^{-\lambda x} \, dx +\lambda \int_{0}^{\infty} xe^{-\lambda x} \, dx \\&=-\log \lambda +1\end{align}$$
> 2. Notice that: $$\begin{align}h(X)&=-\frac{\lambda}{2}\int_{\mathbb{R}}^{} e^{-\lambda \left| x \right| }\left( \log \frac{\lambda}{2}-\lambda \left| x \right|  \right) \, dx \\&=-\frac{\lambda}{2}\int_{0}^{\infty} e^{-\lambda x}\left( \log \frac{\lambda}{2}-\lambda x \right)  \, dx -\frac{\lambda}{2}\int_{-\infty}^{0} e^{\lambda x}\left( \log \frac{\lambda}{2}+\lambda x \right)  \, dx\\&= \end{align}$$
---
