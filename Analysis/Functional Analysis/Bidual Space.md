#Definition #FunctionalAnalysis 

> [!definition]
> The ***bidual*** of a [[Analysis/Normed Space|normed space]] $(V,\|\cdot\|)$ is the set $V^{**}:= \mathcal{B}(V^{*},\mathbb{K})$. 
> 
> There exists a canonical linear map $J: V \to V^{**}$ defined by: $$J(v)(\lambda):=\lambda(v)$$
---
##### Properties
> [!lemma] Proposition 1
> The map $J:V \to V ^{**}$ is a $\mathbb{K}$-linear [[Bounded Linear Map|isometry]] into the Banach space $V^{**}$. This allows us to extend a normed space $V$ into a subspace of a Banach space isometrically, i.e. $\overline{J(V)}\subseteq V^{**}$ is a canonical completion of $V$.

>[!proof]-
>First, we have that: $$\left| J(v)(\lambda) \right|=\left| \lambda(v) \right| \leq \left\| \lambda \right\| \|v\| $$which shows that $J(v)\in (V^{*})^{*}$. Then, by [[Dual Space|Corollary 2]], $$\left\| J(v) \right\| =\sup_{\left\| \lambda \right\| \leq 1} \left| J(v)(\lambda) \right| =\sup_{\left\| \lambda \right\| \leq 1} \left| \lambda(v) \right| =\|v\|$$

- **Remark**: A normed space $V$ is called ***reflexive*** if $J$ is surjective. Then, $V$ is automatically [[Banach Space| Banach]].
---
