#Definition #FunctionalAnalysis 
> [!definition]
> Let $(X,\mathcal{F},\mu)$ where $X$ is a [[locally compact Hausdorff space]], $\mu$ a positive [[Borel Measure|Borel regular measure]], $$L^p_{\text{loc}}(X)=\{ f:X\to \mathbb{C}|f\text{ measurable, }\forall K\subseteq X\text{ compact, }f\cdot \chi_{K}\in L^p(X) \}$$
---
##### Properties
> [!lemma] Proposition 1
> For $1\leq q\leq p$: $L^p_{\text{loc}}(X)\subseteq L^q_{\text{loc}}(X)$

> [!proof]-
> Follows from [[Lp Space|Lemma 5]].
---
> [!lemma] Proposition 3
> If $X=\bigcup_{n\geq 1}^{}K_{n}$ where $K_{n}$ is compact, then $L^p_{\text{loc}}(X)$ is metrizable. 

> [!proof]-
> For all compact $K\subseteq X$, we can define the semi-norm $\left\| f \right\|_{p,K}=\left\| f\cdot \chi_{K} \right\|_{p}$. Therefore, $\{ \|\cdot\|_{p,K_{n}} \}_{n\geq 1}$ is a sufficient countable set of semi-norms, and by [[Topological Vector Space with Seminorms|Proposition 4]], $L^p_{\text{loc}}(X)$ is metrizable.
---