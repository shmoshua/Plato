#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[topological manifold]] of dimension $m$. A ***smooth atlas*** on $M$ is a collection: $$\mathcal{X}:=\{ x_{\alpha}:U_{\alpha}\to x_{\alpha}(U_{\alpha})\subseteq \mathbb{R}^m \}_{\alpha}$$where $U_{\alpha}$ is open, $x_{\alpha}$ is a [[homeomorphism]] s.t.
> 1. $M=\bigcup_{\alpha\in A}^{}U_{\alpha}$ and
> 2. $x_{\beta}\circ x_{\alpha}^{-1}: x_{\alpha}(U_{\alpha}\cap U_{\beta})\to x_{\beta}(U_{\alpha}\cap U_{\beta})$ is a [[diffeomorphism]] for all $\alpha,\beta\in A$

- **Related definition**: the maps $x_{\alpha}$ are called ***charts***, the maps $x_{\beta}\circ x_{\alpha}^{-1}$ are called ***transition maps***.
- **Related definition**: two smooth atlases $\mathcal{X},\mathcal{Y}$ are ***equivalent***, if their union is also a smooth atlas.
---
##### Properties
> [!lemma] Proposition 1
> Let $M$ be a [[smooth manifold]] and $y^1,\dots,y^m\in C^\infty(M)$ s.t. $\{ d_{p}y^i \}\subseteq \text{T}^{*}_{p}M$ are linearly independent. Then, there exists a chart on a neighborhood of $p$ with $y^1,\dots,y^m$ as coordinate functions.

> [!proof]+
> Suppose $y^i$ are defined on an open neighborhood $U\ni p$. Then, define $\varphi :M\to \mathbb{R}^m$: $$\varphi(p):=(y^1(p),\dots,y^m(p))$$Then, $\varphi\in C^\infty(M,\mathbb{R}^m)$