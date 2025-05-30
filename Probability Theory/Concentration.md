#Definition #AGAO 

> [!definition]

---
##### Properties
> [!lemma] Theorem 1 (Bernstein)
> Let $X_{1},\dots,X_{k}$ be independent, zero-mean real random variables iwth $\left| X_{i} \right|\leq R$. For $X:= \sum_{i}^{}X_{i}$ and $\sigma^{2}:= \text{Var}(X)$, we have: $$\mathbb{P}(\left| X \right| \geq t)\leq 2\exp \left( -\frac{t^{2}}{2Rt+4\sigma^{2}} \right),\quad \forall t>0 $$

> [!proof]-
> We have that for any $\theta>0$: $$\mathbb{P}(X\geq t)=\mathbb{P}(\exp(\theta X)\geq \exp(\theta t))\leq \exp(-\theta t)\mathbb{E}[\exp(\theta X)]$$Now, if $\theta\leq \frac{1}{R}$, then: $$\exp(z)\leq 1+z+z^{2},\quad \forall \left| z \right| \leq 1$$Therefore, $$\begin{aligned}\mathbb{E}[\exp(\theta X)]=\mathbb{E}\left[ \exp\left( \theta \sum_{i}^{}X_{i} \right) \right]=\mathbb{E}\left[ \prod_{i}^{}\exp(\theta X_{i}) \right]=\prod_{i}^{}\mathbb{E}[\exp(\theta X_{i})]\leq \prod_{i}^{}\mathbb{E}[1+\theta X_{i}+\theta^{2}X_{i}^{2}]\end{aligned}$$As $X_i$ are zero mean, $$\mathbb{E}[\exp(\theta X)]\leq \prod_{i}^{}(1+\theta^{2}\mathbb{E}[X^{2}_{i}])\leq \prod_{i}^{}\exp \left( \theta^{2}\mathbb{E}[X^{2}_{i}] \right)=\exp \left( \theta^{2}\sum_{i}^{}\mathbb{E}[X_{i}^{2}] \right)  =\exp(\theta^{2}\sigma^{2})$$Therefore, $\mathbb{P}(X\geq t)\leq \exp(-\theta t+\theta^{2}\sigma^{2})$. Now, $\frac{ \partial  }{ \partial \theta }(-\theta t+\theta^{2}\sigma^{2})=-t+2\theta\sigma^{2}=0$ implies $\theta=\frac{t}{2\sigma^{2}}$. Hence,
> 1. if $\frac{t}{2\sigma^{2}}\leq 1/R$, then $\mathbb{P}(X\geq t)\leq \exp\left( -\frac{t^{2}}{4\sigma^{2}} \right)$
> 2. if $\frac{t}{2\sigma^{2}}> 1 / R$, then by setting $\theta=1 / R$ and $-\theta t+\theta^{2}\sigma^{2}\leq - t / 2R$
>    
>  Bringing the two cases together, we have that there exists $\theta$ s.t. $$-\theta t+\theta^{2}\sigma^{2}\leq -\min\left( \frac{t}{2R},\frac{t^{2}}{4\sigma^{2}} \right)\leq-\frac{t^{2}}{2Rt+4\sigma^{2}} $$
> 
---
> [!lemma] Theorem 2 (Matrix Bernstein)
> Let $X_{1},\dots,X_{k}\in \mathbb{R}^{n,n}$ be independent, symmetric random variables with $\mathbb{E}[X_{i}]=0$ and $\left\| X_{i} \right\|\leq R$. Then, for $X:= \sum_{i}^{}X_{i}$ and $\sigma^{2}=\left\| \text{Var}(X) \right\|$ we have that: $$\mathbb{P}(\left\| X \right\| \geq t)\leq 2n\exp \left( -\frac{t^{2}}{2Rt+4\sigma^{2}} \right) ,\quad \forall t>0$$

> [!proof]-
> Let $\lambda_{1}\leq\dots\leq \lambda_{n}$ be the eigenvalues of $X$. $$\mathbb{P}(\left\| X \right\| \geq t)=\mathbb{P}(\lambda_{n}\geq t \lor -\lambda_{1}\geq t)\leq \mathbb{P}(\lambda_{n}\geq t)+\mathbb{P}(-\lambda_{1}\geq t)$$By considering $Y:= -X$, wlog we may assume that $\mathbb{P}(-\lambda_{1}\geq t)=\mathbb{P}(\lambda_{n}\geq t)$. We have that: $$\mathbb{P}(\lambda_{n}\geq t)=\mathbb{P}(\exp(\theta\lambda_{n})\geq \exp(\theta t))\leq \mathbb{P}(\text{Tr}(\exp(\theta X))\geq \exp(\theta t))\leq \exp(-\theta t)\mathbb{E}[\text{tr}(\exp(\theta X))]$$Now, $$\begin{aligned}\mathbb{E}[\text{tr}(\exp(\theta X))]&=\mathbb{E}_{X_{1:k-1}}[\mathbb{E}_{X_{k}}[\text{tr}(\exp(\theta X_{<k}+\theta X_{k}))]]\\&\leq\mathbb{E}_{X_{1:k-1}}[\text{tr}(\exp(\theta X_{<k}+\log \mathbb{E}[\exp(\theta X_{k})]))]\\&\leq\mathbb{E}_{X_{1:k-1}}[\text{tr}(\exp(\theta X_{<k}+\log \mathbb{E}[I+\theta X_{k}+\theta^{2}X_{k}^{2}]))]\\&\leq\mathbb{E}_{X_{1:k-1}}[\text{tr}(\exp(\theta X_{<k}+\log \mathbb{E}[I+\theta^{2}X_{k}^{2}]))]\\&\leq\mathbb{E}_{X_{1:k-1}}[\text{tr}(\exp(\theta X_{<k}+\theta^{2}\mathbb{E}[X_{k}^{2}]))]\\&\vdots\\&\leq \text{tr}\left( \exp\left( \theta^{2}\sum_{i}\mathbb{E}[X^{2}_{i}] \right) \right)\\&\leq \text{tr}(\exp(\theta^{2}\sigma^{2} I))\\&=n\exp(\theta^{2}\sigma^{2})\end{aligned}$$Therefore, $\mathbb{P}(\left\| X \right\|\geq t)\leq 2n\exp(-\theta t+\theta^{2}\sigma^{2})$ and the rest follows analogously to Theorem 1.

---
