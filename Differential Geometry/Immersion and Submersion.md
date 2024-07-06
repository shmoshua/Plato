#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $f:M\to N$ a smooth map. Then, 
> 1. $f$ is an ***immersion*** if $d_{p}f$ is injective for all $p\in M$.
> 2. $f$ is an ***submersion*** if $d_{p}f$ is surjective for all $p\in M$.
- **Remark**: If $f$ is a immersion, $m\leq n$ and if $f$ is a submersion, $m\geq n$.
---
##### Properties
> [!lemma] Theorem 1 (Local Immersion Theorem)
> Let $f:M\to N$ be a smooth map between smooth manifolds and $p\in M$.
> 1. if $d_{p}f$ is injective, then there exists local coordinates $\varphi:=(x^1,\dots,x^m)$ at $p$ and $\psi:=(y^1,\dots,y^n)$ at $f(p)$ s.t. $$\psi f\varphi ^{-1}(x^1,\dots,x^m)=(x^1,\dots,x^m,0,\dots,0)$$
---
##### Examples
> [!h] Example 1 (Immersion)
> Let $\gamma:\mathbb{R}\to \mathbb{R}^{2},t\mapsto(t^2,t^3-t)$ be a [[Regular Curve in Rn|regular curve]]. Then, 
> 1. $\gamma$ is an immersion.
---
> [!lh] Exmaple 2 (Submersion)
> We have that:
> 1. $\mathbb{R}^n\backslash\{ 0 \}\to S^{n-1},x\mapsto x /\|x\|$ is a submersion.
---
![[Tangent Bundle#^d01715]]
![[Tangent Bundle#^04ed06|p]]
---
> [!h] Example 3 (Projective Space)
> We have that
> 1. $\mathbb{R}\mathbb{P}^2$ does not embed in $\mathbb{R}^3$.
> 2. $\mathbb{R}\mathbb{P}^2$ immerses into $\mathbb{R}^3$ as the Boy's surface.
> 3. $\mathbb{R}\mathbb{P}^{2}$ embeds into $\mathbb{R}^4$ called Veronese embedding, given by: $$S^2\to \mathbb{R}^4,\quad (x,y,z)\mapsto(x^{2}-y^{2},xy,yz,xz)$$
---
