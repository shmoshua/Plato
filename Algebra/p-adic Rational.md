#Definition #Algebra #FunctionalAnalysis 
> [!definition]
> For a prime $p$, the $p$-adic rational $\mathbb{Q}_{p}$ is the [[Quotient Field|quotient field]] of $\mathbb{Z}_{p}$, i.e. $$\mathbb{Q}_{p}:=\left\{  \frac{x}{y}:x\in \mathbb{Z}_{p},  \right\}$$
- **Remark**: Every $0\neq x\in \mathbb{Q}_{p}$ can be uniquely written as $x=p^ku$ for $k\in \mathbb{Z}$ and $u\in U$, the set of invertible elements in $\mathbb{Z}_{p}$. 
- **Related definition**: The ***valuation*** is a function $v_{p}:\mathbb{Q}_{p}\to \mathbb{Z}\cup \{ +\infty \}$ with $v_{p}(x)=k$ and $v_{p}(0)=+\infty$.
- **Related definition**: The ***norm***  $\|x\|_{p}:=e^{-v_{p}(x)}$ on $\mathbb{Q}_{p}$.
---
##### Properties
> [!lemma] Lemma 1
> We have:
> 1. $\mathbb{Q}_{p}$ with $d_{p}$ is locally compact.
> 2. $\mathbb{Z}_{p}\subseteq \mathbb{Q}_{p}$ is an open subring.
> 3. $\mathbb{Q}_{p}$ is not compact as $\|p^{-n}\|=e^n$.
> 4. $\mathbb{Q}$ is dense in $\mathbb{Q}_{p}$.
---
> [!lemma] Theorem 2
> Let $\mathbb{K}$ be a locally compact non-discrete field of $\text{char }k=0$. Then, if the image of $\mathbb{Q}\hookrightarrow \mathbb{K}$ is dense, then either $\mathbb{K}=\mathbb{R}$ or $\mathbb{K}=\mathbb{Q}_{p}$ for some prime $p$.
---
