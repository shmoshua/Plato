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

> [!proof]+
> We have that: $$\begin{align}Y&:=-\frac{1}{n}\log f(X_{1},\dots,X_{n})-h(X)\\&=-\frac{1}{n}\sum_{i=1}^{n}\left( -\frac{1}{2}\log 2\pi\sigma^{2}-\frac{(X_{i}-\mu)^{2}}{2\sigma^{2}} \right)- \frac{1}{2}(\log 2\pi e\sigma^{2})\\&=-\frac{1}{2}+\frac{1}{2n}\sum_{i=1}^{n}\left( \frac{X_{i}-\mu}{\sigma} \right)^{2}\\&=\frac{1}{2n}\left( \sum_{i=1}^{n}\left( \frac{X_{i}-\mu}{\sigma} \right) ^{2}-n \right) \end{align}$$By noting $Z_{i}:=(X_{i}-\mu) / \sigma$, we have: $$Y=\frac{1}{2n}\left( \sum_{i=1}^{n}Z_{i}^{2}-n \right)=\frac{1}{2n}\left( \chi^2_{n}-n \right)$$where 
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
