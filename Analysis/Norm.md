#Definition #Analysis

> [!definition]
> A ***norm*** on a $\mathbb{K}$-[[Vector Space|vector space]] $V$ is a function $\|\cdot \|:V \to [0,+\infty)$ s.t. the following holds:
> 1.  **Triangle inequality**: for all $v_{1},v_{2}\in V$: $$\left\| v_{1}+v_{2} \right\| \leq \left\| v_{1} \right\| +\left\| v_{2} \right\| $$
> 2. **Absolute homogeneity**: for all $v\in V$ and $a\in \mathbb{K}$: $$\| a v \|=|a|\cdot\|v\|$$
> 3. **Positive definiteness**: for all $v\in V$: $$\|v\|=0 \iff v=0$$
> 	where with 1,2,3 implies that $\|v\|\ge 0$ for all $v\in V$.


---
##### Properties
> [!lemma] Theorem Norm.1
> The norm $\|\cdot\|:(V,F,\|\cdot\|)\to(\mathbb{R},\mathbb{R},|\cdot|)$ is a [[Continuous Functions in Normed Spaces|continuous function]] on $V$.

>[!proof]-
> For any $x\in V$ and $\varepsilon>0$, let $\delta=\varepsilon$. Then, if $\left\| x- x_{0}\right\|<\varepsilon$ then $|\|x\|-\|x_{0}\||\leq \|x-x_{0}\|<\varepsilon$ by the triangle identity.
---
##### Related Definitions
- [[Open and Closed Balls]]