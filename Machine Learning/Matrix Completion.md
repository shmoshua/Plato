#Definition #ML 

> [!definition]
> Let $A\in \mathbb{R}^{m,n}$ and $\Omega\in \{ 0,1 \}^{m,n}$ be matrices. The ***matrix completion problem*** is to solve the following optimization problem: $$\underset{ \widehat{A}\in \mathbb{R}^{m,n} }{ \arg\min } \frac{1}{2}\left\| (A-\widehat{A})\odot \Omega\right\|^{2}_{F} $$

---
##### Properties
> [!lemma] Proposition 1 (Rank-1 and Full Observability)
> Let $\Omega=1$. Then, $$\underset{u\in \mathbb{R}^m ,v\in \mathbb{R}^n}{ \arg\min } \frac{1}{2}\left\| A-uv^\top\right\|^{2}_{F} $$
> 1. is a non-convex optimization problem.
> 2. $\underset{u\in \mathbb{R}^m ,v\in \mathbb{R}^n}{ \arg\min } \frac{1}{2}\left\| A-uv^\top\right\|^{2}_{F}= \underset{u\in \mathbb{R}^m ,v\in \mathbb{R}^n}{ \arg\min } \frac{1}{2}\|u\|^{2}_{2}\|v\|^{2}_{2}-u^\top Av$

> [!proof]+
> We have that:
> 1. Let $\ell(u,v):=  \frac{1}{2}\left\| A-uv^\top\right\|^{2}_{F}$. Then, $$\frac{ \partial \ell}{ \partial u }=(uv^\top-A)v,\quad \frac{ \partial \ell }{ \partial v } =(v u ^\top - A^\top) u$$and: $$\text{H}_{\ell}(u,v)=\begin{bmatrix}\|v\|^{2}\cdot 1_{n\times n}&2uv^\top - A\\(2uv^\top - A)^\top&\|u\|^{2}\cdot 1_{m\times m}\end{bmatrix}$$Hence, $\text{H}_{\ell}(0,0)=\begin{bmatrix} 0&-A\\-A^\top& 0\end{bmatrix}$. Therefore, $\text{Tr}(\text{H}_{\ell}(0,0))=0=\sum_{i}^{}\lambda_{i}(\text{H}_{\ell}(0,0))$ and either $\text{H}_{\ell}(0,0)=0$ which implies that $A=0$ or we have $\text{H}_{\ell}(0,0)\not \geq  0$. This shows that we have a non-convex problem.
> 2. We have that: $$\begin{aligned}\underset{u\in \mathbb{R}^m ,v\in \mathbb{R}^n}{ \arg\min } \frac{1}{2}\left\| A-uv^\top\right\|^{2}_{F}&=\underset{u\in \mathbb{R}^m ,v\in \mathbb{R}^n}{ \arg\min } \frac{1}{2}\text{Tr}((A-uv^\top)(A^\top-vu^\top))\\&=\underset{u\in \mathbb{R}^m ,v\in \mathbb{R}^n}{ \arg\min } \frac{1}{2}\|A\|^{2}_{F}+\frac{1}{2}\|u\|^{2}\|v\|^{2}-\text{Tr}(u^\top Avuv^\top A^\top)\\&=\left\| A-uv^\top\right\|^{2}_{F}\\&= \underset{u\in \mathbb{R}^m ,v\in \mathbb{R}^n}{ \arg\min } \frac{1}{2}\|u\|^{2}_{2}\|v\|^{2}_{2}-u^\top Av\end{aligned}$$