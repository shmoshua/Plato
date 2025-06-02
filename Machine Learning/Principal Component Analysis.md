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
> 3. Assume that $\mathbb{E}[x x^\top]=\text{diag}(\lambda_{1},\dots, \lambda_{n})$ where $\lambda_{1}\geq\dots\geq \lambda_{n}\geq 0$. Then, we have that $U:=[I_{m}|0]^\top$. Then,
> 	1. From $P^{2}=P$, we have that $\text{Spec}(P)=\{ 0,1 \}$ as $$\lambda v=Pv=P^{2}v=\lambda Pv=\lambda^{2}v$$and $\lambda=\lambda^{2}$ for any eigenvalue $\lambda:=\lambda(P)$. Therefore, for the eigendecomposition $P=V \Lambda V^\top$, we have that we can decompose $P=V'V'^\top$ where $V'\in \mathbb{R}^{n,m}$ and $V'^\top V'$ has a leading $I_{\text{rnk}(P)}$. Hence, $$ \underset{ \begin{array}{c}P: P^{2}=P,P=P^\top\\\text{rnk}(P)\leq m\end{array}}{ \arg\min }R(P)\geq  \underset{ \begin{array}{c}V\in \mathbb{R}^{n,m}:V=[v_{1}|\dots|v_{r}|0|\dots|0]\\V_{1:r}^\top V_{1:r}=I_{r}\end{array}}{ \arg\min }\ R(V V^\top)$$where the other inequality follows from the fact that: $$V V^\top V V^\top = [V_{1:r}|0]\begin{bmatrix}I_{r}&0\\0&0 \end{bmatrix}\begin{bmatrix}V_{1:r}^\top\\0\end{bmatrix}=V$$
> 	   
> 	   Therefore, $\left\| P \right\|\leq 1$.
> 	2. 
