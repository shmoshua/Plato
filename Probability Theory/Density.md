#Definition #ProbabilityTheory 

> [!definition]
> Let $d>0$. A ***probability density function*** is a Borel function $p:\mathbb{R}^d\to \mathbb{R}_{\geq 0}$ s.t. $$\int_{\mathbb{R}^d}^{} p \, dx=1 $$
- **Related definition**: A [[random variable]] $X$ with values in $\mathbb{R}^d$ is said to have density $p$ if: $$\mathbb{P}_{X}(B)=\int_{B} p  \, dx,\quad \forall B\in \mathcal{B}_{\mathbb{R}^d} $$i.e. $\mathbb{P}_{X}=p\ dx$.
---
##### Properties
> [!lemma] Proposition 1
> Let $X=(X_{1},\dots,X_{d})$ be a random variable with values in $\mathbb{R}^d$ and density $p$. 
> 1. for every $j\in [d]$, $X_{j}$ has the density: $$p_{j}(x):=\int_{\mathbb{R}^{d-1}}^{} p(x_{1},\dots,x_{j-1},x,x_{j+1},\dots,x_{d}) \, dx_{1}\dots \widehat{ dx_{j}}\dots dx_{d} $$

> [!proof]-
> Let $\pi_{j}:\mathbb{R}^d\to \mathbb{R}$ be the $j$-th projection. Then, by Fubini, for every Borel function $f:\mathbb{R}\to \mathbb{R}_{\geq 0}$, $$\begin{align}\mathbb{E}[f(X_{j})]&=\mathbb{E}[f(\pi_{j}(X))]\\&=\int_{\mathbb{R}^d}f(x_{j}) p(x_{1},..,x_{d}) \, dx_{1}\dots dx_{d}\\&=\int_{\mathbb{R}}f(x_{j}) \left( \int_{\mathbb{R}^{d-1}}^{\infty} p(x_{1},\dots,x_{d}) \, dx_{1}\dots \widehat{dx_{j}}\dots dx_{d} \right)dx_{j}\\&=\int_{\mathbb{R}}^{} f(x_{j})p_{j}(x_{j}) \, dx_{j}  \end{align}$$
> 
- **Remark**: the density is well-defined by Fubini, i.e. $\{ x\in \mathbb{R}:p_{j}(x)=+\infty \}$ is zero measure and we can readily change the probability density there. 