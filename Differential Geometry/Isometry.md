#Definition #DifferentialGeometry 

> [!definition]
> Let $(M,g)$ and $(N,h)$  be two [[Riemannian Manifold|Riemannian manifolds]]. A smooth map $f:M\to N$ is a ***isometry***, if:
> 1. $f$ is a diffeomorphism and
> 2. $g=f^{*}h$, where $f^{*}h$ is the [[Pullback|pullback metric]].
- **Remark**: For a Reimannian manifold $(M,g)$, $\text{Iso}(M,g)$ denotes the set of isometries on $M$, which is a [[Lie group]].
- **Related definition**: If $f$ is a [[local diffeomorphism]], then $f$ is a local isometry.
- **Related defintion**: A property or quantity is ***intrinsic***, if it is invariant under isometries.
---
##### Examples
> [!h] Example 1
> The map: $$\begin{array}{cccc} {F:}&{((0,\infty)\times(0,2\pi),dr^{2}+r^{2}d\theta^{2})}&\to&{(\mathbb{R}^{2},dx^{2}+dy^{2})}\\&{(r,\theta)} &\mapsto & {(r\cos\theta,r\sin\theta)} \end{array}{}$$is a local isometry.

> [!proof]-
> We have for $v,w\in T_{(r,\theta)}N$:$$\begin{align}(F^{*}g)_{(r,\theta)}(v,w)&=g_{(r\cos\theta,r\sin\theta)}(d_{p}F(v),d_{p}F(w))\end{align}$$