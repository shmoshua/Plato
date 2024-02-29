#Definition #DifferentialGeometry 

> [!definition]
> Let $U\subseteq \mathbb{R}^n$ be an open set. A map $f:U\to \mathbb{R}^m$ is ***differentiable at $p\in U$*** , if there exists a [[linear map]] $L:\mathbb{R}^n\to \mathbb{R}^m$ s.t.
> 1. $f(p+v)=f(p)+L(v)+R(p,v)$ for all $v\in \mathbb{R}^n$ s.t. $p+v\in U$ and
> 2. $\lim_{ v \to 0 }\left\| R(p,v) \right\|  / \|v\|=0$
> 
> Then, we write $D_{p}f=L$.
> 
> ---
> Let $M$ be a [[smooth manifold]]. A function $f:M\to \mathbb{R}$ is ***differentiable at $p\in M$*** if for some chart $(U,\varphi)$ at $p$, 
> 1. $f\circ\varphi ^{-1}:\varphi(U)\to \mathbb{R}$ is differentiable at $\varphi(p)$.
- **Remark**: The differentiability is independent of the chart chosen.