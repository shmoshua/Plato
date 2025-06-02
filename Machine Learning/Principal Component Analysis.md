#Definition #ML 

> [!lemma] Theorem 1 (Principal Component Analysis)
> Consider the following loss function: $$R(P):=\frac{1}{2}\mathbb{E}[\left\| x-Px \right\| ^{2}_{2}]$$where $P$ is a self-adjoint projection. Then, if $\mathbb{E}[x]=0$, 
> 1. $R(P)=\frac{1}{2}(\text{Var}(x)-\text{Var}(Px))$
> 2. $R(P)=\frac{1}{2}(\text{Var}(x)-\text{tr}(P\mathbb{E}[x x^\top]))$, in particular $\mathbb{E}[x x^\top]$ is a sufficient statistic for $\text{Var}(Px)$.
> 3. We have that: $$U U^\top = \underset{ \begin{array}{c}P: P^{2}=P,P=P^\top\\\text{rnk}(P)\leq m\end{array}}{ \arg\min }R(P)$$where $U$ is the $m$ principal orthogonal eigenvectors of $\mathbb{E}[xx^\top]$. 

> [!proof]+
> We have that:
> 1. Consider: $$\begin{aligned}R(P)=\frac{1}{2}\mathbb{E}[\left\| x-Px \right\| ^{2}_{2}]=\frac{1}{2}\mathbb{E}[\|x\|^{2}_{2}]+\frac{1}{2}\mathbb{E}[\left\| Px \right\| ^{2}_{2}]-\underbrace{ \mathbb{E}\left[ \braket{ x , P^{2}x }  \right]  }_{ =\mathbb{E}[\braket{ Px , Px } ]=\mathbb{E}[\left\| Px \right\| ^{2}_{2}] }=\frac{1}{2}(\mathbb{E}[\|x\|^{2}_{2}-\left\| Px \right\| ^{2}_{2}])\end{aligned}$$The rest follows from the fact that $\mathbb{E}[x]=0$.
> 2. We have that: $$\text{Var}(Px)=\mathbb{E}[\left\| Px \right\| ^{2}_{2}]=\mathbb{E}[\braket{ x , P^{2}x } ]=\mathbb{E}[\braket{ x , Px } ]=\mathbb{E}[\text{tr}(Pxx^\top )]=\text{tr}(P\mathbb{E}[xx^\top])$$
> 3. Assume that $\mathbb{E}[x x^\top]=\text{diag}(\lambda_{1},\dots, \lambda_{n})$ where $\lambda_{1}\geq\dots\geq \lambda_{n}\geq 0$. Then, we have that $U:=[I_{m}|0]^\top$. Then, as $$\left\| P \right\| $$
