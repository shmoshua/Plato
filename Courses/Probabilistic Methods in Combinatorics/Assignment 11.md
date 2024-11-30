#Series #ProbabilisticMethods 

##### Problem 1
Let $X_{1},\dots,X_{n}$ be independently uniformly chosen number from $\mathbb{Z}_{7}$ and $X=(X_{1},\dots,X_{n})$.  Let $f:\Omega\to \mathbb{R}$ where $f(x):=d(x,U)$. Then, we have that $f$ is $1$-Lipschitz w.r.t. the hamming distance: Indeed, if $x,x'\in \mathbb{Z}_{7}^n$ differ in exactly one coordinate, then $x,x'$ are adjacent and their distance to $U$ can differ by at most 1. 

Now, we claim that: $\mathbb{E}[f(X)]\leq 2\sqrt{ n }$. Assume otherwise. Then, by McDiarmid:$$\mathbb{P}(f(X)=0)\leq \mathbb{P}(\left| f(X)-\mathbb{E}[f(X)] \right| \geq 2\sqrt{ n })\leq 2\cdot  \exp(-8)< 7^{-1}$$which is a contradiction as $\mathbb{P}(f(X)=0)=\frac{\left| U \right|}{\left| V \right|}=7^{-1}$. 

Therefore, by McDiarmid again, we have that: $$\mathbb{P}(f(X)\geq (2+c)\sqrt{ n })\leq\mathbb{P}(f(X)\geq \mathbb{E}[f(X)]+c\sqrt{ n })\leq \exp \left( -2c^{2}\right) $$As our distribution is uniform, $\frac{\left| W \right|}{\left| V \right|}\leq \exp(-2c^{2})$ and $\left| W \right|\leq 7^n \exp \left( -2c^{2} \right)$ and this proves the statement.

---
##### Problem 2

Let $G\sim G(n, 1/2)$ and let $\chi(G)$ be the chromatic number of $G$. Then, we have that: $$$$


Then, with the vertex exposure martingale, i.e. we have $X_{1},\dots,X_{n}$ as random variables where $X_{i}\in\Omega_{i}:=\{ 0,1 \}^{i-1}$ where $(X_{i})_{j}$ means there is an edge $\{ i,j \}\in E$. Then, let $X:=(X_{1},\dots,X_{n})$ with $\Omega:=\prod_{i=1}^{n}\Omega_{i}$ and consider $f:\Omega\to \mathbb{R}$ where $f(X)=\chi(G)$. 

Then, $f$ is $1$-Lipschitz if $x,x'\in \Omega$ differ only at the $i$-th element, then the chromatic number can change at most by 1, depending on whether to color node $i$ with a new color or not. 

Now, we have that: $$\mathbb{P}\left( \left| f(X) - \mathbb{E}[f(X)] \right| \geq \frac{c\sqrt{ n }}{2\log n} \right)\leq 2 \exp \left( -\frac{c^{2}}{2 \log^{2}n} \right) $$

