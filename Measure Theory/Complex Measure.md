#Definition #MeasureTheory #FunctionalAnalysis 
> [!definition]
> For a [[measure space]] $(X,\Sigma)$, a function $\mu:\Sigma\to \mathbb{C}$ is a ***complex measure*** if:
> 1. $\mu(\varnothing)=0$ and
> 2. $\mu$ is [[Additive Functions|$\sigma$-additive]].
- **Remark**: Notice that in contrast to positive measures, $\sum_{n=1}^{}\mu(A_{n})\in \mathbb{C}$, the series has to converge, especially for any permutation of indices. Hence, $\sum_{n=1}^{}\left| \mu(A_{n}) \right|<+\infty$, i.e. it absolutely converges by Riemann.
- **Related definition**: For a complex measure $\mu:\Sigma\to \mathbb{C}$, the ***total variation*** of $\mu$ is a positive measure $\left| \mu \right|:\Sigma\to [0,+\infty]$ s.t. $$\left| \mu \right| (E):=\sup \left\{ \left.  \sum_{i=1}^{\infty}\left| \mu(E_{i}) \right|    \right|E=\bigsqcup_{i=1}^{\infty}E_{i},E_{i}\in \Sigma \right\}$$and $\left\| \mu \right\|:=\left| \mu \right|(X)$.
---
##### Properties
> [!lemma] Theorem 1
> Let $\mu:\Sigma\to \mathbb{C}$ be a complex measure. Then, 
> 1. $\left| \mu(E) \right|\leq \left| \mu \right|(E)$ for all $E\in \Sigma$.
> 1. $\left| \mu \right|$ is a positive measure on $\Sigma$.
> 2. $\|\mu \|=\left| \mu \right|(X)<+\infty$

> [!proof]+
> > [!lemma] 
> > Let $z_{1},\dots,z_{n}\in \mathbb{C}$. Then, there exists a subset $S\subseteq[n]$ s.t. $$\left| \sum_{k\in S}^{}z_{i} \right| \geq \frac{1}{\pi}\sum_{k=1}^{n}\left| z_{k} \right| $$
> 
> > [!proof]-
> > Let $z_{k}=\left| z_{k} \right|e^{i\alpha_{k}}$ for all $k\in [n]$ s.t. $-\pi<\alpha_{k}\leq \pi$. Then, for $-\pi\leq\theta\leq \pi$, we define: $$S(\theta):=\{ k\in [n]:\cos(\alpha_{k}-\theta)>0 \}$$Then,
> > $$\begin{align}\left| \sum_{k\in S(\theta)}^{}z_{k} \right|&=\left| \sum_{k\in S(\theta)}^{}z_{k}e^{-i\theta} \right| \\&\geq \text{Re}\left( \sum_{k\in S(\theta)}^{}z_{k}e^{-i\theta} \right) \\&=\sum_{k\in S(\theta)}^{}\left| z_{k} \right| \cos(\alpha_{k}-\theta)\\& =\sum_{k=1}^{n}\left| z_{k} \right| \max\{ 0,\cos(\alpha_{k}-\theta) \}\\&=: f(\theta)\end{align}$$Then, $f:[-\pi,\pi]\to[0,+\infty)$ is continuous and there exists $\theta_{0}$ s.t. $f(\theta_{0})\geq f(\theta)$ for all $\theta\in [-\pi,\pi]$. Indeed, $$\begin{align}f(\theta_{0})\geq \frac{1}{2\pi}\int_{-\pi}^{\pi}f(\theta)  \, d\theta&=\sum_{k=1}^{n}\left| z_{k} \right| \frac{1}{2\pi}\int_{-\pi}^{\pi}\max\{ 0,\cos(\alpha_{k}-\theta) \}  \, d\theta \\&=\frac{1}{\pi}\sum_{k=1}^{n}\left| z_{k} \right|\end{align} $$ By choosing $S:=S(\theta_{0})$, we prove the statement.
> 
> Assume that $\left| \mu \right|(X)=\infty$. Then, $X=A_{1}\sqcup B_{1}$ with $\left| \mu(A_{1}) \right|,\left| \mu(B_{1}) \right|>1$.  Wlog, $\left| \mu \right|(B_{1})=+\infty$. Then, $B_{1}=A_{2}\sqcup B_{2}$ with $\left| \mu(A_{2}) \right|,\left| \mu(B_{2}) \right|>1$ and wlog $\left| \mu \right|(B_{2})=+\infty$. Therefore, we construct: $(A_{n})_{n}\subseteq \Sigma$ which are pairwise disjoint. This is a contradiction to $\sum_{n=1}^{}\left| \mu(A_{n}) \right|\in \mathbb{C}$. 
---

> [!lemma] Theorem 1
> Let $(X,\Sigma)$ be a measure space, $\mu:\Sigma\to[0,+\infty]$ a non-negative finite measure and $\nu:\Sigma\to \mathbb{C}$ a complex measure s.t. $$\left| \nu(A) \right|\leq \mu(A)\quad \forall A\in \Sigma$$
> Then, $d\nu=\rho d\mu$ where $\left| \rho \right|\leq 1$. Moreover, if $\nu$ is positive, then $0\leq\rho\leq 1$

> [!proof]-
> Let $f=\sum_{a\in\mathbb{C}}^{}a\chi_{f^{-1}[\{ a \}]}$ be a [[simple function]]. Then, $$\left| \int_{X}^{} f \, d\nu  \right| \leq \sum_{a\in \mathbb{C}}^{}\left| a \right| \left| \nu(f^{-1}[\{ a \}]) \right|\leq \sum_{a\in \mathbb{C}}^{}\left| a \right| \mu(f^{-1}[\{ a \}])=\int_{X}\left| f \right|  \, d\mu  $$
---
