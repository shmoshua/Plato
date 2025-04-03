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
2. Notice that: $$\begin{aligned}(A+uv^\top)\left( A^{-1}-\frac{A^{-1}uv^\top A^{-1}}{1+v^\top A^{-1}u} \right)&=I+uv^\top A^{-1}-\frac{uv^\top A^{-1}+u(v^\top A^{-1}u)v^\top A^{-1}}{1+v^\top A^{-1}u}\\&=I+uv^\top A^{-1}-uv^\top A^{-1}\\&=I\end{aligned}$$

---
#### Problem 3
Let $X\in \text{GL}(n,\mathbb{R})$. We have that for any $u,v\in \mathbb{R}^n$, $$d_{X}f(uv^\top)=\left. \frac{ \partial  }{ \partial t }  \right|_{t=0}(X+tuv^\top)^{-1}=\left. \frac{ \partial  }{ \partial t }  \right| _{t=0}X ^{-1}-\frac{tX ^{-1}uv^\top X ^{-1}}{1+ t  v^\top A u}=-X ^{-1}uv^\top X ^{-1} $$where we may use that $X+tuv^\top$ is invertible for small $t$ as $\text{GL}(n,\mathbb{R})$ is open in $\text{Mat}_{n,n}(\mathbb{R})$ as $\text{GL}(n,\mathbb{R})= \det ^{-1}(\mathbb{R} \backslash \{ 0 \})$.

Hence, for any $Y$, let $Y=\sum_{i=1}^{n}\sigma_{i}u_{i}v_{i}^\top$ be the SVD. Using the linearity of differentials, we have: $$d_{X}f(Y)=\sum_{i=1}^{n}\sigma_{i}d_{X}f(u_{i}v_{i}^\top)=-X ^{-1}Y X ^{-1}$$

---
#### Problem 4
1. As $0\preceq \Delta$, we have that $A\preceq A+\Delta$. Further, we have that $A+\Delta\in S^n_{++}$ as $A\in S^n_{++}$. Indeed, $$z^\top(A+\Delta)z=z^\top Az+z^\top \Delta z> 0,\quad \forall z\in \mathbb{R}^n$$Therefore, by Problem 1.2, $(A+\Delta)^{-1}\preceq A^{-1}$.
2. We now have that: $$\begin{aligned}d^{2}_{X}f(Y,Y)&=\left. \frac{ \partial  }{ \partial t }  \right|_{t=0}d_{X+tY}f(Y)\\&=-\left. \frac{ \partial  }{ \partial t }  \right|_{t=0}(X+tY)^{-1} Y (X+tY)^{-1}\\&=-\left( \left. \frac{ \partial  }{ \partial t }  \right|_{t=0}(X+tY)^{-1} \right) Y X^{-1}-X^{-1} Y \left( \left. \frac{ \partial  }{ \partial t }  \right|_{t=0}(X+tY)^{-1} \right)\\&=2X ^{-1}YX ^{-1}YX ^{-1}\end{aligned} $$which is positive semi-definite for all $Y\in S^n$ and $X\in  S^n_{++}$ by taking $y:= \sqrt{ 2 }YX ^{-1}x$ for all $x\in \mathbb{R}^n$.
   
   Now, let $v\in \mathbb{R}^n$ and define $$\phi:T\to X,\quad X\mapsto v^\top f(X)v$$Then, $$d^2_{X}\phi(Y,Y)=v^\top d^2_{X}f(Y,Y)v^\top\geq 0,\quad \forall X\in S^n_{++},Y\in S^n$$Hence, $\phi$ is a convex function and as $v$ is arbitrary, $f$ is a convex operator.

---

