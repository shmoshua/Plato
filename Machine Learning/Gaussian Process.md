#Definition #ML 
> [!definition]
>  For a set $X$, a ***Gaussian process*** is the set  $f:=\{ f(x) \}_{x\in X}$ with the ***mean function*** $\mu:X\to \mathbb{R}$ and the ***covariance function*** $k:X \times X\to \mathbb{R}$ s.t. 
>  1. for every finite $A=\{ x_{1},\dots,x_{n} \}\subseteq X$, $$f(A):=(f(x_{1}),\dots,f(x_{n})) \sim \mathcal{N}\left( \mu_{A},K_{AA}\right)$$where $\mu_{A}:=(\mu(x_{1}),\dots,\mu(x_{n}))$ and $K_{AA}:=\begin{bmatrix}k(x_{i},x_{j})\end{bmatrix}_{i,j\in [n]}$.
> 
> A Gaussian process is denoted as $f \sim \text{GP}(\mu,k)$.

^fc4049

---
##### Properties
> [!lemma] Proposition 1
> For a Gaussian process $\text{GP}(\mu,k)$ on $X$,
> 1. $k$ is a SPsD [[kernel]]. Conversely, any SPsD kernel $k:X\times X\to \mathbb{R}$ can be a covariance function on a Gaussian process of $X$. 

^acc53b

> [!proof]-
> We have that:
> 1. for all $x,y\in X$, $f(\{ x,y \}):=(f(x),f(y)) \sim \mathcal{N}(\mu_{\{ x,y \}},K_{\{ x,y \}})$ where: $$K_{\{ x,y \}}:=\begin{bmatrix}k(x,x)&k(x,y)\\k(y,x)&k(y,y)\end{bmatrix}$$As covariance matrices are symmetric, we have that $k(x,y)=k(y,x)$. 
>    
>    Further, the Gram matrix is positive semidefinite by definition. 

^d1890f

---
> [!lemma] Proposition 2
> Let $f\sim \text{GP}(\mu,k)$ on $X$ and set $A:=\{ x_{1},\dots,x_{} \}$