#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. The ***cotangent space*** $M$ at $p$ is the [[Dual Space|dual vector space]] of $\text{T}_{p}M$, denoted as $\text{T}^{*}_{p}M$. The elements of $\text{T}^{*}_{p}M$ are called ***covectors***.
- **Remark**: from [[Tangent Space II|Proposition 2]] $\text{T}_{p}^{*}M\cong I_{p} / I_{p}^{2}$, where $I_{p}:=\{ f\in C^\infty_{p}(M):f(p)=0 \}$.
- **Related definition**: Given a chart $(U,\varphi)$ at $p\in M$, the ***coordinate differentials*** are: $$\begin{array}{cccc} {d_{p}x^i:}&{\text{T}_{p}M}&\to&{\mathbb{R}}\\&{v} &\mapsto & {v(x^i) \left. \frac{d}{dx^i} \right| _{}[d_{p}\varphi (v)]_{i}} \end{array}{}$$Notice that:
	1. For $dx^i:=\varphi ^{*}(d\pi^i)$, $(dx^i)_{p}$ coincides with the definition above.
---
