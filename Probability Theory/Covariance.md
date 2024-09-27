#Definition #ProbabilityTheory 

> [!definition]
> Let $X,Y\in L^2(\Omega,\mathcal{A},\mathbb{P})$ be real [[Random Variable|random variables]]. The **covariance** of $X,Y$ is given by: $$\begin{align}\text{Cov}(X,Y)&:=\mathbb{E}[(X-\mathbb{E}[X])(Y-\mathbb{E}[Y])]\\&=\mathbb{E}[XY]-\mathbb{E}[X]\mathbb{E}[Y]\end{align}$$ 
- **Related definition**: For $X=(X_{1},\dots,X_{d}):\Omega\to \mathbb{R}^d$ s.t. $\mathbb{E}[\left| X \right|^{2}]<+\infty$, the ***covariance matrix*** is defined as: $\Sigma_{X}=\left( \text{Cov}(X_{i},X_{j}) \right)_{i\in[d],j\in [d]}$
- **Remark**: $\text{Cov}(X,X)=$ [[Variance|$\text{Var}(X)$]].
---
##### Properties
> [!lemma] Proposition 1 (Basic Properties)
> We have that:
> 1. $\left| \text{Cov}(X,Y) \right|\leq \sqrt{ \text{Var}(X)\text{Var(Y)} }$
> 2. $(X,Y)\mapsto \text{Cov}(X,Y)$ is symmetric and bilinear on $L^2(\Omega,\mathcal{A},\mathbb{P})$. 
> 3. The covariance matrix is symmetric positive semidefinite. 
> 4. $\Sigma_{X}=\mathbb{E}[(X-\mathbb{E}[X])(X-\mathbb{E}[X])^\top]$
> 5. For a matrix $A$, $\Sigma_{AX}=A\Sigma_{X}A^\top$
> 6. For a vector $\xi\in \mathbb{R}^d$, $\text{Var}(\xi^\top X)= \xi^\top \Sigma_{X}\xi$

> [!proof]-
> We have:
> 1. [[Expected Value|Cauchy-Schwarz]]
> 2. Symmetry is clear from the definition. Then, $$\begin{align}\text{Cov}(X_{1}+X_{2},Y)&=\mathbb{E}[(X_{1}+X_{2})Y]-\mathbb{E}[X_{1}+X_{2}]\mathbb{E}[Y]\\&=\mathbb{E}[X_{1}Y]+\mathbb{E}[X_{2}Y]-\mathbb{E}[X_{1}]\mathbb{E}[Y]-\mathbb{E}[X_{2}]\mathbb{E}[Y]\\&=\text{Cov}(X_{1},Y)+\text{Cov}(X_{2},Y)\end{align}$$
> 3. $\Sigma_{X}$ is symmetric from 2. Then, for every $\lambda\in \mathbb{R}^d$, $$\lambda^\top\Sigma_{X}\lambda=\sum_{i,j=1}^{d}\lambda_{i}\lambda_{j}\text{Cov}(X_{i},X_{j})=\text{Var}\left( \sum_{i=1}^{d}\lambda_{i}X_{i} \right)\geq 0 $$
> 4. We have for any $i,j$ $$\mathbb{E}[(X_{i}-\mathbb{E}[X_{i}])(X_{j}-\mathbb{E}[X_{j}])]=\text{Cov}(X_{i},X_{j})$$
> 5. We have that: $$\Sigma_{AX}=\mathbb{E}[A(X-\mathbb{E}[X])(X-\mathbb{E}[X])^\top A^\top]=A \Sigma_{X}A^\top$$
> 6. By applying 5 on $\xi^\top$.
---
