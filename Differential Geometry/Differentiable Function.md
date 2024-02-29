#Definition #DifferentialGeometry 

> [!definition]
> Let $U\subseteq \mathbb{R}^n$ be an open set. A map $f:U\to \mathbb{R}^m$ is ***differentiable at $p\in U$*** , if there exists a [[linear map]] $L:\mathbb{R}^n\to \mathbb{R}^m$ s.t.
> 1. $f(p+v)=f(p)+L(v)+R(p,v)$ for all $v\in \mathbb{R}^n$ s.t. $p+v\in U$ and
> 2. $\lim_{ v \to 0 }\left\| R(p,v) \right\|  / \|v\|=0$
> 
> Then, we write $D_{p}f=L$.
> 
> ---
> Let $M,N$ be a [[smooth manifold|smooth manifolds]]. A function $f:M\to N$ is ***differentiable at $p\in M$*** if for some charts $(U,\varphi)$ at $p$ and $(W,\psi)$ at $f(p)$ s.t.
> 1. $f(U)\subseteq W$ and
> 2. $\psi \circ f\circ\varphi ^{-1}:\varphi(U)\to \psi(W)$ is differentiable at $\varphi(p)$.
- **Remark**: The differentiability is independent of the chart chosen.
- **Related definition**: $f\in C^k(M,N)$ if for every pair $(U,\varphi),(W,\psi)$ of charts on $M$ and $N$ respectively s.t. $f(U)\subseteq W$, we have $\psi \circ f\circ\varphi ^{-1}\in C^k$
---
##### Properties
> [!lemma] Theorem 1
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and let $f\in C^1(M,N)$. Then, $f$ is differentiable at every $p\in M$.
---