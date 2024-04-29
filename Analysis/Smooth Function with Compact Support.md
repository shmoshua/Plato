#Definition #Analysis #FunctionalAnalysis 

> [!definition]
> For a topological space $X$, the ***support*** of a function $f:X\to \mathbb{R}$ is defined as: $$\text{supp }f:=\overline{f^{-1}[\mathbb{C}\backslash\{ 0 \}]}$$
> Further if $\text{supp }f$ is compact and $f$ is smooth, then $f$ is a smooth function with compact support, i.e. $f\in C_{00}^\infty(X)$.
- **Remark**: If $X$ is Euclidean, bounded support means compact support. 
---
##### Properties
> [!lemma] Proposition 1
> Let $\Omega \subseteq \mathbb{R}^n$ be an open subset and $1\leq p<+\infty$. Then, $C_{00}^\infty(\Omega)$ is dense in $L^p(\Omega,m)$ where $m$ is a [[Borel Measure|Borel regular measure]]. 

> [!proof]-
> As $\Omega$ is locally compact and $m$ is Borel regular, $C_{00}(\Omega)$ is dense in $L^p(\Omega)$. So we will show that $C_{00}^\infty(\Omega)$ is dense in $C_{00}(\Omega)$. 
> 
> For $f\in C_{00}(\Omega)$, since $\text{supp }f$ is compact and $\text{supp }f\subseteq\Omega$, there exists $\varepsilon_{0}>0$ s.t. $$\text{supp }f+B_{\leq \varepsilon_{0}r}(0)\subseteq\Omega$$for $r$ s.t. $\text{supp }\delta \subseteq B_{\leq r}(0)$. 
> 
> Then, for all $\varepsilon<\varepsilon_{0}$, $$\text{supp}(\delta_{\varepsilon}*f)\subseteq \text{supp}(\delta_{\varepsilon})+\text{supp}(f)\subseteq B_{\leq \varepsilon r}+\text{supp}(f)\subseteq \Omega$$ and $\delta_{\varepsilon}*f\in C_{00}(\Omega)$ and from [[Convolution (Rn)|Proposition 4]], $\delta_{\varepsilon}*f\in C^\infty_{00}(\Omega)$. Lastly, by [[Approximate Identity|Proposition 2]], $\delta_{\varepsilon}*f\xrightarrow{L^p}f$ as $\varepsilon\to 0$.
---
> [!lemma] Lemma 2 (used in Plancherel)
> Let $1\leq p_{1},p_{2}<+\infty$ and $f\in L^{p_{1}}(\mathbb{R}^n)\cap L^{p_{2}}(\mathbb{R}^n)$. Then, there exists $(\varphi_{k})_{k}\subseteq C_{00}^\infty(\mathbb{R}^n)$ s.t. 
> 1. $\varphi_{k}\to f$ in $L^{p_{1}}$ and
> 2. $\varphi_{k}\to f$ in $L^{p_{2}}$ 

> [!proof]-
> Let $\chi_{R}:=\chi_{B_{<R}(0)}$. For $\varepsilon>0$ there exists $R$ s.t. $$\left\| f(1-\chi_{R}) \right\|_{p_{1}} <\varepsilon,\quad \left\| f(1-\chi_{R}) \right\|_{p_{2}} <\varepsilon$$
> Now, $f\cdot \chi_{R}\in L^{p_{1}}\cap L^{p_{2}}$ and has compact support. Therefore, $$\delta_{1 / k}*(f\cdot \chi_{R})\in C_{00}^\infty(\mathbb{R}^n)$$
> by [[Convolution (Rn)|Proposition 4]]. Further, by [[Approximate Identity|Proposition 2]], $$\delta_{1/k}*(f\cdot \chi_{R})\xrightarrow{k\to \infty}f\cdot \chi_{R}$$ in both $L^{p_{1}}$ and $L^{p_{2}}$. 
---
