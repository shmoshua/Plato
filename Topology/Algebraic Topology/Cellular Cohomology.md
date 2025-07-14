#Definition #AlgebraicTopology 

> [!definition]
> Let $X$ be a [[CW-complex]] and $G$ an [[abelian group]].
> 1. the ***cellular cohomology*** of $X$ is $H^{*}(\mathcal{C}_{\text{cw}}^{*}(X);G)$ where $\mathcal{C}^{*}_{\text{cw}}(X):=\text{Hom}(\mathcal{C}_\text{cw}(X),G)$ and $\mathcal{C}_{\text{cw}}(X)$ is the [[cellular chain complex]] of $X$.

^8b568d

---
##### Properties
> [!lemma] Theorem 1
> Let $X$ be a CW-complex and $G$ an abelian group.
> 1. $H^n(\mathcal{C}^{*}_{\text{cw}}(X);G)\cong H^n(X;G)$

^484cae

> [!proof]-
> We have that:
> 1. By [[Ext|UCT]], we have: $$\begin{CD}0 @>>>\text{Ext}(H_{n-1}^{\text{cw}}(X),G)@>>> H^{n}(\mathcal{C}^{*}_{\text{cw}}(X);G)@>>> \text{Hom}(H_{n }^{\text{cw}}(X),G)@>>>0\\ & @V\cong VV&&@V\cong VV\\0 @>>>\text{Ext}(H_{n-1}(X),G)@>>> H^{n}(X;G)@>>> \text{Hom}(H_{n}(X),G)@>>>0\end{CD}$$where the isomorphisms follow from $H_{p}^\text{cw}(X)\cong H_{p}(X)$ from [[Cellular Chain Complex|Proposition 1]]. Note that we don't have a canonical map for the middle. However, as the SES both split by UCT, $$\begin{aligned}H^n(\mathcal{C}^{*}_{\text{cw}}(X);G)&\cong \text{Ext}(H_{n-1}^{\text{cw}}(X),G) \oplus \text{Hom}(H_{n }^{\text{cw}}(X),G)\\&\cong \text{Ext}(H_{n-1}(X),G) \oplus \text{Hom}(H_{n}(X),G)\cong  H^n(X;G)\end{aligned}$$

^f7a432

---
