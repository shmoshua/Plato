#Series #AGAO 

#### Exercise 1
For the first program, the Lagrangian is given as: $$L(f,x):=\left\| C^{-1}f \right\| _{\infty}+x^\top(d-Bf)$$as $\left\| \cdot \right\|_{\infty}$ is convex. 

Then, by letting $$L(x):= \min_{f\in \mathbb{R}^E_{\geq 0}}\left\| C^{-1}f \right\| _{\infty}+x^\top(d-Bf)=x^\top d+\min_{f\in \mathbb{R}^E_{\geq 0}}(\left\| C^{-1}f \right\| _{\infty}-x^\top B f)$$Therefore, the dual is given by: $$\max_{x}L(x)=\max_{x}x^\top d \quad \text{ s.t. }\quad \sum_{e\in E}^{}\max\{ c_{e}b_{e}^\top x, 0 \}\leq 1$$

To compute this explicitly, we can rewrite the 

We can construct a flow $f>0$ s.t. $Bf=d$ if and only if for every $u\to v\in E$, there exists a directed path from $s$ to $u$ and a directed path from $v$ to $t$.

For strong duality, consider the following example. $V=\{ u,v,w \}$ and $E:=\{  u\to v , v\to w, u\to w \}$ with $c(u\to v)=$ and $d=[-1,0,1]$. Then, $$B=\begin{bmatrix}-1&0&-1\\1&-1&0\\0&1&1\end{bmatrix}$$and $Bf=d$ implies that $f=(1,1,0)+a(-1,-1,1)$ for some $a\in \mathbb{R}$. However as $f\geq 0$, $0\leq a\leq 1$.

In the second program, we have that the Lagrangian is given as: $$L(f,x,s):=\left\| C^{-1}f \right\| _{\infty}+x^\top(d-Bf)-s^\top f$$and the dual is given by $\max_{x,s,s\geq 0}\min_{f} L(f,x,s)$. 

Slater's condition holds when there exists f > 0 s.t. _Bf_ = _d_. Note that there exists a flow f ≥ 0 s.t. _Bf_ = _d_ if and only if there exists a directed path from s .


#### Exercise 2
We have that the Lagrangian is given as: $$L(x,y,s)=e^{-x}+\frac{sx^{2}}{y}$$Now, for$s\geq0$:  $$L(s)=\inf_{x\in \mathbb{R},y> 0}\left( e^{-x}+\frac{sx^2}{y} \right)=\inf_{x\in \mathbb{R}} e^{-x}=0$$Hence, the dual optimum is given by $0$. However, for the primal program, as $y> 0$ and $x^{2}\geq 0$, $x^{2} / y\leq 0$ if and only if $x=0$. Hence, the optimal value is given by $1$. Therefore, the strong duality doesn't hold. 

Notice that the Slater condition also does not hold: $x^2 / y <0$ cannot hold for any $x\in \mathbb{R}$ and $y> 0$. 

---


