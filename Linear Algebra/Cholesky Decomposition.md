#Definition #LinearAlgebra 

> [!definition]
> Let $A\in \text{Mat}_{n,n}(\mathbb{C})$ be [[Hermitian]], [[positive semi-definite]].
> 1. The ***Cholesky decomposition*** is given as: $$A=LL^{*}$$where $L$ is a lower triangular matrix where the diagonal entries are real and non-negative.
---
##### Properties
> [!lemma] Theorem 1 (Existence and Uniqueness of Cholesky Decomposition)
> Let $A$ be Hermitian positive semi-definite. Then,
> 1. a Cholesky decomposition exists.
> 2. if $A$ is positive definite, $L$ has positive entries on the diagonal and $L$ is unique.
> 3. if $A$ is real, $L$ is also real.

> [!proof]-
> We have that:
> 1. We show it using induction over $n$. 
> 	1. if $n=1$, then by positive semi-definiteness, $A=[a]$ where $a\geq 0$. Therefore, by setting $\ell=\sqrt{ a }$, we have that $a=\ell^{2}$.
> 	2. for $n>1$, we can partition $A$ as follows: $$A=\begin{bmatrix}\alpha_{11}&a_{21}^{*}\\a_{21}&A_{22}\end{bmatrix},\quad \alpha_{11}\in \mathbb{C}$$Then, we first claim that $\alpha_{11}$ is real from $A$ being Hermitian and also non-negative as: $\alpha_{11}=e_{1}^\top A e_{1}\geq 0$. Now, let $\ell_{21}:=a_{21} / \sqrt{ \alpha_{11} }$. Then, 
> 		1. **Claim: $A_{22}-\ell_{21}\ell_{21}^{*}$ is Hermitian positive semidefinite.**
> 		   One easily sees that $A_{22}-\ell_{21}\ell_{21}^{*}$ is Hermitian. Let $x\in \mathbb{C}^{n-1}$ be non-zero. Then, define: $x':=(\chi_{1},x)\in \mathbb{C}^n$ where $\chi_{1}:=-\frac{1}{\alpha_{11}}a_{21}^{*}x$. Then, we get: $$\begin{align}0\leq x'^\top Ax'&=x'^\top\begin{bmatrix}0\\ \left( -\frac{1}{\alpha_{11}}a_{21}a_{21}^{*}+A_{22} \right)x\end{bmatrix}\\&=x^\top\left( A_{22}-\ell_{21}\ell_{21}^{*} \right) x\end{align}$$
> 	
> 		Therefore, there exists a Cholesky composition $L_{22}$ s.t. $A_{22}-\ell_{21}\ell_{21}^{*}=L_{22}L_{22}^{*}$. Then, $$L:=\begin{bmatrix}\sqrt{ \alpha_{11} }&0\\ \ell_{21}&L_{22}\end{bmatrix}$$we have that it is lower triangular with diagonal entries real and non-negative. Lastly, $$\begin{align}L L^{*}&=\begin{bmatrix}\alpha_{11}&\sqrt{ \alpha_{11} }\ell_{21}^{*}\\\sqrt{ \alpha_{11} }\ell_{21}&\ell_{21}\ell_{21}^{*}+L_{22}L_{22}^{*}\end{bmatrix}=A\end{align}$$
> 2. Analogous as above except that $\sqrt{ \alpha_{11} }>0$. For uniqueness, let $K$ be another such lower triangular matrix. Then, $$LL^{*}=KK^{*}$$as $L$ has positive entries on the diagonal, $\det L>0$ and we have: $$I=L^{-1}K K^{*} (L^{-1})^{*}=(L^{-1}K)(L^{-1}K)^{*}$$Therefore, $(L^{-1}K) = ((L^{-1}K)^{-1})^{*}$ and as $L^{-1}K$ is lower triangular, we have that $L^{-1}K$ is diagonal. However, as $I=(L^{-1}K)(L^{-1}K)^{*}$, we have that $L^{-1}K$ only has $\pm 1$ as entries. However, from the positive diagonal assumption, we have that $L^{-1}K=I$ and $L=K$.
> 3. Analogous as above except $\ell_{21}$ is real. 
---