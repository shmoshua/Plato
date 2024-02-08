#Analysis #Definition #FunctionalAnalysis 

> [!definition]
> A function $f\in L^p(\mathbb{R}^d)$ w.r.t the [[Lebesgue Measure|Lebesgue measure]] has ***weak derivatives*** in $L^p$ up to order $k\in\mathbb{N}$ if for every $(\alpha_{1},\dots,\alpha_{d})\in \mathbb{N}^d$ with $|\alpha|:=\alpha_{1}+\cdots+\alpha_{d}\leq k$, there exists $g_{\alpha}\in L^p(\mathbb{R}^d)$ s.t. $$\int _{\mathbb{R}^d}g_{\alpha}(x)\varphi(x) \, d\mathcal{L}(x)=(-1)^{\left| \alpha \right| }\int _{\mathbb{R}^d}f(x) \partial_{x}^\alpha\varphi(x) \, d\mathcal{L}(x)  $$for all $\varphi \in C^{\infty}(\mathbb{R}^d)$. Then, we write with abuse of notation: $$g_{\alpha}(x)=\partial^\alpha_{x}f$$and the call the function space $L^p_{k}(\mathbb{R}^d)$.

- **Remark**: If $f\in C^\infty(\mathbb{R}^d)$, then $$g_{\alpha}(x)=\partial^\alpha_{x} f(x)$$by integration by parts. 
- **Remark**: The norm: $$\left\| f \right\| _{{L^p_{k}(\mathbb{R}^d)}}:=\sum_{\left| \alpha \right| \leq k}^{}\left\| \partial^\alpha_{x}f \right\| _{p}$$gives us a [[Banach Space|Banach space]].
---

