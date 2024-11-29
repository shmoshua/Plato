#Series #ProbabilisticMethods 

##### Problem 1
Let $X_{1},\dots,X_{n}$ be independently uniformly chosen number from $\mathbb{Z}_{7}$ and $X=(X_{1},\dots,X_{n})$.  Let $f:X\to \mathbb{R}$ where $f(x):=d(x,U)$. Then, we have that $f$ is $1$-Lipschitz w.r.t. the hamming distance: Indeed, if $x,x'\in \mathbb{Z}_{7}^n$ differ in exactly one coordinate, then $x,x'$ are adjacent and their distance to $U$ can differ by at most 1. 

Now, we have that: $$\mathbb{E}[f(X)]$$

Therefore, by McDiarmid, we have that: $$\mathbb{P}(f(X)\geq \mathbb{E}[f(X)]+\lambda)\leq \exp \left( -\frac{2\lambda^{2}}{n} \right) $$
