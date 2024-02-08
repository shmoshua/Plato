#Definition #FunctionalAnalysis 

> [!definition]
> For a set $X$, a ***complex [[Measure|measure]]*** is a function $\mu: \mathcal{B}(X)\to \mathbb{C}$ defined on the [[Borel Sigma-Algebra|Borel $\sigma$-algebra]] $\mathcal{B}(X)$ s.t. for all $E\in \mathcal{B}(X)$ and $E=\bigcup_{i=1}^{\infty}E_{i}$ a disjoint union, then: $$\mu(E)=\sum_{i=1}^{\infty}\mu(E_{i})$$

- **Remark**: Riemann states that this is absolutely convergent.
- **Related Definition**: for a complex measure $\mu:\mathcal{B}(X)\to \mathbb{C}$,  the ***total variation*** of $\mu$ is defined as:$$\left| \mu \right| (E):=\sup\left\{   \sum_{i=1}^{\infty}\left| \mu(E_{i}) \right| : E=\bigcup_{i=1}^{\infty}E_{i}\text{ a partition}  \right\}$$Then, 
   1. $|\mu|$ is a $\sigma$-additive positive measure and
   2. $\left| \mu \right|(X)<+\infty$.
- **Related definition**: a complex measure $\mu$ is regular if $\left| \mu \right|$ is [[Borel Measure|Borel regular]]. 
---
##### Complex Measures as Dual of Continuous Vanishing Functions
For $\mu:\mathcal{B}(X)\to \mathbb{C}$, we can write $\mu=\mu_{1}+i \mu_{2}$ where $\mu_{1},\mu_{2}:\mathcal{B}(X)\to \mathbb{R}$ called **signed measures**. Each signed measure can be decomposed into $\mu_{i}=\mu_{i}^+ -\mu_{i}^-$ where $\mu_{i}^+(X)<+\infty$ and $\mu_{i}^-(X)<+\infty$

Therefore, we have: $$\mu=(\mu_{1}^+ -\mu_{1}^-)+i(\mu_{2}^+ -\mu_{2}^-)$$and hence $\int_{X}^{} f \, d\mu(x)$ makes sense for all $f\in C_{0}(X,\mathbb{C})$.

> [!lemma] Theorem (Riesz Representation)
> For every [[Bounded Linear Map|bounded linear map]] $\Phi:C_{0}(X,\mathbb{C})\to \mathbb{C}$, there is a unique regular complex measure $\mu$ s.t. $$\Phi(f)=\int_{X}^{} f \, d\mu $$Further, it holds that: $\left\| \Phi \right\|=\left| \mu \right|(X)$.
