#Definition #ML 
> [!definition]
>  For a set $X$, a ***Gaussian process*** is the set  $\{ f(x) \}_{x\in X}$ with the mean $\mu:X\to \mathbb{R}$ and $k:X \times X\to \mathbb{R}$ s.t. 
>  1. for every finite $A=\{ x_{1},\dots,x_{n} \}\subseteq X$, $$f(A):=(f(x_{1}),\dots,f(x_{n})) \sim \mathcal{N}\left( (\mu(x_{1}),\dots,\mu(x_{n})),\begin{bmatrix}k(x_{1},x_{1})&\dots&k(x)\end{bmatrix} \right) $$