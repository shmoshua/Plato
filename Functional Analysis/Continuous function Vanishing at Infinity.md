#Definition  #FunctionalAnalysis 
> [!definition]
> For a [[topological space]] $X$, $(C_{0}(X),\|\cdot\|_{b})$ denotes [[Normed Space|normed vector space]] of continuous functions $f:X\to \mathbb{\mathbb{C}}$ that ***vanish at infinity***, i.e. for all $\varepsilon>0$, there exists $K\subseteq X$ compact s.t $$\sup_{x\in X \backslash K}\left| f(x) \right| <\varepsilon$$
---
##### Properties
> [!lemma] Proposition 1
> $(C_{0}(X),\|\cdot\|_{b})$ is a [[Banach space]].

> [!proof]-
> Let $(f_{n})_{n}$ be a [[Cauchy sequence]] in $C_{0}(X)$. Then, for all $x\in X$, $(f_{n}(x))_{n}$ is a Cauchy sequence and there exists $f_{n}\to f$ pointwise.
> 1. **$f$ is continuous** by the uniform convergence theorem.
> 2. **$f$ vanishes at infinity**: let $\varepsilon>0$. Then, there exists $N$ s.t. $\left\| f_{n}-f_{m} \right\|_{b}<\varepsilon$ for all $n,m\geq N$. Further, there exists $K\subseteq X$ compact s.t. $\left| f_{N}(x) \right|<\varepsilon$ for all $x\in X \backslash K$. Therefore, for $x\in X \backslash K$, $$\left| f(x) \right| \leq \left| f(x)-f_{N}(x) \right| +\left| f_{N}(x) \right|< \varepsilon+\varepsilon=2\varepsilon$$
> 3. **$f_{n}$ converges to $f$ in norm**: for $\varepsilon>0$, there exists $N$ s.t. $$\left| f_{n}(x)-f_{m}(x) \right|\leq \left\| f_{n}-f_{m} \right\|_{b} <\varepsilon $$for all $n,m\geq N$. By taking $m\to \infty$, $\left| f_{n}(x)-f(x) \right|\leq \varepsilon$ for all $n\geq N$ and $\left\| f_{n}-f \right\|_{b}\leq \varepsilon$.
---
> [!lemma] Proposition 2
> $C_{0}(X,\mathbb{C})^{*}$ is the space of [[Analysis/Complex Measure|complex measures]] $\mu:\mathcal{B}_{X}\to \mathbb{C}$.
---
> [!lemma] Theorem 3 (Stone-Weierstrass)
> Let $X$ be a [[locally compact Hausdorff space]] and let $\mathcal{B}\subseteq C_{0}(X)$ be a subalgebra s.t. 
> 1. if $f\in \mathcal{B}$, then $\overline{f}\in \mathcal{B}$.
> 2. for all $x\in X$, there exists $f\in \mathcal{B}$ with $f(x)\neq 0$.
> 3. for all $x,y\in X$ with $x\neq y$, there exists $f\in \mathcal{B}$ with $f(x)\neq f(y)$.
> 
> Then, $\mathcal{B}$ is dense in $(C_{0}(X),\|\cdot\|_{\infty})$.