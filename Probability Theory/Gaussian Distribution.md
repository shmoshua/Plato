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
> 5. the [[entropy]] is given by $H(p)=\frac{1}{2}\ln \left| 2\pi e\Sigma \right|$

^6f6281

We have that: $$\begin{align}H(p)&=\mathbb{E}[-\log p]\\&=\mathbb{E}\left[ \frac{d}{2}\log(2\pi)+\frac{1}{2}\log \det\Sigma+\frac{1}{2}(x-\mu)^\top\Sigma ^{-1}(x-\mu) \right] \\&=\frac{d}{2}\log(2\pi)+\frac{1}{2}\log \det\Sigma+\frac{1}{2}\mathbb{E}[(x)]\end{align}$$


> [!proof]-
> We have that:
> 1. As $\Sigma$ is SPD, we have an eigendecomposition $\Sigma=USU^\top$ where $U$ is orthogonal and $S=\text{diag}(s_{1},\dots,s_{d})$. Then, as $\Sigma$ is SPD, $s_{1},\dots,s_{d}>0$ and $\Sigma ^{-1}=US^{-1}U^\top$ is well defined. Set $y:=x-\mu$ we have that $$(x-\mu)^\top\Sigma ^{-1}(x-\mu)=y^\top US^{-1}\underbrace{ U^\top y }_{ =:z }=z^\top S^{-1}z=\frac{z_{1}^{2}}{s_{1}}+\dots+\frac{z_{d}^{2}}{s_{d}}$$Therefore, 
>    $$\begin{align}\int _{\mathbb{R}^d} \exp \left( -\frac{1}{2}(x-\mu)^\top\Sigma ^{-1}(x-\mu) \right)\, dx&=\int _{\mathbb{R}^d} \exp \left( -\frac{z_{1}^{2}}{2s_{1}}-\dots-\frac{z_{d}^{2}}{2s_{d}}\right)\, dx\\&=\int _{\mathbb{R}^d} \exp \left( -\frac{z_{1}^{2}}{2s_{1}}-\dots-\frac{z_{d}^{2}}{2s_{d}}\right)\, \left| \det(U^\top) \right| dz\\&=\prod_{i\in [d]}^{}\int_{\mathbb{R}}^{} \exp \left( -\frac{z_{i}^{2} }{2s_{i}}\right)  \, dz_{i} \\&=\prod_{i\in [d]}^{}\sqrt{ 2s_{i} }\int_{\mathbb{R}}^{} \exp \left( -u_{i}^{2}\right)  \, du_{i} \\&=\sqrt{ (2\pi)^{d}\det S }\\&=\sqrt{ (2\pi)^d \det\Sigma } \end{align}$$as $\Sigma$ and $S$ are similar.
> 2. We have that: $$\mathbb{E}[X]=\mathbb{E}[Y+\mu]=\mathbb{E}[Y]+\mu=\mathbb{E}[UZ]+\mu=U\mathbb{E}[Z]+\mu=\mu$$where: $$\mathbb{E}[Z_{i}]=c\int_{\mathbb{R}^d}^{} z_{i}\exp \left( -\frac{z^{2}_{1}}{2s_{1}} -\dots -\frac{z^{2}_{d}}{2s_{d}} \right)  \, dz=0 $$
>    as $\int_{\mathbb{R}}^{} t\exp(-t^{2}) \, dt=0$ where $c$ is the normalization constant.
> 3. We have that: $$\begin{align}\mathbb{V}[X]:=\mathbb{E}[(X-\mu)(X-\mu)^\top]&=\mathbb{E}[YY^\top]\\&=\mathbb{E}[UZZ^\top U^\top]\\&=U\mathbb{E}[Z Z^\top]U^\top\end{align}$$where: $$\begin{align}\mathbb{E}[Z_{i}Z_{j}]=\frac{1}{\sqrt{ (2\pi)^d \det \Sigma }}\int_{\mathbb{R}^d}^{} z_{i}z_{j}\exp \left( -\frac{z^{2}_{1}}{2s_{1}} -\dots -\frac{z^{2}_{d}}{2s_{d}} \right)  \, dz \end{align}$$which is $0$ if $i\neq j$. However, if $i=j$, then: $$\begin{align}\mathbb{E}[Z_{i}^{2}]&=\frac{1}{\sqrt{ (2\pi)^d \det \Sigma }}\int_{\mathbb{R}^d}^{} z_{i}^{2}\exp \left( -\frac{z^{2}_{1}}{2s_{1}} -\dots -\frac{z^{2}_{d}}{2s_{d}} \right)  \, dz\\&=\frac{1}{\sqrt{ 2\pi s_{i}}}\int_{\mathbb{R}}^{} z_{i}^{2}\exp\left( -\frac{z_{i}^{2}}{2s_{i}} \right) \, dz_{i}\\&=\frac{2s_{i}}{\sqrt{ \pi }}\int_{\mathbb{R}}^{} u_{i}^{2}\exp\left( -u_{i}^{2} \right) \, du_{i} \\&=s_{i}\end{align}$$
>    
>    Therefore, $\mathbb{E}[ZZ^\top]=S$ and $\mathbb{V}[X]=USU^\top=\Sigma$.
> 4. First, we show it for $X \sim \mathcal{N}(0,I)$. Then, we have: $$\begin{align}\Phi_{X}(\xi)&=\mathbb{E}[\exp(i\xi^\top X)]\\&=\frac{1}{\sqrt{ (2\pi)^d}}\int_{\mathbb{R}^d}\exp\left( i\xi^\top x-\frac{1}{2}x^\top x \right)  \, dx \\&=\frac{1}{\sqrt{ (2\pi)^d}}\int_{\mathbb{R}^d}\exp\left( i\sum_{i=1}^{d}\xi_{i}x_{i}-\frac{1}{2}\sum_{i=1}^{d}x_{i}^{2}\right)  \, dx\\&=\prod_{i=1}^{d}\int_{\mathbb{R}} \frac{1}{\sqrt{ 2\pi }}\exp\left( i\xi_{i}x_{i}-\frac{1}{2}x_{i}^{2}\right)  \, dx_{i}\\&=\prod_{i=1}^{d}\exp\left( -\frac{\xi_{i}^{2}}{2} \right) \\&=\exp \left( -\frac{1}{2}\xi^\top \xi \right) \end{align}$$ Now, for a general $X \sim \mathcal{N}(\mu,\Sigma)$, we have that $X=\mu+\sqrt{ \Sigma } Z$ where $Z \sim \mathcal{N}(0,I)$. Therefore, $$\begin{align}\Phi_{X}(\xi)&=\mathbb{E}[\exp(i\xi^\top (\mu+\sqrt{ \Sigma }Z))]\\&=\exp(i\xi^\top\mu)\mathbb{E}[\exp(i\xi^\top\sqrt{ \Sigma }Z)]\\&=\exp(i\xi^\top\mu)\Phi_{Z}(\sqrt{ \Sigma }^\top\xi)\\&=\exp\left( i\xi^\top\mu-\frac{1}{2}\xi^\top\Sigma \xi \right)\end{align}$$

^6af1ff

---
> [!lemma] Proposition 2 (Marginals and Conditionals are Gaussian)
> Let $X:\Omega\to \mathbb{R}^m,Y:\Omega\to \mathbb{R}^n$ s.t. $$(X,Y)\sim \mathcal{N}\left((\mu_{X},\mu_{Y}),\begin{bmatrix}\Sigma_{XX}&\Sigma_{XY}\\\Sigma_{XY}^\top&\Sigma_{YY}\end{bmatrix}\right)$$ where $\mu_{A}:=\mathbb{E}[A]$ and $\Sigma_{AB}:=\text{Cov}(A,B)$ for all $A,B\in \{ X,Y \}$. Then,
> 1. $X \sim \mathcal{N}(\mu_{X},\Sigma_{XX}), Y\sim \mathcal{N}(\mu_{Y},\Sigma_{YY})$
> 2. $X|Y=y\sim \mathcal{N}(\mu_{X}+\Sigma_{XY}\Sigma_{YY}^{-1}(y-\mu_{Y}),\Sigma_{XX}-\Sigma_{XY}\Sigma_{YY}^{-1}\Sigma_{XY}^\top)$

^e649b0

> [!proof]-
> We have:
> 1. Using the [[characteristic function]]: $$\begin{align}\Phi_{X}(\xi)&=\Phi_{X,Y}(\xi,0)\\&=\exp \left( i\xi^\top\mu_{X}-\frac{1}{2}\xi^\top \Sigma_{XX}\xi\right)\end{align}$$Therefore, $X \sim \mathcal{N}(\mu_{X},\Sigma_{XX})$. 
> 2. Let's define $X':=X - \mu_{X}$ and $Y':=Y-\mu_{Y}$. Let $A\in \text{Mat}_{m,n}(\mathbb{R})$ and we define $Z:=X'-AY'$. Then, $$\begin{align}\mathbb{E}[ZY'^\top]&=\mathbb{E}[(X'-AY')Y'^\top]\\&=\mathbb{E}[X'Y'^\top-AY'Y'^\top]\\&=\Sigma_{XY}-A\Sigma_{YY}\end{align}$$Therefore, for $A:=\Sigma_{XY}\Sigma_{YY}^{-1}$, $\text{Cov}(Z,Y')=0$. Hence, for $X'=AY'+Z$, we have: $$\begin{align}\Phi_{X'|Y'}(\xi|y')&=\mathbb{E}[\exp(i\xi^\top X')|Y'=y']\\&=\mathbb{E}[\exp(i\xi^\top AY')\exp(i\xi^\top Z)|Y'=y']\\&=\mathbb{E}[\exp(i\xi^\top Ay')\exp(i\xi^\top Z)]\\&=\mathbb{E}[\exp(i\xi^\top Ay')]\mathbb{E}[\exp(i\xi^\top Z)]\\&=\exp(i\xi^\top Ay')\exp \left( -\frac{1}{2}\xi^\top\Sigma_{Z}\xi \right)  \end{align}$$where$$\Sigma_{Z}=\Sigma_{XX}+A\Sigma_{YY}A^\top-2\Sigma_{XY}A^\top=\Sigma_{XX}-\Sigma_{XY}A^\top=\Sigma_{XX}-\Sigma _{XY}\Sigma_{YY}^{-1}\Sigma_{XY}^\top$$Hence, $X'|Y'=y' \sim \mathcal{N}(\Sigma_{XY}\Sigma_{YY}^{-1}y',\Sigma_{XX}-\Sigma _{XY}\Sigma_{YY}^{-1}\Sigma_{XY}^\top)$. Then, $$\begin{align}\Phi_{X|Y}(\xi|y)&=\mathbb{E}[\exp \left( i \xi^\top X \right)|Y=y ]\\&=\mathbb{E}[\exp \left( i \xi^\top (X'+\mu_{X}) \right)|Y'=y-\mu_{Y} ]\\&=\exp(i\xi^\top(\mu_{X}+A(y-\mu_{Y})))\exp \left( -\frac{1}{2}\xi^\top\Sigma_{Z}\xi \right)   \end{align}$$which gives us $X|Y=y \sim \mathcal{N}(\mu_{X}+\Sigma_{XY}\Sigma_{YY}^{-1}(y-\mu_{Y}),\Sigma_{XX}-\Sigma _{XY}\Sigma_{YY}^{-1}\Sigma_{XY}^\top)$. 
>    
>    
>    

^bf26eb

---
> [!lemma] Proposition 3 (Basic Operations of Gaussian is Gaussian)
> Let $X \sim \mathcal{N}(\mu,\Sigma)$. Then, for a matrix $M$:
> 1. $MX\sim \mathcal{N}(M\mu,M\Sigma M^\top)$
> 2. for $X' \sim \mathcal{N}(\mu',\Sigma')$ s.t. $X,X'$ are independent, $X+X' \sim \mathcal{N}(\mu+\mu',\Sigma+\Sigma')$

^061ea5

> [!proof]-
> We have: 
> 1. Let $Y:=MX$, then we have: $$\begin{align}\Phi_{Y}(\xi)&=\mathbb{E}[\exp(i\xi^\top MX)]\\&=\Phi_{X}(M^\top \xi)\\&=\exp \left( i\xi^\top M\mu-\frac{1}{2}\xi^\top M\Sigma M^\top \xi \right) \end{align}$$Hence, $MX \sim \mathcal{N}(M\mu,M\Sigma M^\top)$.
> 2. We have that: $$\begin{align}\Phi_{X+X'}(\xi)&=\mathbb{E}[\exp(i\xi^\top(X+X'))]\\&=\mathbb{E}[\exp(i\xi^\top X)]\mathbb{E}[\exp(i\xi^\top X')]\\&=\exp \left( i\xi^\top(\mu+\mu')-\frac{1}{2}\xi^\top(\Sigma+\Sigma')\xi \right) \end{align}$$and $X+X' \sim \mathcal{N}(\mu+\mu',\Sigma+\Sigma')$.

^89a1c5

---
> [!lemma] Proposition 4 (Absolute Value of Gaussian)
> Let $Z \sim \mathcal{N}(m,\sigma^{2})$. Then, 
> 1. $\mathbb{E}[\left| Z \right|]=\sigma\sqrt{ \frac{2}{\pi} }+\frac{m\sqrt{ \pi }}{\sigma}$

> [!proof]-
> We have:$$\begin{align}\mathbb{E}[\left| Z \right| ]&=\frac{2}{\sqrt{ 2\pi \sigma^{2} }}\int_{0}^{\infty} z e^{-(z-m)^{2}/2\sigma^{2}} \, dz\\&=\frac{2}{\sqrt{ 2\pi \sigma^{2} }}\int_{0}^{\infty} (z+m) e^{-z^{2}/2\sigma^{2}} \, dz\\&=\frac{2}{\sqrt{ 2\pi \sigma^{2} }}\left( \int_{0}^{\infty} z e^{-z^{2}/2\sigma^{2}} \, dz +m\int_{0}^{\infty} e^{-z^{2}/2\sigma^{2}} \, dz  \right)\\&=\frac{2}{\sqrt{ 2\pi \sigma^{2} }}\left( \sigma^{2}+\frac{m\pi }{\sqrt{ 2 }} \right)\\&=\sigma\sqrt{ \frac{2}{\pi} }+\frac{m\sqrt{ \pi }}{\sigma}\end{align}$$
---