#Definition #ML 

> [!lemma] Theorem 1 (Principal Component Analysis)
> Consider the following loss function: $$R(P):=\frac{1}{2}\mathbb{E}[\left\| x-Px \right\| ^{2}_{2}]$$where $P$ is a self-adjoint projection. Then, if $\mathbb{E}[x]=0$, 
> 1. $R(P)=\frac{1}{2}(\text{Var}(x)-\text{Var}(Px))$
> 2. $R(P)=\frac{1}{2}(\text{Var}(x)-\text{tr}(P\mathbb{E}[x x^\top]))$, in particular $\mathbb{E}[x x^\top]$ is a sufficient statistic for $\text{Var}(Px)$.
> 3. We have that: $$U U^\top = \underset{ \begin{array}{c}P: P^{2}=P,P=P^\top\\\text{rnk}(P)\leq m\end{array}}{ \arg\min }R(P)$$where $U$ is the $m$ principal orthogonal eigenvectors of $\mathbb{E}[xx^\top]$. 

> [!proof]-
> We have that:
> 1. Consider: $$\begin{aligned}R(P)=\frac{1}{2}\mathbb{E}[\left\| x-Px \right\| ^{2}_{2}]=\frac{1}{2}\mathbb{E}[\|x\|^{2}_{2}]+\frac{1}{2}\mathbb{E}[\left\| Px \right\| ^{2}_{2}]-\underbrace{ \mathbb{E}\left[ \braket{ x , P^{2}x }  \right]  }_{ =\mathbb{E}[\braket{ Px , Px } ]=\mathbb{E}[\left\| Px \right\| ^{2}_{2}] }=\frac{1}{2}(\mathbb{E}[\|x\|^{2}_{2}-\left\| Px \right\| ^{2}_{2}])\end{aligned}$$The rest follows from the fact that $\mathbb{E}[x]=0$.
> 2. We have that: $$\text{Var}(Px)=\mathbb{E}[\left\| Px \right\| ^{2}_{2}]=\mathbb{E}[\braket{ x , P^{2}x } ]=\mathbb{E}[\braket{ x , Px } ]=\mathbb{E}[\text{tr}(Pxx^\top )]=\text{tr}(P\mathbb{E}[xx^\top])$$
> 3. From $P^{2}=P$, we have that $\text{Spec}(P)=\{ 0,1 \}$ as $$\lambda v=Pv=P^{2}v=\lambda Pv=\lambda^{2}v$$and $\lambda=\lambda^{2}$ for any eigenvalue $\lambda:=\lambda(P)$. Therefore, for the eigendecomposition $P=V \Lambda V^\top$, we have that we can decompose $P=V'V'^\top$ where $V'\in \mathbb{R}^{n,m}$ and $V'^\top V'$ has a leading $I_{\text{rnk}(P)}$. Hence, $$ \underset{ \begin{array}{c}P: P^{2}=P,P=P^\top\\\text{rnk}(P)\leq m\end{array}}{ \arg\min }R(P)\geq  \underset{ \begin{array}{c}V\in \mathbb{R}^{n,m}:V=[v_{1}|\dots|v_{r}|0|\dots|0]\\V_{1:r}^\top V_{1:r}=I_{r}\end{array}}{ \arg\min }\ R(V V^\top)$$where the other inequality follows from the fact that: $$V V^\top V V^\top = [V_{1:r}|0]\begin{bmatrix}I_{r}&0\\0&0 \end{bmatrix}\begin{bmatrix}V_{1:r}^\top\\0\end{bmatrix}=VV^\top$$Therefore, it suffices to show that: $U U^\top = \underset{ \begin{array}{c}V\in \mathbb{R}^{n,m}:V=[v_{1}|\dots|v_{r}|0|\dots|0]\\V_{1:r}^\top V_{1:r}=I_{r}\end{array}}{ \arg\max } \text{tr}(V V^\top \Lambda)$
>    
>    Now, assume that $\mathbb{E}[x x^\top]=\text{diag}(\lambda_{1},\dots, \lambda_{n})$ where $\lambda_{1}\geq\dots\geq \lambda_{n}\geq 0$. Then, we have that $U:=[I_{m}|0]^\top$. Then, for $V\in \mathbb{R}^{n,m}$ with $V=[v_{1}|\dots|v_{r}|0]$ and $V_{1:r}^\top V_{1:r}=I_{r}$ we have that: $$\text{tr}(V V^\top \Lambda)=\sum_{i\in[n]}^{}(V V^\top \Lambda)_{ii}=\sum_{i\in[n]}^{}\lambda_{i}\underbrace{ \sum_{j\in[m]}^{}V_{ij}^{2} }_{ =: \omega_{i} }=\sum_{i\in[n]}^{}\lambda_{i}\omega_{i}$$Further, we have that: $$\sum_{i\in[n]}^{}\omega_{i}=\left\| V \right\| ^{2}_{F}=\text{tr}(VV^\top)=\text{tr}(V^\top V)=r\leq m$$Therefore, the argmax is given if $\omega_{i}=1$ for all $i\in[m]$. This is given by $V:=U$. 
>    
>    Now, for any general $\mathbb{E}[x x^\top]$, as it is SPD, we have that $\mathbb{E}[xx^\top]=Q \Lambda Q^\top$ for some orthogonal $Q$. Then, $$\begin{aligned}\underset{ \begin{array}{c}V\in \mathbb{R}^{n,m}:V=[v_{1}|\dots|v_{r}|0|\dots|0]\\V_{1:r}^\top V_{1:r}=I_{r}\end{array}}{ \arg\max } \text{tr}(V V^\top Q\Lambda Q^\top)&=\underset{ \begin{array}{c}V\in \mathbb{R}^{n,m}:V=[v_{1}|\dots|v_{r}|0|\dots|0]\\V_{1:r}^\top V_{1:r}=I_{r}\end{array}}{ \arg\max } \text{tr}(Q^\top V V^\top Q\Lambda)\\&=Q\cdot \underset{ \begin{array}{c}V\in \mathbb{R}^{n,m}:V=[v_{1}|\dots|v_{r}|0|\dots|0]\\V_{1:r}^\top V_{1:r}=I_{r}\end{array}}{ \arg\max } \text{tr}(W W^\top\Lambda)\\&=QU\end{aligned}$$where $U$ is the principal orthogonal eigenvectors of $\Lambda$.

---
> [!lemma] Proposition 2 (Power Method)
>  Let $A\in \mathbb{R}^{n,n}$ be a diagonalizable matrix with $\lambda_{1}(A)> \lambda_{2}(A)\geq\dots\geq \lambda_{n}(A)\geq 0$ with a unique principal component $u_{1}$. 
>  1. for $v_{0}\in \mathbb{R}^n$, if $\braket{ v_{0} , u_{1} }\neq0$, then: $$v^{t+1}:=\frac{Av^t}{\left\| Av^t \right\| }$$converges to $u_{1}$ with computational complexity $O(Tn^{2})$ after $T$ iterations.
>  2. By iteratively finding the principal component of $A_{i}:=A - \sum_{j< i}^{}\lambda_{j} u_{j}u_{j}^\top$ using the power method, we can find the $m$ principal components in time $O(Tn^{2}m)$.

> [!proof]-
> We have:
> 1. The runtime is easy to see. Now, let $A=\sum_{i\in [n]}^{}\lambda_{i} u_{i}u_{i}^\top$. Then, $v^0=\sum_{i}^{}\alpha_{i}u_{i}$ where $\alpha_{1}\neq 0$ as $\braket{ v^0 , u_{1} }\neq 0$. Hence, $$v^k \propto \sum_{i\in[n]}^{}\lambda_{i}^k\alpha_{i}u_{i} \propto \alpha_{1}u_{1}+\sum_{i\geq 2} \alpha_{i}\left( \frac{\lambda_{i}}{\lambda_{1}} \right) ^k u_{i}$$where $0\leq \lambda_{i} / \lambda_{1}< 1$. Hence, as $v^k$ is normal, $v^k \to u_{1}$.
> 2. Obvious.
- **Remark**: In PCA, as we find the principal components of $\mathbb{E}[xx^\top]$ which takes $O(Nn^{2})$ time to compute where $N$ is the number of data points, we have the total runtime $O(Tn^{2}m+Nn^{2})$.

---
> [!lemma] Proposition 3 (SGD)
> We find $W,V$ by: $$V\gets V - \eta (I-P)xx^\top W^\top, \quad W\gets W-\eta V^\top(I-P)xx^\top$$where $x$ is either chosen u.a.r. from the data or $x \sim \mathcal{D}$. 


> [!proof]+
> We have that:
> $$\begin{aligned}\nabla _{V} \left\| x-VWx \right\| ^{2}_{2}=\nabla _{V}\left\| (I-VW)x \right\| ^{2}_{2}=(I-P)xx^\top W^\top\\\nabla _{W} \left\| x-VWx \right\| ^{2}_{2}=\nabla _{W}\left\| (I-VW)x \right\| ^{2}_{2}=V^\top(I-P)xx^\top \end{aligned}$$