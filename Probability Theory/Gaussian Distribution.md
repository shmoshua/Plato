#Definition #ProbabilityTheory 

> [!definition]
> A [[random variable]] $X:\Omega\to \mathbb{R}^d$ has a ***Gaussian distribution*** with mean $\mu\in \mathbb{R}^d$ and a [[Symmetric Positive Definite Matrices|SPD]] matrix $\Sigma\in \mathbb{R}^{d,d}$ called the covariance matrix, if the [[Density|density]] is given as: $$p(x)=\frac{1}{\sqrt{ (2\pi)^d \det \Sigma }}\exp \left( -\frac{1}{2}(x-\mu)^\top\Sigma ^{-1}(x-\mu) \right) $$and denoted by $X\sim \mathcal{N}(\mu,\Sigma)$. 
- **Remark**: If $d=1$, then we have $p(x)=\frac{1}{\sigma\sqrt{ 2\pi }}\exp\left( -\frac{(x-\mu)^{2}}{2\sigma^{2}} \right)$.
---
##### Properties
> [!lemma] Proposition 1 (Basic Properties)
> Let $X\sim \mathcal{N}(\mu,\Sigma)$.
> 1. $p$ is indeed a density function. 
> 2. $\mathbb{E}[X]=\mu$

> [!proof]+
> We have that:
> 1. As $\Sigma$ is SPD, we have an eigendecomposition $\Sigma=USU^\top$ where $U$ is orthogonal and $S=\text{diag}(s_{1},\dots,s_{d})$. Then, as $\Sigma$ is SPD, $s_{1},\dots,s_{d}>0$ and $\Sigma ^{-1}=US^{-1}U^\top$ is well defined. Set $y:=x-\mu$ we have that $$(x-\mu)^\top\Sigma ^{-1}(x-\mu)=y^\top US^{-1}\underbrace{ U^\top y }_{ =:z }=z^\top S^{-1}z=\frac{z_{1}^{2}}{s_{1}}+\dots+\frac{z_{d}^{2}}{s_{d}}$$Therefore, 
>    $$\begin{align}\int _{\mathbb{R}^d} \exp \left( -\frac{1}{2}(x-\mu)^\top\Sigma ^{-1}(x-\mu) \right)\, dx&=\int _{\mathbb{R}^d} \exp \left( -\frac{z_{1}^{2}}{2s_{1}}-\dots-\frac{z_{d}^{2}}{2s_{d}}\right)\, dx\\&=\int _{\mathbb{R}^d} \exp \left( -\frac{z_{1}^{2}}{2s_{1}}-\dots-\frac{z_{d}^{2}}{2s_{d}}\right)\, \left| \det(U^\top) \right| dz\\&=\prod_{i\in [d]}^{}\int_{\mathbb{R}}^{} \exp \left( -\frac{z_{i}^{2} }{2s_{i}}\right)  \, dz_{i} \\&=\prod_{i\in [d]}^{}\sqrt{ 2s_{i} }\int_{\mathbb{R}}^{} \exp \left( -u_{i}^{2}\right)  \, du_{i} \\&=\sqrt{ (2\pi)^{d}\det S }\\&=\sqrt{ (2\pi)^d \det\Sigma } \end{align}$$as $\Sigma$ and $S$ are similar.
> 2. We have that: $$\begin{align}\mathbb{E}[X_{i}]&=\int_{\mathbb{R}}^{} x_{i}p_{i}(x_{i}) \, dx_{i}\\&= \int_{\mathbb{R^d}}^{} x_{i}p(x) \, dx \\&=\frac{1}{\sqrt{ (2\pi)^d \det \Sigma }}\int_{\mathbb{R}^d}^{} x_{i}\exp \left( -\frac{1}{2}(x-\mu)^\top\Sigma ^{-1}(x-\mu) \right)\, dx\\&=\frac{1}{\sqrt{ (2\pi)^d \det \Sigma }}\int_{\mathbb{R}^d}^{} (y_{i}+\mu_{i})\exp \left( -\frac{1}{2}y^\top\Sigma ^{-1}y \right)\, dy\\&=\frac{1}{\sqrt{ (2\pi)^d \det \Sigma }}\int_{\mathbb{R}^d}^{} (Uz+\mu_{i})\exp \left( -\frac{z_{1}^{2}}{2s_{1}}-\dots-\frac{z_{d}^{2}}{2s_{d}}\right)\, dz \end{align}$$$$\begin{align}\mathbb{E}[X]\end{align}$$
