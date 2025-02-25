#Series #AGAO 

#### Problem 1
Let $A\in \text{Mat}_{n,n}(\mathbb{R})$ be symmetric. Then, it admits a decomposition $A=Q\Lambda Q^\top$ where $Q$ is orthogonal and $\Lambda$ is diagonal. Therefore, $$\|A\|=\|Q\Lambda Q^\top\|=\|\Lambda Q^\top\|=\|Q\Lambda^\top\|=\|\Lambda^\top\|=\|\Lambda\|=\sup_{\|x\|=1}\|\Lambda x\|$$and where we use the orthogonality of $Q$ and the fact that induced norm is invariant under transposition, given by Hahn-Banach. 

We claim that $\sup_{\|x\|=1}\|\Lambda x\|= \max_{i}|\lambda_{i}|=\max(\left| \lambda_{\max}(A) \right|,\left| \lambda_{\min}(A) \right|)$. 

Let $j\in[n]$ s.t. $\left| \lambda_{j} \right|=\max_{i}\left| \lambda_{i} \right|$. Then, $\|\Lambda e_{j}\|=\left| \lambda_{j} \right|$ and $\sup_{\|x\|=1}\left\| \Lambda x \right\|\geq \max_{i}\left| \lambda_{i} \right|$. Conversely, for any $\|x\|=1$, we have that: $$\left\| \Lambda x \right\| ^{2}=\sum_{i=1}^{n}\left| \lambda_{i} \right|^{2} x_{i}^{2}\leq \left| \lambda_{j} \right| ^{2}\sum_{i=1}^{n}x_{i}^{2}=\left| \lambda_{j} \right| ^{2}$$Hence, $\left\| \Lambda x \right\|\leq \max_{i}\left| \lambda_{i} \right|$ for all $x$ with $\|x\|=1$ and we have the statement.

If the steps above are unclear:
1. Claim 1: for an orthogonal matrix $A\in \text{Mat}_{n,n}(\mathbb{R})$, for any vector $x\in \mathbb{R}^n$, $$\|Ax\|_{2}^2=x^\top A^\top Ax=x^\top x=\|x\|^2_{2}$$
2. In particular, for any matrix $B\in \text{Mat}_{n,n}(\mathbb{R})$, $$\|AB\|=\sup_{\|x\|=1}\|ABx\|_{2}=\sup_{\|x\|=1}\|Bx\|_{2}=\|B\|$$

Now, consider $$A:=\begin{bmatrix}0&2\\0 &0\end{bmatrix}$$Then, the eigenvalues of $A$ are only zero. However, for $x=(0,1)$, we have $\|Ax\|_{2}=2>0$.

---
#### Problem 2
Assume $f$ is $\beta$-gradient Lipschitz. Let $x\in S$ and $\delta$ small s.t. $x+\delta\in S$ and consider $g:[0,1]\to \mathbb{R}^n$ given by $g(t):=\nabla f(x+t\delta)$, which is differentiable on $(0,1)$. Hence, by mean value theorem, there exists $t\in(0,1)$ and $z:=x+t\delta$ s.t. $$\nabla f(y)-\nabla f(x)=g(1)-g(0)=\nabla g(t)=H_{f}(z)(y-x)$$By Cauchy-Schwarz, we get: $$\|\nabla f(x+\delta)-\nabla f(x)\|_{2}=\|H_{f}(x+t\delta)\delta\|_{2}\leq \beta\|\delta\|_{2}$$