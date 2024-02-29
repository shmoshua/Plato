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
- **Remark**: For $f\in C^1(M,N)$, $f$ is differentiable at every $p\in M$.
- **Remark**: $C^k(M,\mathbb{R})$ forms a $\mathbb{R}$-algebra.
- **Remark**: For $f\in C^k(M,N)$ and $g\in C^k(N,R)$, $g\circ f\in C^k(M,R)$.
---
##### Properties
> [!lemma] Lemma 1
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and let $M=\bigcup_{\alpha\in A}^{}U_{\alpha}$ be an open covering of $M$. Then, the following are equivalent:
> 1. $f\in C^k(M,N)$
> 2. $f|_{U_{\alpha}}\in C^k(U_{\alpha},N)$ for all $\alpha\in A$

> [!proof]- Proof (Incomplete)
> Let $f\in C^k(M,N)$. Then, for any chart $(V,\varphi)$ and $(W,\psi)$ on $U_{\alpha},N$ respectively s.t. $f(V)\subseteq W$, $$\psi \circ f|_{U_{\alpha}}\circ \varphi ^{-1}=\psi \circ f\circ \varphi ^{-1}\in C^k(\varphi(V),\psi(W))$$Therefore, $f|_{U_{\alpha}}\in C^k(U_{\alpha},N)$.
> 
> Conversely, assume that $f|_{U_{\alpha}}\in C^k(U_{\alpha},N)$ for all $\alpha\in A$. Then, for any chart $(V,\varphi)$ and $(W,\psi)$ on $M,N$, there exists a chart $(V\cap U_{\alpha},\varphi|_{V\cap U_{\alpha}})$ on $U_{\alpha}$ and: $$\psi \circ f\circ (\varphi|_{V\cap U_{\alpha}})^{-1}=\psi \circ f|_{U\alpha}\circ (\varphi|_{V\cap U_{\alpha}})^{-1}\in C^k(\varphi(V\cap U_{\alpha}),\psi(W))$$
---
##### Examples
> [!h] Example 1
> Let $M=\mathbb{R}$ and $N=S^1$. Then, $\exp:\mathbb{R}\to S^1,t\mapsto e^{2\pi it}$ is smooth.
---
> [!h] Example 2
> We have:
> 1. The map $\text{GL}(n,\mathbb{R})\times\text{GL}(n,\mathbb{R})\to\text{GL}(n,\mathbb{R}):(A,B)\mapsto AB$ is smooth.
> 2. For $A\in \text{GL}(n,\mathbb{R})$, $L_{A}:\text{GL}(n,\mathbb{R})\to\text{GL}(n,\mathbb{R}):B\mapsto AB$ is a $C^\infty$-diffeomorphism.
> 