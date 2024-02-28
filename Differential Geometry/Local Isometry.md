#Definition #DifferentialGeometry 

> [!definition]
> Let $(N,h)$ and $(M,g)$ be two [[Riemannian Manifold|Riemannian manifolds]]. A map $F:(N,h)\to(M,g)$ is a ***local isometry***, if:
> 1. $F$ is a local diffeomorphism, i.e. for all $p\in N$ there exists an open neighborhood $U$ s.t. $f|_{U}$ is a diffeomorphism.
> 2. $F^{*}g=h$, where $F^{*}g$ is the [[Pullback|pullback metric]].
- **Related definition**: When $F$ is a diffeomorphism and $F^{*}g=h$ and $(F^{-1})^{*}h=g$, then $F$ is an ***isometry*** and $M$ and $N$ are ***isometric***.
---
##### Examples
> [!h] Example 1
> The map: $$\begin{array}{cccc} {F:}&{((0,\infty)\times(0,2\pi),dr^{2}+r^{2}d\theta^{2})}&\to&{(\mathbb{R}^{2},dx^{2}+dy^{2})}\\&{(r,\theta)} &\mapsto & {(r\cos\theta,r\sin\theta)} \end{array}{}$$is a local isometry.

> [!proof]+
> We have for $v,w\in T_{(r,\theta)}N$:$$\begin{align}(F^{*}g)_{(r,\theta)}(v,w)&=g_{(r\cos\theta,r\sin\theta)}(d_{p}F(v),d_{p}F(w))\end{align}$$