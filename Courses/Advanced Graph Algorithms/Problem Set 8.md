#Series #AGAO 

#### Exercise 1
For the first program, the Lagrangian is given as: $$L(f,x):=\left\| C^{-1}f \right\| _{\infty}+x^\top(d-Bf)$$as $\left\| \cdot \right\|_{\infty}$ is convex. 

Then, by letting $$L(x):= \min_{f\in \mathbb{R}^E_{\geq 0}}\left\| C^{-1}f \right\| _{\infty}+x^\top(d-Bf)=x^\top d+\min_{f\in \mathbb{R}^E_{\geq 0}}(\left\| C^{-1}f \right\| _{\infty}-x^\top B f)$$
Notice that if $\sum_{e\in E}^{}\max\{ c_{e}b_{e}^\top x, 0 \}\leq  1$, then for any $f\geq 0$, we have that: $$\begin{aligned}\left\| C^{-1}f \right\| _{\infty}-x^\top Bf&=\left\| C^{-1}f \right\| _{\infty}\left( 1-\sum_{e}^{}\frac{f(e)}{\left\| C^{-1}f \right\| _{\infty}}b^\top_{e}x \right)\geq \left\| C^{-1}f \right\| _{\infty}\left( 1-\sum_{e}^{}c(e)b^\top_{e}x \right)\geq 0\end{aligned}$$if $\left\| C^{-1}f \right\|_{\infty}> 0$. Further, we have that $\left\| C^{-1}f \right\|_{\infty}-x^\top Bf=0$ if $f=0$. Hence, in this condition, $\min_{f\in \mathbb{R}^E_{\geq 0}}(\left\| C^{-1}f \right\| _{\infty}-x^\top B f)=0$. However, if $\sum_{e\in E}^{}\max\{ c_{e}b_{e}^\top x, 0 \}>  1$ then the minimum is $-\infty$. Therefore, the dual is given as: $$\max_{x}L(x)=\max_{x}x^\top d \quad \text{ s.t. }\quad \sum_{e\in E}^{}\max\{ c_{e}b_{e}^\top x, 0 \}\leq 1$$

To see if strong duality holds: We know that Slater's condition holds if there exists $f>0$ s.t. $Bf=d$. As there exists $f\geq 0$ with $Bf=d$ if and only if there exists a directed path from $s$ to $t$ from last exercise sheet. Therefore, we need to check if for every edge $u\to v$ there exists direct paths from $s$ to $u$ and $v$ to $t$. Then by Slater, strong duality holds. Otherwise, 



#### Exercise 2
We have that the Lagrangian is given as: $$L(x,y,s)=e^{-x}+\frac{sx^{2}}{y}$$Now, for$s\geq0$:  $$L(s)=\inf_{x\in \mathbb{R},y> 0}\left( e^{-x}+\frac{sx^2}{y} \right)=\inf_{x\in \mathbb{R}} e^{-x}=0$$Hence, the dual optimum is given by $0$. However, for the primal program, as $y> 0$ and $x^{2}\geq 0$, $x^{2} / y\leq 0$ if and only if $x=0$. Hence, the optimal value is given by $1$. Therefore, the strong duality doesn't hold. 

Notice that the Slater condition also does not hold: $x^2 / y <0$ cannot hold for any $x\in \mathbb{R}$ and $y> 0$. 

---


