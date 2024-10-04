#Definition #ML 
> [!definition]
>  For a set $X$, a ***Gaussian process*** is the set  $f:=\{ f(x) \}_{x\in X}$ with the ***mean function*** $\mu:X\to \mathbb{R}$ and the ***covariance function*** $k:X \times X\to \mathbb{R}$ s.t. 
>  1. for every finite $A=\{ x_{1},\dots,x_{n} \}\subseteq X$, $$f(A):=(f(x_{1}),\dots,f(x_{n})) \sim \mathcal{N}\left( \mu_{A},K_{AA}\right)$$where $\mu_{A}:=(\mu(x_{1}),\dots,\mu(x_{n}))$ and $K_{AA}:=\begin{bmatrix}k(x_{i},x_{j})\end{bmatrix}_{i,j\in [n]}$.
> 
> A Gaussian process is denoted as $f \sim \text{GP}(\mu,k)$.

^fc4049

- **Related definition**: For a normed vector space $X$, a covariance function is: ^cc13be
	1. ***stationary***  if $k(x,y)=\tilde{k}(x-y)$ for all $x,y\in X$ for some $\tilde{k}:X\to \mathbb{R}$.
	2. ***isotropic***  if $k(x,y)=\tilde{k}(\left\| x-y \right\|)$ for all $x,y\in X$ for some $\tilde{k}:\mathbb{R}_{\geq 0}\to \mathbb{R}$.
---
##### Properties
> [!lemma] Proposition 1
> For a Gaussian process $\text{GP}(\mu,k)$ on $X$,
> 1. $k$ is a [[kernel]].
> 