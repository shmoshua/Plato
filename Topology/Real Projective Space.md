#Definition #Topology 

> [!definition]
> The ***real projective space*** $\mathbb{R}\mathbb{P}^n$ is given by $$\mathbb{R}\mathbb{P}^n:=(\mathbb{R}^{n+1}\backslash\{ 0 \} )/(\mathbb{R} \backslash \{ 0 \})$$given by the [[Group Action|action]] $\mathbb{R}\backslash\{ 0 \}\curvearrowright\mathbb{R}^{n+1}\backslash \{ 0 \}, (\lambda,x)\mapsto\lambda x$.
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\mathbb{R}\mathbb{P}^n$ is a [[metric space]] given by $S^n$.
> 2. $\mathbb{R}\mathbb{P}^n$ is a [[smooth manifold]] of dimension $n$ given by charts: $(U_{j},\varphi_{j})_{0\leq j\leq n}$ where: 
> 	- $U_{j}:=\pi(V_{j})$ where $V_{j}:=\{ x\in \mathbb{R}^{n+1} \backslash \{ 0 \}: x^j\neq 0 \}$ and
> 	$$\varphi_{j}:U_{j}\to \mathbb{R}^n,\quad \pi(x)\mapsto \frac{(x^0,\dots,\widehat{x^j},\dots,x^n)}{x^j}$$

> [!proof]+
> We will verify that they are charts.
> 1. Firstly for $x\in \mathbb{R}^{n+1} \backslash \{ 0 \}$, there exists $0\leq j\leq n$ s.t. $x^j\neq 0$. Therefore, $x\in V_{j}$ and $\pi(x)\in \pi(U_{j})$. 
> 2. We show that $\varphi_{j}$ is well-defined. For $y=\lambda x$ with $\pi(y)=\pi(x)\in U_{j}$, we have: $$\varphi_{j}(\pi(y))=\frac{\lambda(x^0,\dots,\widehat{x^j},\dots,x^n)}{\lambda x^j}=\frac{(x^0,\dots,\widehat{x^j},\dots,x^n)}{x^j}=\varphi_{j}(\pi(x))$$
> 3. $\varphi_{j}$ is a homeomorphism to an open set:  We have that: $$\varphi_{j}(U_{j})=\varphi_{j}(\pi(V_{j}))=\mathbb{R}^n$$
