#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. 
> 1. An [[atlas]] $\mathcal{A}$ on $M$ is ***oriented*** if for any two overlapping charts $(U_{\alpha},\varphi_{\alpha}),(U_{\beta},\varphi_{\beta})$ in $\mathcal{A}$, the coordinate transformation $\theta_{\beta\alpha}:\varphi_{\alpha}(U_{\alpha}\cap U_{\beta})\to\varphi_{\beta}(U_{\alpha}\cap U_{\beta})$ has the property that: $$\det d_{x}\theta_{\beta\alpha}>0,\quad \forall x\in\varphi_{\alpha}(U_{\alpha}\cap U_{\beta})$$
> 2. $M$ is ***orientable*** if it admits an oriented atlas.
- **Remark**: In an orientable manifold, $d_{p}\varphi:\text{T}_{p}M\to \mathbb{R}^m$ is orientation-preserving.
---
##### Properties
> [!lemma] Proposition 1
> Let $M$ be a [[smooth manifold]]. The following are equivalent:
> 1. $M$ is orientable.
> 2. $M$ admits a [[volume form]].
