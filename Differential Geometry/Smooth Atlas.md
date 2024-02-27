#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[topological manifold]] of dimension $m$. A ***smooth atlas*** on $M$ is a collection: $$\mathcal{X}:=\{ x_{\alpha}:U_{\alpha}\to x_{\alpha}(U_{\alpha})\subseteq \mathbb{R}^m \}_{\alpha}$$where $U_{\alpha}$ is open, $x_{\alpha}$ is a [[homeomorphism]] s.t.
> 1. $M=\bigcup_{\alpha\in A}^{}U_{\alpha}$ and
> 2. $x_{\beta}\circ x_{\alpha}^{-1}: x_{\alpha}(U_{\alpha}\cap U_{\beta})\to x_{\beta}(U_{\alpha}\cap U_{\beta})$ is a [[diffeomorphism]] for all $\alpha,\beta\in A$

- **Related definition**: the maps $x_{\alpha}$ are called ***charts***, the maps $x_{\beta}\circ x_{\alpha}^{-1}$ are called ***transition maps***.
- **Related definition**: two smooth atlases $\mathcal{X},\mathcal{Y}$ are ***equivalent***, if their union is also a smooth atlas.
---