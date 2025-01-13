#Definition #PAI 

> [!definition]
> Let $\mathcal{P}$ be a family of distributions and $\mathcal{Q}\subseteq \mathcal{P}$ a subfamily called ***variational family***. Then, 
> 1. the ***variational inference*** of $p\in \mathcal{P}$ is given by: $$\mathcal{q}^{*}\in \underset{ q\in \mathcal{Q} }{ \arg\min }\  D(q\|p)$$where $D(q\|p)$ is the [[relative entropy]] of $q$ and $p$. 
- **Remark**: Common variational families are Gaussian distributions, Gaussian distributions with diagonal covariance, etc.
