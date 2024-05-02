#Definition #FunctionalAnalysis 

> [!definition]
> Let $G$ be a [[Locally Compact Topological Group|locally compact Hausdorff topological group]] and $\mu$ a [[Haar Measure|left Haar measure]]. If $G$ is abelian and $\sigma$-compact, i.e. it is a countable union of [[Compact Space|compact]] subsets, for $f,g\in L^1(G,\mu)$, the ***convolution*** of $f,g$ is defined as: $$\begin{array}{cccc} {f*g:}&{G}&\to&{\mathbb{C}}\\&{x} &\mapsto & {\int_{G}^{} f(xy)g(y^{-1}) \, d\mu(y) } \end{array}{}$$
---
##### Properties
> [!lemma] Proposition 1 (Convolution is Well-defined)
> For $f,g\in L^1(G)$, 
> 1. $f*g$ is well defined.
> 2. $f*g\in L^1(G)$.

> [!proof]-
> 
> Given $f,g\in L^1(G)$, consider $$\begin{array}{cccc} {}&{G\times G}&\to&{[0,+\infty]}\\&{(x,y)} &\mapsto & {\left| f(xy)g(y^{-1}) \right| } \end{array}{}$$which is positive and $\mu \times \mu$-measurable. Then, by [[Product Measure|Fubini]], $$\begin{align}\int_{G}^{} \int_{G}^{} \left| f(xy)g(y^{-1}) \right|  \, d\mu(y)  \, d\mu(x) &=\int_{G}^{} \left| g(y^{-1})  \right| \int_{G}^{} \left| f(xy) \right|  \, d\mu(x) \, d\mu(y)\\&=\int_{G}^{} \left| g(y^{-1})  \right| \int_{G}^{} \left| f(yx) \right|  \, d\mu(x) \, d\mu(y) \\&=\|f\|_{1}\cdot \int_{G}^{} \left| g(y^{-1})  \right|  d\mu(y) \\&=\|f\|_{1}\|g\|_{1}\end{align}$$Therefore, for $\mu$-a.e. $x\in G$, $$\int_{G}^{} \left| f(xy)  \right|\left| g(y^{-1}) \right|  \, d\mu(y)<+\infty $$and $$(f*g)(x):=\int_{G}^{} f(xy)g(y^{-1}) \, d\mu(y) <+\infty$$for a.e. $x\in G$ and: $$\|f*g\|_{1}=\int_{G}^{} \left| \int_{G}^{} f(xy)g(y^{-1}) \, d\mu(y)  \right|  \, d\mu(x)\leq \left\| f \right\| _{1}\left\| g \right\| _{1} $$
---
> [!lemma] Theorem 2 (Convolution Banach Algebra)
> Let $G$ be a locally compact Hausdorff abelian group. Then, $L^1(G)$ is a commutative [[C*-Algebra|involutive Banach algebra]] with the convolution product $*$ and the involution $f^{*}(x)=\overline{f(x ^{-1})}$

> [!proof]+
> We have that:
> 1. **Associativity of $*$**:
> 	$$\begin{align}((f*g)*h)(x)&=\int_{G}^{} (f*g)(xy)h(y^{-1}) \, d\mu(y)\\&=\int_{G}^{}\int_{G}^{} f(xyz)g(z^{-1}) h(y^{-1}) \, d\mu(z)\, d\mu(y)\end{align} $$
> 2. For $f\in L^1(G)$, $d\nu(x)=f(x)d\mu(x)$ is a complex measure on $G$ with $\left| v_{f} \right|=\left| f \right|_{\mu}$.. Then, $\mu,\nu$ are complex measures on $G$ and $\mu * \nu$ is a complex measure on $G\times G$ and $\mu * \nu=m_{*}(\mu \times \nu)$
---
