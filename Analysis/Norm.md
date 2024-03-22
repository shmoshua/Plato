#Definition #Analysis

> [!definition]
> A ***norm*** on a $\mathbb{K}$-[[Vector Space|vector space]] $V$ is a function $\|\cdot \|:V \to [0,+\infty)$ s.t. the following holds:
> 1.  **Triangle inequality**: for all $v_{1},v_{2}\in V$: $$\left\| v_{1}+v_{2} \right\| \leq \left\| v_{1} \right\| +\left\| v_{2} \right\| $$
> 2. **Absolute homogeneity**: for all $v\in V$ and $a\in \mathbb{K}$: $$\| a v \|=|a|\cdot\|v\|$$
> 3. **Positive definiteness**: for all $v\in V$: $$\|v\|=0 \iff v=0$$
> 	where with 1,2,3 implies that $\|v\|\ge 0$ for all $v\in V$.


---
##### Properties
> [!lemma] Theorem 1
> The norm $\|\cdot\|:(V,F,\|\cdot\|)\to(\mathbb{R},\mathbb{R},|\cdot|)$ is a [[Continuous Functions in Normed Spaces|continuous function]] on $V$.

>[!proof]-
> For any $x\in V$ and $\varepsilon>0$, let $\delta=\varepsilon$. Then, if $\left\| x- x_{0}\right\|<\varepsilon$ then $|\|x\|-\|x_{0}\||\leq \|x-x_{0}\|<\varepsilon$ by the triangle identity.
---
##### Examples
> [!lh] Example 1 (Finite-dimensional Vector Space)
> On $\mathbb{K}^d$, we have: 
> 1. **$p$-norm**: $\|v\|^p:=\sum_{j=1}^{d}\left| v_{j} \right| ^p$
> 2. **maximum norm**: $\|v\|_{\infty}:=\max_{j\in[d]}\left| v_{j} \right|$

> [!proof]-
> We have:
> 1. Firstly, $\|\lambda v\|^p=\sum_{j=1}^{d}\left| \lambda \right|^p\left| v_{j} \right|^p=\left| \lambda \right|^p\|v\|^p$. Further, $\|v\|^p=0 \iff \left| v_{j} \right|=0$ for all $j\in[d]$. Lastly, the triangular inequality follows from the minkowski inequality.
---
> [!h] Example 2 (Operator Norm)
> Let $V,W$ be [[Normed Space|normed spaces]]. Then, the ***operator norm*** on [[Bounded Linear Map|$\mathcal{B}(V,W)$]] is defined as: $$\left\| T \right\| :=\sup_{v\neq 0}\frac{\left\| Tv \right\| _{W}}{\|v\|_{V}}$$
---