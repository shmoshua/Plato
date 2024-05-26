#Definition #FunctionalAnalysis 

> [!definition]
> A [[Locally Compact Topological Group|LCH group]] $G$ is ***unimodular*** if the [[Haar Measure|modular function]] $\Delta_{G}\equiv 1$. 
- **Equivalent definition**: $G$ is unimodular if every left Haar measure is also a right Haar measure.
---
##### Properties
> [!lemma] Proposition 1
> For LCH group $G$, the following are equivalent:
> 1. $G$ is unimodular.
> 2. any left Haar measure $\mu$ of $G$ is inverse invariant, i.e. $\int_{G}^{} f(x) \, d\mu(x)=\int_{G}^{} f(x ^{-1}) \, d\mu(x)$

> [!proof]-
> (1=2) follows from [[Haar Measure|Corollary 3]]. For the other direction, from [[Haar Measure|Lemma 5]], $f\mapsto\Lambda(f^\vee)$ is a right Haar functional and $\mu$ is a right Haar measure. Therefore, $G$ is unimodular.
---
##### Examples
> [!h] Example 1 (Simple Unimodular Groups)
> We have that:
> 1. $(\mathbb{R}^n,+)$, $(\mathbb{R}^\times,\cdot)$.
> 3. Discrete groups.
> 4. $\text{GL}(n,\mathbb{R})$.
---
> [!h] Example 2 
> We have that:
> 1. Any [[LCA group]] is unimodular.
> 2. Any compact Hausdorff group is unimodular.

> [!proof]-
> We have:
> 1. For left Haar measure $\mu$ and $f\in C_{00}(G)$, $$\Delta_{G}(g)\int_{G}^{} f \, d\mu =\int_{G}^{} f(xg^{-1}) \, d\mu(x)=\int_{G}^{} f(g^{-1}x) \, d\mu(x)=\int_{G}^{}f  \, d\mu   $$Therefore, $\Delta_{G}(g)=1$. 
> 2. As $\Delta_{G}$ is a continuous homomorphism, $\Delta_{G}(G)$ is a compact subgroup of $\mathbb{R}^\times$. Therefore, $\Delta_{G}(G)=\{ 1 \}$. 
---
![[Lattice#^58e178]]
![[Lattice#^5ab53c|p]]
---
