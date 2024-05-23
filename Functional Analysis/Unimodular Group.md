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
> [!h] Example 1
> We have that:
> 1. $(\mathbb{R}^n,+)$, $(\mathbb{R}^\times,\cdot)$.
> 3. Discrete groups.
> 4. $\text{GL}(n,\mathbb{R})$.
---