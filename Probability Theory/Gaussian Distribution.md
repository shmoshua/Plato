#Definition #ProbabilityTheory 

> [!definition]
> A [[random variable]] $X:\Omega\to \mathbb{R}^d$ has a ***Gaussian distribution*** with mean $\mu\in \mathbb{R}^d$ and covariance matrix $\Sigma\in \mathbb{R}^{d,d}$, if the [[Density|density]] is given as: $$p(x)=\frac{1}{\sqrt{ (2\pi)^d \det \Sigma }}\exp \left( -\frac{1}{2}(x-\mu)^\top\Sigma ^{-1}(x-\mu) \right) $$
- **Remark**: If $d=1$, then we have $p(x)=\frac{1}{\sigma\sqrt{ 2\pi }}\exp\left( -\frac{(x-\mu)^{2}}{2\sigma^{2}} \right)$.
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $p$ is indeed a density function. 

> [!proof]+
> We have that:
> 1. $$\begin{align}\int_{\mathbb{R}^d}^{} p \, dx =\frac{1}{\sqrt{ (2\pi)^d \det \Sigma }}\int _{\mathbb{R}^d} \exp \left( -\frac{1}{2}(x-\mu)^\top\Sigma ^{-1}(x-\mu) \right)\, dx \end{align}$$