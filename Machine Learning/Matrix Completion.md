#Definition #ML 

> [!definition]
> Let $A\in \mathbb{R}^{m,n}$ and $\Omega\in \{ 0,1 \}^{m,n}$ be matrices. The ***matrix completion problem*** is to solve the following optimization problem: $$\underset{ \widehat{A}\in \mathbb{R}^{m,n} }{ \arg\min } \frac{1}{2}\left\| (A-\widehat{A})\odot \Omega\right\|^{2}_{F} $$

---
##### Properties
> [!lemma] Proposition 1 (Rank-1 and Full Observability)
> Let $\Omega=1$. Then, $$\underset{u\in \mathbb{R}^m ,v\in \mathbb{R}^n}{ \arg\min } \underbrace{ \frac{1}{2}\left\| A-uv^\top\right\|^{2}_{F} }_{ =: \ell(u,v) } $$
> 1. is a non-convex optimization problem.
> 2. $\underset{u\in \mathbb{R}^m ,v\in \mathbb{R}^n}{ \arg\min } \ell(u,v)= \underset{u\in \mathbb{R}^m ,v\in \mathbb{R}^n}{ \arg\min } \frac{1}{2}\|u\|^{2}_{2}\|v\|^{2}_{2}-u^\top Av$
> 3. the optimum is given by $\sigma_{1}u_{1},v_{1}$ where $u_{1},v_{1}$ are the first left and right singular vectors. 


> [!proof]-
> We have that:
> 1. Let $\ell(u,v):=  \frac{1}{2}\left\| A-uv^\top\right\|^{2}_{F}$. Then, $$\frac{ \partial \ell}{ \partial u }=(uv^\top-A)v,\quad \frac{ \partial \ell }{ \partial v } =(v u ^\top - A^\top) u$$and: $$\text{H}_{\ell}(u,v)=\begin{bmatrix}\|v\|^{2}\cdot 1_{n\times n}&2uv^\top - A\\(2uv^\top - A)^\top&\|u\|^{2}\cdot 1_{m\times m}\end{bmatrix}$$Hence, $\text{H}_{\ell}(0,0)=\begin{bmatrix} 0&-A\\-A^\top& 0\end{bmatrix}$. Therefore, $\text{Tr}(\text{H}_{\ell}(0,0))=0=\sum_{i}^{}\lambda_{i}(\text{H}_{\ell}(0,0))$ and either $\text{H}_{\ell}(0,0)=0$ which implies that $A=0$ or we have $\text{H}_{\ell}(0,0)\not \geq  0$. This shows that we have a non-convex problem.
> 2. We have that: $$\begin{aligned}\underset{u\in \mathbb{R}^m ,v\in \mathbb{R}^n}{ \arg\min } \frac{1}{2}\left\| A-uv^\top\right\|^{2}_{F}&=\underset{u\in \mathbb{R}^m ,v\in \mathbb{R}^n}{ \arg\min } \frac{1}{2}\text{Tr}((A-uv^\top)(A^\top-vu^\top))\\&=\underset{u\in \mathbb{R}^m ,v\in \mathbb{R}^n}{ \arg\min } \frac{1}{2}\|A\|^{2}_{F}+\frac{1}{2}\|u\|^{2}\|v\|^{2}-u^\top Av\\&= \underset{u\in \mathbb{R}^m ,v\in \mathbb{R}^n}{ \arg\min } \frac{1}{2}\|u\|^{2}_{2}\|v\|^{2}_{2}-u^\top Av\end{aligned}$$
> 3. Let $u':=\alpha u$ and $v':=\beta v$. Then,$$\begin{aligned}\underset{u\in \mathbb{R}^m ,v\in \mathbb{R}^n}{ \arg\min } \frac{1}{2}\|u\|^{2}_{2}\|v\|^{2}_{2}-u^\top Av= \underset{ \alpha,\beta\in \mathbb{R} }{ \arg\min }\left( \frac{\alpha^{2}\beta^{2}}{2}-\alpha\beta\underset{\|u\|^{2}=\|v\|^{2}=1}{ \max }u^\top Av \right)\end{aligned}$$ Now, using Lagrange multipliers, we have: $$\mathcal{L}(u,v;\mu,\xi):=u^\top Av-\mu( u^\top u - 1)-\xi(v^\top v - 1)$$Then, $$\begin{aligned}\frac{ \partial \mathcal{L} }{ \partial u } =v^\top A^\top - 2\mu u^\top\overset{ ! }{ = }0,\quad \frac{ \partial \mathcal{L} }{ \partial v }=u^\top A -2\xi v^\top\overset{ ! }{ = }0\end{aligned}$$as $\|u\|=\|v\|=1$ we have that: $$u=\frac{Av}{\|Av\|},\quad v=\frac{A^\top u}{\left\| A^\top u \right\| }$$Combining the two equations, we get that $u$ needs to be a unit eigenvector of $AA ^\top$ and $v$ a unit eigenvector of $A^\top A$. Now, $$\underset{\|u\|^{2}=\|v\|^{2}=1}{ \max }u^\top Av =\frac{u^\top A A^\top u}{\left\| A^\top u \right\| }=\sqrt{ u^\top A A^\top u }=\sigma_{1}\|u\|=\sigma_{1}$$Finally, $$\underset{ \alpha,\beta\in \mathbb{R} }{ \arg\min }\left( \frac{\alpha^{2}\beta^{2}}{2}-\alpha\beta \cdot \sigma_{1} \right)=\underset{ \alpha\in \mathbb{R} }{ \arg\min }\left( \frac{\alpha^{2}}{2}-\alpha \cdot \sigma_{1} \right)$$is optimized when $\alpha=\sigma_{1}$. This proves the statement.

- **Remark**: The left right singular vectors can be found using [[Principal Component Analysis|power iteration]] on $AA^\top$ and $A^\top A$. 

---
> [!lemma] Proposition 2 (ALS)
> Consider the regularized objective $\ell(U,V)$: $$\underset{U\in \mathbb{R}^{n\times k} ,V\in \mathbb{R}^{k\times m}}{ \arg\min }\frac{1}{2}\left\|(A-UV)\odot \Omega \right\|^{2}_{F}  +\frac{\lambda}{2}(\left\| U \right\| ^{2}_{F}+\left\| V \right\| ^{2}_{F})$$
> 1. $\ell(U,V)$ is a polynomial of degree 4 in the following monomials:
> 	1. $\omega_{ij}u_{ir}v_{rj}u_{is}v_{sj}$ for $1\leq r,s\leq k$ and
> 	2. $w_{ij}u_{ir}v_{rj}$ for $1\leq r\leq k$ and
> 	3. $u^{2}_{ir},v^{2}_{rj}$
> 2. In particular, higher order terms only involve exactly one row index $i$ of $U$ and column index $j$ of $V$. 
> 3. Modulo treating $U$ as a constant, we can isolate the objective w.r.t $v_{j}$: $$\ell_{U}(v_{j}):= \frac{1}{2}v_{j}^\top\left( \sum_{i\in[k]} \omega_{ij}u_{i}u_{i}^\top+\lambda I_{k} \right)v_{j}-\sum_{i\in[k]}^{}\omega_{ij}a_{ij}u_{i}^\top v_{j}$$
> 4. this gives rise to ***alternating least squares (ALS)***: $$V^{t+1}\gets \underset{ V }{ \arg\min }\ \ell(U^t,V),\quad U^{t+1}\gets \underset{ U }{ \arg\min }\ \ell(U,V^{t+1})$$

> [!proof]-
> We have that 1.2. are easy to check. Now, treating $U$ as a constant, $$\left\| (A-UV)\odot \Omega \right\|^{2}_{F}=\sum_{i,j}^{}\omega_{ij}(a_{ij}-u_{i}^\top v_{j} )^{2}=\sum_{i,j}^{}\omega_{ij}(a_{ij}^{2}-2u_{i}^\top v_{j}+v_{j}^\top u_{i}u_{i}^\top v_{j} )$$Further, $\left\| V \right\|^{2}_{F}=\sum_{j=1}^{m}v_{j}^\top v_{j}$. This shows the statement. Now, if we try to optimize $\ell_{U}(v_{j})$, we get that: $$\frac{ \partial \ell_{U} }{ \partial v_{j} } =v_{j}^\top\left( \sum_{i\in[k]}\omega_{ij}u_{i}u_{i}^\top +\lambda I_{k} \right)-\left( \sum_{i\in[k]}^{} \omega_{ij}a_{ij}u_{i}^\top \right)  $$and we can solve the lsq problem: $$v_{j}^{*}:=\left( \sum_{i\in[k]}\omega_{ij}u_{i}u_{i}^\top +\lambda I_{k} \right)^{-1}\left( \sum_{i\in[k]}^{} \omega_{ij}a_{ij}u_{i}\right) $$
> 
> 
> 
- **Remark**: In ALS, the objective will monotonically decrease and converges to a fixed point, i.e. $\nabla \ell(U^{*},V^{*})=0$ but might be a saddle point. 
- **Remark**: ALS also has the advantage of easy augmentation of the model increaisng $n$ or $m$ by one. Just increase one LS problem.
---
> [!lemma] Proposition 3 (Projected Gradient Descent)
> The ***projected gradient descent*** is the following iterative algorithm: $$A^0\gets 0,\quad A^{t+1}\gets \text{BestRa}$$