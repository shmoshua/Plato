#Series #AGAO 

#### Problem 1
For the first program, the Lagrangian is given as: $$L(f,x):=\left\| C^{-1}f \right\| _{\infty}+x^\top(d-Bf)$$as $\left\| \cdot \right\|_{\infty}$ is convex. Then, by letting $L(x):= \min_{f\in \mathbb{R}^E_{\geq 0}}L(f,x)$, the dual is given by: $\max_{x}L(x)$. 

For strong duality, consider the following example. $V=\{ u,v,w \}$ and $E:=\{  u\to v , v\to w, u\to w \}$ with $c(u\to v)=$ and $d=[-1,0,1]$. Then, $$B=\begin{bmatrix}-1&0&-1\\1&-1&0\\0&1&1\end{bmatrix}$$and $Bf=d$ implies that $f=(1,1,0)+a(-1,-1,1)$ for some $a\in \mathbb{R}$. However as $f\geq 0$, $0\leq a\leq 1$.