#Definition #DifferentialGeometry 
> [!definition]
> Let $M$ be a [[smooth manifold]]. For $p\in M$, the ***tangent space*** $\text{T}_{p}M$ is defined as: $$\text{T}_{p}M:=\left\{  v\in C^\infty(M)^{*}\left| \exists \gamma:(-\varepsilon,\varepsilon)\to M\text{ smooth curve, } \gamma(0)=p\text{ s.t. }vf=\left. \frac{d}{dt} \right|_{t=0}f(\gamma(t)) \right. \right\}$$
> 
---
##### Properties
> [!lemma] Theorem 1 (Tangent Space is a Vector Space)
> For $\text{T}_{p}M$ and $(U,\varphi)$ a chart at $p$ with coordinate functions $x^1,\dots,x^m\in C^\infty(\mathbb{R})$,
> 1. the ***coordinate vectors***, defined as: $$\left. \frac{ \partial  }{ \partial x ^i} \right| _{p}:C^\infty(M)\to \mathbb{R},\quad f\mapsto \left. \frac{ \partial f }{ \partial x^i }  \right| _{p}:=\left. \frac{ \partial f\circ \varphi ^{-1} }{ \partial \pi^i } \right| _{\varphi(p)} $$form a basis of $\text{T}_{p}M$.
> 2. $\text{T}_{p}M\cong \mathbb{R}^m$ as a vector space.

> [!proof]+
> We have that: 
> 1. **Claim 1: $\left. \frac{ \partial  }{ \partial x^i } \right|_{p}\in \text{T}_{p}M$**. 
>    Let us define a curve $\tilde{\gamma}:(-\varepsilon,\varepsilon)\to \mathbb{R}^m,t\mapsto \varphi(p)+te_{i}$. Then, it is smooth and therefore, $\gamma:=\varphi ^{-1}\circ\tilde{\gamma}$ is smooth and:$$\left. \frac{d}{dt} \right| _{t=0}f(\gamma(t))=\left. \frac{d}{dt} \right| _{t=0}f(\varphi ^{-1}(\tilde{\gamma}(t)))=d_{\varphi(p)}(f\circ \varphi ^{-1})(e_{i})=\left. \frac{ \partial f\circ \varphi ^{-1} }{ \partial \pi^j }  \right|_{\varphi(p)} \delta_{i}^j=\left. \frac{ \partial f }{ \partial x^i } \right| _{p} $$
> 2. **Claim 2: $\left. \frac{ \partial  }{ \partial x^i } \right|_{p}$ forms a basis**:
>    Let $\gamma:(-\varepsilon,\varepsilon)\to M$ be a smooth curve. Then, let $v\in C^\infty(M)^{*}$ with $vf=\frac{d}{dt}|_{t=0}f(\gamma(t))$. Therefore, $v\in \text{T}_{p}M$. Then, we have $\varphi(\gamma(t))=\sum_{i=1}^{m}(x^i\circ\gamma)(t)e_{i}$. Therefore, $$\begin{align}vf&=\left. \frac{d}{dt} \right|_{t=0}f(\gamma(t))=\left. \frac{d}{dt} \right|_{t=0}f\circ \varphi ^{-1}\left( \sum_{i=1}^{m}(x^i\circ \gamma)(t)e_{i} \right)\\&=d_{p}\end{align}$$
