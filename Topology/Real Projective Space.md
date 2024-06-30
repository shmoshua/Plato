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

> [!proof]-
> We will verify that they are charts.
> 1. Firstly for $x\in \mathbb{R}^{n+1} \backslash \{ 0 \}$, there exists $0\leq j\leq n$ s.t. $x^j\neq 0$. Therefore, $x\in V_{j}$ and $\pi(x)\in \pi(U_{j})$. 
> 2. We show that $\varphi_{j}$ is well-defined. For $y=\lambda x$ with $\pi(y)=\pi(x)\in U_{j}$, we have: $$\varphi_{j}(\pi(y))=\frac{\lambda(x^0,\dots,\widehat{x^j},\dots,x^n)}{\lambda x^j}=\frac{(x^0,\dots,\widehat{x^j},\dots,x^n)}{x^j}=\varphi_{j}(\pi(x))$$
> 3. $\varphi_{j}$ is a homeomorphism to an open set:  We have that: $$\varphi_{j}(U_{j})=\varphi_{j}(\pi(V_{j}))=\mathbb{R}^n$$Then, we first show the injectivity: if $\varphi_{j}(\pi(x))=\varphi_{j}(\pi(y))=(a^0,\dots,a^{n-1})$, then set: $$\tilde{a}:=(a^0,\dots,a^{j-1},1,a^j,\dots,a^{n-1})\in\mathbb{R}^{n+1}\backslash\{ 0 \}$$ and $\pi(x)=\pi(\tilde{a})$ as $x^j \tilde{a}=x$. The surjectivity is also given by $\tilde{a}$. To show that it is a homeomorphism, $a\mapsto \pi(\tilde{a})$ is continuous. Similarly, $\varphi_{j}$ is continuous as $\varphi_{j}\circ\pi$ is continuous. 
>  4. We finally show that the charts are smoothly compatible. For $0\leq j< k\leq n$, we have that for $a\in\varphi_{k}(U_{j}\cap U_{k})$: $$\begin{align}\varphi_{j}\varphi_{k}^{-1}(a^0,\dots,a^{n-1})&=\varphi_{j}(\pi(a^0,\dots,a^{k-1},1,a^k,\dots,a^{n-1}))\\&=\frac{(a^0,\dots,\widehat{a^j},\dots,a^{k-1},1,a^k,. ..,a^{n-1})}{a^j}\end{align}$$which is smooth.

---
