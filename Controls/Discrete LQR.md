#Definition #Project

> [!definition]
> A ***discrete-time linear quadratic regulator*** in infinite-horizon setting is defined as the system dynamic: 
> 1. $x_{0}=x_{\text{init}}$
> 2. $x_{t+1}=A x_{t}+Bu_{t}$ for all $t\geq 0$
> 
> where $\{ x_{t} \}_{t=0}^T\subseteq \mathbb{R}^n$,  $A\in \mathbb{R}^{n,n}$ and $B\in \mathbb{R}^{n,m}$ are given and we aim to find $\{ u_{t} \}_{t=0}^T\subseteq \mathbb{R}^m$ s.t. the **quadratic loss function** $$J:=\sum_{t=0}^{\infty}(x_{t}^\top Qx_{t}+u_{t}^\top Ru_{t}+2x_{t}^\top N x_{t})$$and the optimal control is given by: $$u_{t}:=-F x_{t}$$
> where $$F=(R+B^\top PB)^{-1}(B^\top PA+N^\top)$$and $P$ is the unique positive definite solution to the [[discrete algebraic Riccati equation]]:$$P=A^\top PA-(A^\top PB+N)(R+B^\top PB)^{-1}(B^\top PA+N^\top)+Q$$

---
> [!definition]
> A ***discrete-time linear quadratic regulator*** in infinite-horizon setting is defined as the optimization problem:
> $$\begin{align}\min_{u}&&& \frac{1}{2}\sum_{t=0}^{\infty}(x_{t}^\top Qx_{t}+u_{t}^\top Ru_{t})\\ \text{subject to}&&&x_{t+1}=A x_{t}+Bu_{t}&\forall t \geq 0\\&&&\end{align}$$ where $Q,R$ are [[Symmetric Matrices|symmetric]].

This can be rewritten using the [[Lagrange multipliers]] as $\min_{u}J(u)$ where:
$$J(u):= \frac{1}{2}\sum_{t=0}^{\infty}(x_{t}^\top Qx_{t}+u_{t}^\top Ru_{t})+\lambda_{t}^\top (Ax_{t}+Bu_{t}-x_{t+1})$$Then, using the partial derivatives, we have for all $t\geq 0$: 
$$\begin{align}\frac{ \partial J }{ \partial x_{t} } &=x_{t}^\top Q+\lambda_{t}^\top A-\lambda^\top_{t-1}\overset{ ! }{ = }0\\\frac{ \partial J }{ \partial u_{t} } &=u_{t}^\top R+\lambda_{t}^\top B\overset{ ! }{ = }0
\\\frac{ \partial J }{ \partial \lambda_{t} } &=(Ax_{t}+B u_{t}-x_{t+1})^\top\overset{ ! }{ = }0\end{align}$$
Therefore, we have $u_{t}=-R^{-1}B^\top \lambda_{t}$. Rewriting the rest of the equations, we get: 

$$\begin{bmatrix}x_{t+1}\\\lambda_{t}\end{bmatrix}=\underbrace{ \begin{bmatrix}A+BR^{-1}B^\top A^{-\top}Q&-BR^{-1} B^\top A^{-\top}\\-A^{-\top}Q&A^{-\top} \end{bmatrix} }_{ =:\mathcal{M}_{1} }\begin{bmatrix}x_{t}\\\lambda_{t-1}\end{bmatrix}$$and
$$\begin{bmatrix}x_{t+1}\\\lambda_{t+1}\end{bmatrix}=\underbrace{ \begin{bmatrix}A&-BR^{-1}B^\top\\-A^{-\top}QA&A^{-\top}(I+QBR^{-1}B^\top)\end{bmatrix} }_{ =:\mathcal{M}_{2} }\begin{bmatrix}x_{t}\\\lambda_{t}\end{bmatrix}$$

As $k \to \infty$, we want $x_{k} \to 0$.
Then, using the [[Schur Decomposition| Schur decomposition]], we have for $i\in\{ 1,2 \}$:
$$\mathcal{M}_{i}=U_{i}T_{i}U_{i}^\top$$where $U_{i}$ is orthogonal and $T_{i}$ is upper-triangular. We can write the matrices $U_{i}$ and $T_{i}$ in blocks as well:
$$U_{i}:=\begin{bmatrix}^{11}U_{i}&^{12}U_{i}\\^{21}U_{i}&^{22}U_{i}\end{bmatrix},\quad T_{i}:=\begin{bmatrix}^{1}T_{i}&^{2}T_{i}\\0&^{3}T_{i}\end{bmatrix}$$
where $^1T_{i},^3T_{i}$ are upper-triangular matrices. Then, all eigenvalues of $^1T_{i}$ are all the eigenvalues of $\mathcal{ M}_{i}$ with an absolute value less than 1.

$$u_{t }:= -R^{-1}B U_{21}U_{11}^{-1}x_{t}$$

