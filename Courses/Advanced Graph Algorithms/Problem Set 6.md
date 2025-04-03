#Series #AGAO 

#### Problem 1
1. Consider the following matrices
$$A:=\begin{bmatrix}2&0\\0&1\end{bmatrix}, \quad B:=\begin{bmatrix}3&1\\1&2\end{bmatrix}$$where $A$ is obviously positive definite and the eigenvalues of $B$ are $\frac{1}{2}(5\pm \sqrt{ 5 })> 0$.
Then, $B-A=\begin{bmatrix}1&1\\1&1\end{bmatrix}\in S^2_{+}$ as it admits $0,2$ as eigenvalues. However, we have that $$B^{2}-A^{2}=\begin{bmatrix}10&5\\5&5\end{bmatrix}-\begin{bmatrix}4&0\\0&1\end{bmatrix}=\begin{bmatrix}6&5\\5&4\end{bmatrix}$$which has a negative determinant. This shows that $A^{2}\not\preceq B^{2}$.
1. Let $A,B\in S^n_{++}$ s.t. $A\preceq B$. Let $C\in \mathbb{R}^{n,n}$. Then, $$x^\top C(B-A)C^\top x\geq 0\quad \forall x\in \mathbb{R}^{n}$$Hence, $CAC^\top \preceq CBC^\top$.
   
   First, we have that $x^\top A x\leq x^\top B x$ for any $x$. Now, for any $y\in R^n$, by setting $x:= A^{-1/2}y$, we have that: $$y^\top y\leq y^\top A^{-1 /2}BA^{-1/2} y$$Hence, $I\preceq A^{-1/2}BA^{-1/2}$. Therefore, $\lambda_{i}(A^{-1/2}BA^{-1/2})\geq 1$ for all $i\in[n]$ and $$\lambda_{i}(A^{1/2}B^{-1}A^{1/2})= \frac{1}{\lambda_{i}(A^{-1/2}BA^{-1/2})}\leq 1$$Let $Q:= A^{1/2}B^{-1}A^{1/2}$. Then, for the decomposition $Q=U\Lambda U^\top$ we have that $I=UU^\top$ and $I-Q=U(I-\Lambda)U^\top$. Hence, $I\succeq A^{1/2}B^{-1}A^{1/2}$. Now by taking $C:= A^{-1/2}$, we have that $B^{-1}\preceq A^{-1}$.
---
#### Problem 2
1. We have: $$\left( I+uv^\top \right) \left( I-\frac{uv^\top}{1+v^\top u} \right)=I+uv^\top -\frac{uv^\top+uv^\top uv^\top}{1+v^\top u} =I+uv^\top -\frac{(1+v^\top u)uv^\top}{1+v^\top u} =I$$