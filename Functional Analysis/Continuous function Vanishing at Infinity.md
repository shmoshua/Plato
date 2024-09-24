#Definition  #FunctionalAnalysis 
> [!definition]
> For a [[Topological Space]] $X$, $(C_{0}(X),\|\cdot\|_{b})$ denotes [[Normed Space|normed vector space]] of continuous functions $f:X\to \mathbb{\mathbb{C}}$ that ***vanish at infinity***, i.e. for all $\varepsilon>0$, there exists $K\subseteq X$ compact s.t $$\sup_{x\in X \backslash K}\left| f(x) \right| <\varepsilon$$
- **Remark**: if $X$ is compact, $C_{0}(X)=C(X)$.
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
> [!lemma] Theorem 3 (Real Stone-Weierstrass)
> Let $X$ be a [[Locally Compact Hausdorff Space]] and let $\mathcal{A}\subseteq C_{0}(X,\mathbb{R})$ be a subalgebra s.t. 
> 1. for all $x\in X$, there exists $f\in \mathcal{A}$ with $f(x)\neq 0$.
> 2. for all $x,y\in X$ with $x\neq y$, there exists $f\in \mathcal{A}$ with $f(x)\neq f(y)$.
> 
> Then, $\mathcal{A}$ is dense in $(C_{0}(X,\mathbb{R}),\|\cdot\|_{b})$, i.e. the topology of uniform convergence.

> [!proof]+
> We have:
> 1. **Claim: for $x\neq y\in X$, there exists $f\in \mathcal{A}$ s.t. $f(x)\neq f(y)$, $f(x)\neq 0$ and $f(y)\neq 0$.**
>    Assume otherwise. Let $f_{1}\in \mathcal{A}$ s.t. $f_{1}(x)\neq f_{1}(y)$. 
>    
>    If $f_{1}(y)\neq 0$, then, $f_{1}(x)=0$ by assumption. Then, let  $f_{2}\in \mathcal{A}$ with $f_{2}(x)\neq 0$.
>    
>    If $f_{2}(x)\neq f_{2}(y)$, then $f_{2}(y)=0$ and let $f:=f_{1}+cf_{2}$ where $c$ is a non-zero real number s.t. $f_{1}(y)\neq cf_{2}(x)$. Then, $f(x)=cf_{2}(x)\neq f_{1}(y)=f(y)$, and $f(x),f(y)$ are non-zero, which is a contradiction.
>    
>    Therefore, $f_{2}(x)=f_{2}(y)$ and let $f=f_{1}\pm f_{2}$. Then, $f(x)=\pm f_{2}(x)\neq f_{1}(y)\pm f_{2}(y)=f(y)$ and $f(x)$ and $f(y)$ are both non-zero, which is a contradiction.
>    
>    Therefore, $f_{1}(y)=0$ and by symmetry, $f_{1}(x)=0$. Which is again a contradiction. This shows that the claim holds.
> 2.  **Claim: for $x\neq y\in X$ and $a,b\in \mathbb{R}$, there exists $g\in \mathcal{A}$ s.t. $g(x)=a$ and $g(y)=b$.**
>    Consider the system: $$\begin{bmatrix}f(x)&f(x)^{2}\\f(y)&f(y)^{2}\end{bmatrix}\begin{bmatrix}\alpha\\\beta\end{bmatrix}=\begin{bmatrix}a\\b\end{bmatrix}$$where $f\in \mathcal{A}$ from claim 1. Then, as $f(x)f(y)(f(y)-f(x))\neq 0$, the matrix is invertible and for $\alpha,\beta$, $g:=\alpha f+\beta f^{2}$ is the desired function.
> 3. **Claim: for $f,g\in \mathcal{A}$, $\left| f \right|,\max\{ f,g \},\min\{ f,g \}\in \mathcal{A}$**.
>    
---

> [!lemma] Theorem 4 (Complex Stone-Weierstrass)
> Let $X$ be a [[Locally Compact Hausdorff Space]] and let $\mathcal{B}\subseteq C_{0}(X)$ be a subalgebra s.t. 
> 1. if $f\in \mathcal{B}$, then $\overline{f}\in \mathcal{B}$.
> 2. for all $x\in X$, there exists $f\in \mathcal{B}$ with $f(x)\neq 0$.
> 3. for all $x,y\in X$ with $x\neq y$, there exists $f\in \mathcal{B}$ with $f(x)\neq f(y)$.
> 
> Then, $\mathcal{B}$ is dense in $(C_{0}(X),\|\cdot\|_{b})$.

^2e5b88
