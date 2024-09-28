#Definition #ProbabilityTheory 

> [!definition]
> A [[random variable]] $X:\Omega\to \mathbb{R}^d$ has a ***Gaussian distribution*** with mean $\mu\in \mathbb{R}^d$ and a [[Symmetric Positive Definite Matrices|SPD]] matrix $\Sigma\in \mathbb{R}^{d,d}$ called the covariance matrix, if the [[Density|density]] is given as: $$p(x)=\frac{1}{\sqrt{ (2\pi)^d \det \Sigma }}\exp \left( -\frac{1}{2}(x-\mu)^\top\Sigma ^{-1}(x-\mu) \right) $$and denoted by $X\sim \mathcal{N}(\mu,\Sigma)$. 

^a29bbb

- **Remark**: If $d=1$, then we have $p(x)=\frac{1}{\sigma\sqrt{ 2\pi }}\exp\left( -\frac{(x-\mu)^{2}}{2\sigma^{2}} \right)$.
- **Remark**: This can be extended to $\Sigma$ that is positive semidefinite by reducing the dimensionality to $\text{rank}(\Sigma)$.  ^38c683
---
##### Properties
> [!lemma] Proposition 1 (Basic Properties)
> Let $X\sim \mathcal{N}(\mu,\Sigma)$.
> 1. $p$ is indeed a density function. 
> 2. $\mathbb{E}[X]=\mu$
> 3. $\text{Var}[X]=\Sigma$
> 4. the [[characteristic function]] is given by: $$\Phi_{X}(\xi):=\exp \left( i \xi^\top\mu-\frac{1}{2}\xi^\top\Sigma \xi \right) $$

> [!proof]+
> We have that:
> 1. As $\Sigma$ is SPD, we have an eigendecomposition $\Sigma=USU^\top$ where $U$ is orthogonal and $S=\text{diag}(s_{1},\dots,s_{d})$. Then, as $\Sigma$ is SPD, $s_{1},\dots,s_{d}>0$ and $\Sigma ^{-1}=US^{-1}U^\top$ is well defined. Set $y:=x-\mu$ we have that $$(x-\mu)^\top\Sigma ^{-1}(x-\mu)=y^\top US^{-1}\underbrace{ U^\top y }_{ =:z }=z^\top S^{-1}z=\frac{z_{1}^{2}}{s_{1}}+\dots+\frac{z_{d}^{2}}{s_{d}}$$Therefore, 
>    $$\begin{align}\int _{\mathbb{R}^d} \exp \left( -\frac{1}{2}(x-\mu)^\top\Sigma ^{-1}(x-\mu) \right)\, dx&=\int _{\mathbb{R}^d} \exp \left( -\frac{z_{1}^{2}}{2s_{1}}-\dots-\frac{z_{d}^{2}}{2s_{d}}\right)\, dx\\&=\int _{\mathbb{R}^d} \exp \left( -\frac{z_{1}^{2}}{2s_{1}}-\dots-\frac{z_{d}^{2}}{2s_{d}}\right)\, \left| \det(U^\top) \right| dz\\&=\prod_{i\in [d]}^{}\int_{\mathbb{R}}^{} \exp \left( -\frac{z_{i}^{2} }{2s_{i}}\right)  \, dz_{i} \\&=\prod_{i\in [d]}^{}\sqrt{ 2s_{i} }\int_{\mathbb{R}}^{} \exp \left( -u_{i}^{2}\right)  \, du_{i} \\&=\sqrt{ (2\pi)^{d}\det S }\\&=\sqrt{ (2\pi)^d \det\Sigma } \end{align}$$as $\Sigma$ and $S$ are similar.
> 2. We have that: $$\mathbb{E}[X]=\mathbb{E}[Y+\mu]=\mathbb{E}[Y]+\mu=\mathbb{E}[UZ]+\mu=U\mathbb{E}[Z]+\mu=\mu$$where: $$\mathbb{E}[Z_{i}]=c\int_{\mathbb{R}^d}^{} z_{i}\exp \left( -\frac{z^{2}_{1}}{2s_{1}} -\dots -\frac{z^{2}_{d}}{2s_{d}} \right)  \, dz=0 $$
>    as $\int_{\mathbb{R}}^{} t\exp(-t^{2}) \, dt=0$ where $c$ is the normalization constant.
> 3. We have that: $$\begin{align}\mathbb{V}[X]:=\mathbb{E}[(X-\mu)(X-\mu)^\top]&=\mathbb{E}[YY^\top]\\&=\mathbb{E}[UZZ^\top U^\top]\\&=U\mathbb{E}[Z Z^\top]U^\top\end{align}$$where: $$\begin{align}\mathbb{E}[Z_{i}Z_{j}]=\frac{1}{\sqrt{ (2\pi)^d \det \Sigma }}\int_{\mathbb{R}^d}^{} z_{i}z_{j}\exp \left( -\frac{z^{2}_{1}}{2s_{1}} -\dots -\frac{z^{2}_{d}}{2s_{d}} \right)  \, dz \end{align}$$which is $0$ if $i\neq j$. However, if $i=j$, then: $$\begin{align}\mathbb{E}[Z_{i}^{2}]&=\frac{1}{\sqrt{ (2\pi)^d \det \Sigma }}\int_{\mathbb{R}^d}^{} z_{i}^{2}\exp \left( -\frac{z^{2}_{1}}{2s_{1}} -\dots -\frac{z^{2}_{d}}{2s_{d}} \right)  \, dz\\&=\frac{1}{\sqrt{ 2\pi s_{i}}}\int_{\mathbb{R}}^{} z_{i}^{2}\exp\left( -\frac{z_{i}^{2}}{2s_{i}} \right) \, dz_{i}\\&=\frac{2s_{i}}{\sqrt{ \pi }}\int_{\mathbb{R}}^{} u_{i}^{2}\exp\left( -u_{i}^{2} \right) \, du_{i} \\&=s_{i}\end{align}$$
>    
>    Therefore, $\mathbb{E}[ZZ^\top]=S$ and $\mathbb{V}[X]=USU^\top=\Sigma$.
> 4. First, we show it for $X \sim \mathcal{N}(0,I)$. Then, we have: $$\begin{align}\Phi_{X}(\xi)&=\mathbb{E}[\exp(i\xi^\top X)]\\&=\frac{1}{\sqrt{ (2\pi)^d}}\int_{\mathbb{R}^d}\exp\left( i\xi^\top x-\frac{1}{2}x^\top x \right)  \, dx \\&=\frac{1}{\sqrt{ (2\pi)^d\det\Sigma }}\int_{\mathbb{R}^d}\exp\left( i\sum_{i=1}^{d}\xi_{i}x_{i}-\frac{1}{2}\sum_{i=1}^{d}x_{i}^{2}\right)  \, dx\\&=\frac{1}{\sqrt{ (2\pi)^d\det\Sigma }}\int_{\mathbb{R}^d}\exp\left( i\sum_{i=1}^{d}\xi_{i}x_{i}-\frac{1}{2}\sum_{i=1}^{d}x_{i}^{2}\right)  \, dx \end{align}$$ We have that: $$$$$$\Phi_{X}(\xi):=\exp \left( i \xi^\top\mu-\frac{1}{2}\xi^\top\Sigma \xi \right) $$

---
> [!lemma] Proposition 2
> Let $X:\Omega\to \mathbb{R}^m,Y:\Omega\to \mathbb{R}^n$ s.t. $$(X,Y)\sim \mathcal{N}\left((\mu_{X},\mu_{Y}),\begin{bmatrix}\Sigma_{XX}&\Sigma_{XY}\\\Sigma_{XY}&\Sigma_{YY}\end{bmatrix}\right)$$ where $\mu_{A}:=\mathbb{E}[A]$ and $\Sigma_{AB}:=\text{Cov}(A,B)$ for all $A,B\in \{ X,Y \}$. Then,
> 1. $p(x)$

