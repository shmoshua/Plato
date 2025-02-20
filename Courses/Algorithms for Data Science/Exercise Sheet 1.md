#Algorithms #Series 

#### 1. Quadratic Regression
Let $\varphi:[d]\times[d]\to [d^{2}]$ be a bijection given by $\varphi(i,j)=(i-1)d+j$. Then, we define $\beta ^{*}\in \mathbb{R}^{d^{2}}$ to be the vectorized counterparts of $(f^{*}_{ij})_{i,j\in [d]}$, i.e. $$\beta ^{*}_{\varphi(i,j)}=f^{*}_{ij},\quad \forall i,j\in[d]$$Then, by defining $\Phi\in \mathbb{R}^{n,d^{2}}, \Phi_{k,\varphi(i,j)}=x^{(k)}_{i}x^{(k)}_{j}$ we get that: $$(\Phi\beta ^{*})_{k}=\sum_{1\leq i,j\leq d}^{}x^{(k)}_{i}x^{(k)}_{j}f^{*}_{ij}=f^{*}(x^{(k)})$$Let $\widehat{\beta}:\mathbb{R}^n\to \mathbb{R}^{d^{2}}$ then be the least square estimator for $y=\Phi\beta ^{*}+w$ with $w\sim \mathcal{N}(0,I_{n})$. Let $\widehat{f}:= \Phi\widehat{\beta}$. Then, it follows that: $$\begin{align}\frac{1}{n}\mathbb{E}\left[ \sum_{k=1}^{n}(\widehat{f}(y)_{k}-f^{*}(x^{(k)}))^{2} \right] &=\frac{1}{n}\mathbb{E}\left[ \sum_{k=1}^{n}((\Phi\widehat{\beta}(y))_{k}-(\Phi\beta ^{*})_{k})^{2} \right]\\&=\frac{1}{n}\mathbb{E}[\left\| \Phi\widehat{\beta}(y)-\Phi \beta ^{*} \right\| ^{2}]=\frac{\text{rk}(\Phi)}{n}\leq \frac{d^{2}}{n}\end{align} $$as $\Phi\in \mathbb{R}^{n,d^{2}}$.

---
#### 2. Nuclear and Frobenius norm for Low-Rank

Let $X\in \mathbb{R}^{n,d}$ with $\text{rk}(X)=:r$. Then, by Cauchy-Schwarz$$\left\| X \right\| _{*}^{2}=\left( \sum_{i=1}^{r}\sigma_{i} \right) ^{2}\leq r\left( \sum_{i=1}^{r}\sigma_{i}^{2} \right) =r\left\| X \right\| _{F}^{2}$$

---
#### 3. Second Moment of Random Unit Vectors
Let $U\in \text{SO}(d)$ be an orthogonal matrix. Then, $y:=Ux \sim \text{Uniform}(S^{d-1})$ if $x\sim \text{Uniform}(S^{d-1})$. Then, we get that:$$\mathbb{E}[xx^\top]U=\mathbb{E}[yy^\top]U=\mathbb{E}[Uxx^\top U^\top]U=U\mathbb{E}[xx^\top],\quad \forall U\in \text{SO}(d)$$i.e. $\mathbb{E}[xx^\top]$ commutes with all rotation matrices. Let $A:=\mathbb{E}[xx^\top]$. 


We claim that $A$ has to be a scalar multiple of the identity. Consider the inclusion $\pi:\text{SO}(d)\hookrightarrow \text{GL}(d,\mathbb{R})$. Then, this is 


---
