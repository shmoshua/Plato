#Definition #DifferentialGeometry 
> [!definition]
> Let $M$ be a [[smooth manifold]]. For $p\in M$, the ***tangent space*** $\text{T}_{p}M$ is defined as: $$\text{T}_{p}M:=\left\{  v:C^\infty(M)\to \mathbb{R}| \exists \gamma:(-\varepsilon,\varepsilon)\to M\text{ smooth curve s.t. }vf=\left. \frac{d}{dt} \right|_{0}f(\gamma(t))  \right\}$$
---
##### Properties
> [!lemma] Theorem 1 (Tangent Space is a Vector Space)
> For $\text{T}_{p}M$ and $(U,\varphi)$ a chart at $p$ with coordinate functions $x^1,\dots,x^m\in C^\infty(\mathbb{R})$,
> 1. the ***coordinate vectors***, defined as: $$\left. \frac{ \partial  }{ \partial x ^i} \right| _{p}:C^\infty(M)\to \mathbb{R},\quad f\mapsto \left. \frac{ \partial f }{ \partial x^i }  \right| _{p}:=\left. \frac{ \partial f\circ \varphi ^{-1} }{ \partial \pi^i } \right| _{\varphi(p)} $$form a basis of $\text{T}_{p}M$.
> 2. $\text{T}_{p}M\cong \mathbb{R}^m$ as a vector space.

> [!proof]+
> We have that: 
> 1. **Claim 1: $\left. \frac{ \partial  }{ \partial x^i } \right|_{p}\in \text{T}_{p}M$**. 
>    We have that: $$\left. \frac{ \partial f }{ \partial x^i } \right|_{p}=\left. \frac{ \partial f\circ \varphi }{ \partial \pi^i }  \right| _{\varphi(p)}= $$
