#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. The ***cotangent space*** $M$ at $p$ is the [[Dual Space|dual vector space]] of $\text{T}_{p}M$, denoted as $\text{T}^{*}_{p}M$. The elements of $\text{T}^{*}_{p}M$ are called ***covectors***.
- **Remark**: from [[Tangent Space II|Proposition 2]] $\text{T}_{p}^{*}M\cong I_{p} / I_{p}^{2}$, where $I_{p}:=\{ f\in C^\infty_{p}(M):f(p)=0 \}$.
- **Related definition**: Given a chart $(U,\varphi)$ at $p\in M$, the ***coordinate differentials*** are: $$\begin{array}{cccc} {d_{p}x^i:}&{\text{T}_{p}M}&\to&{\mathbb{R}}\\&{v} &\mapsto & {v(x^i)} \left. \frac{d}{dt} \right| _{p_{i}}\end{array}{}$$
---
##### Properties
> [!lemma] Proposition 1
> We have that for chart $(U,\varphi)$ with $x^1,\dots,x^m$ as coordinates,
> 1. $\{ d_{p}x^i \}_{i}$ forms a basis of $\text{T}^{*}_{p}M$, i.e. for $f\in C^\infty(M)$, $$d_{p}f=\sum_{i=1}^{m}\left. \frac{ \partial f }{ \partial x^i } \right| _{p}d_{p}x^i $$

> [!proof]-
> We have: $$d_{p}f\left( \left.\frac{ \partial  }{ \partial x^j }   \right|_{p}  \right) =\left. \frac{ \partial f }{ \partial x^j }  \right| _{p} \left. \frac{d}{dt} \right| _{f(p)}=\sum_{i=1}^{m}\left. \frac{ \partial f }{ \partial x^i }  \right| _{p}\delta_{ij} \left. \frac{d}{dt} \right| _{p_{i}}=\sum_{i=1}^{m}\left. \frac{ \partial f }{ \partial x^i }  \right| _{p}d_{p}x^i\left( \left. \frac{ \partial  }{ \partial x^j }  \right|_{p}  \right)$$