#Definition #AlgebraicTopology 

> [!definition]
> Let $\mathcal{C}:=\{ C_{p} \}_{p\in \mathbb{Z}}$ be a [[graded abelian group]] s.t. $C_{p}$ is [[Finitely Generated Abelian Group|finitely generated]] for all $p\in \mathbb{Z}$ and $C_{p}\neq 0$ for finitely many $p$'s.
> 1. The ***Euler characteristic*** of $\mathcal{C}$ is defined as: $$\chi(\mathcal{C}):=\sum_{p\in \mathbb{Z}}^{}(-1)^p\text{rank}(C_{p})\in \mathbb{Z}$$
- **Related definition**: For a topological space $X$ of bounded finite type, i.e. $H_{p}(X)$ is finitely generated for all $p\in \mathbb{Z}$ and $H_{p}(X)\neq 0$ for only finitely many $p$'s, 
	- $\chi(X):=\chi(H_{*}(X))$.
---
##### Properties
> [!lemma] Theorem 1
> Let $\mathcal{C}$ be a chain complex of bounded finite type, i.e. for all $p\in \mathbb{Z}$, $C_{p}$ is finitely generated for all $p\in \mathbb{Z}$ and $C_{p}\neq 0$ for finitely many $p$'s. Then, 
> 1. $\chi(\mathcal{C})=\chi(H_{*}(\mathcal{C}))$

> [!proof]-
> Let $Z_{i}\subseteq C_{i}$ be the subgroup of cycles and $B_{i}\subseteq Z_{i}$, the subgroup of boundaries. Then, $$ 0\to B_{i}\hookrightarrow Z_{i}\to H_{i}(\mathcal{C})\to 0$$is an exact sequence of finitely generated abelian groups and by [[Finitely Generated Abelian Group|Theorem 6]], $$\text{rank}(Z_{i})=\text{rank}(B_{i})+\text{rank}(H_{i}(\mathcal{C}))$$Similarly, $$0\to Z_{i}\hookrightarrow C_{i}\xrightarrow{\partial} B_{i-1}\to 0$$is an exact sequence of finitely generated abelain groups. Therefore, $$\text{rank}(C_{i})=\text{rank}(Z_{i})+\text{rank}(B_{i-1})$$Bringing everything together, $$\begin{align}\chi(\mathcal{C})&=\sum_{p\in \mathbb{Z}}^{}(-1)^p \text{rank}(C_{p})=\sum_{p\in \mathbb{Z}}^{}(-1)^p( \text{rank}(Z_{p})+\text{rank}(B_{p-1}))\\&=\sum_{p\in \mathbb{Z}}^{}(-1)^p( \text{rank}(B_{p})+\text{rank}(H_{p}(\mathcal{C}))+\text{rank}(B_{p-1}))\\&=\sum_{p\in \mathbb{Z}}^{}(-1)^p\text{rank}(H_{p}(\mathcal{C}))+\sum_{p\in \mathbb{Z}}^{}(-1)^p\text{rank}(B_{p})-\sum_{p\in \mathbb{Z}}^{}(-1)^p\text{rank}(B_{p})\\&=\chi(H_{*}(\mathcal{C}))\end{align}$$
- **Corollary**: For a finite CW-complex $X$, we have that: $$\chi(X)=\chi(H_{*}(X))=\chi(H_{*}(\mathcal{C}(X)))=\chi(\mathcal{C}(X))=\sum_{p\in \mathbb{Z}}^{}(-1)^p\text{rank}(C_{p}(X))=\sum_{p\in \mathbb{Z}}^{}(-1)^p\left| I_{p} \right| $$
---
> [!lemma] Theorem 2 (Euler)
> Given any finite CW-complex structure on $S^{2}$, 
>  $$\left| I_{2} \right| -\left| I_{1} \right| -\left| I_{0} \right| =2$$

> [!proof]-
> We have that a finite CW-complex structure $X$ has no cells of dimension $\geq 3$. Hence, we have that: $$\left| I_{2} \right| -\left| I_{1} \right| +\left| I_{0} \right| =\chi(X)=\chi(H_{*}(X))=\text{rank}(\mathbb{Z})+\text{rank}(\mathbb{Z})=2$$
---
