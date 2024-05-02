#Definition #FunctionalAnalysis 

> [!definition]
>  For a [[Linear Map|linear map]] $T:V \to W$, $T$ has ***finite-rank***, if $\text{Im}(T)\subseteq W$ is finite-dimensional.
---
##### Properties
> [!lemma] Theorem 1
> For a finite-rank linear operator $T:V\to W$, if $T\in \mathcal{B}(V,W)$, then it  is [[Compact Operator|compact]].

> [!proof]-
> As $T$ is bounded, $T(B_{\leq 1}(0))\subseteq\text{Im}(T)$ is bounded. Further, $\text{Im}(T)$ is a finite-dimensional normed space, which is isomorphic to $\mathbb{R}^n$. Therefore, from [[Heine-Borel]], $T(B_{<1}(0))$ is pre-compact, i.e. $\overline{T(B_{<1}(0))}$ is compact.
---