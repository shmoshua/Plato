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
> [!lemma] Theorem 3 (Covering Space CW-Complex)
> Let $\pi:X\to Y$ be a [[covering space]]. If $Y$ has a finite CW-complex structure, 
> 1. $\pi$ induces a finite CW-complex structure on $X$ s.t. $\chi(X)=k\chi(Y)$.

> [!proof]-
> Let $f_{\sigma}:B^n_{\sigma}\to Y^{(n)}$ be the characteristic map and $k$ be the \#sheets of the covering $\pi$. As $B^n_{\sigma}$ is simply-connected, there exist $k$ different [[Lift|lifts]] of $f_{\sigma}$, given by $f^{(1)}_{\sigma},\dots,f^{(k)}_{\sigma}:B^n_{\sigma}\to X^{(n)}$. Therefore, each $n$-cell is mapped to $k$ $n$-cells in $X$ and we have the statement by [[Topology/Algebraic Topology/Euler Characteristic|Theorem 1 Corollary]].

---
##### Examples
> [!h] Example 1 (Spheres)
> We have that:
> 1. $\chi(S^n)=\begin{cases}0&n\text{ is odd}\\2&n\text{ is even}\end{cases}$ for all $n\geq 1$.
> 2. Any covering map $\pi:S^n\to Y$ to a CW-complex $Y$, is either $2:1$ or a homeomorphism if $n$ is even
> 3. $\chi(\mathbb{R}\mathbb{P}^n)=1$ for even $n$.
> 4. Any covering map $\pi:\mathbb{R}\mathbb{P}^n\to Y$ to a CW-complex $Y$ is a homeomorphism if $n$ is even.

> [!proof]+
> We have that: 
> 1. $H_{p}(S^n)\cong \mathbb{Z}$ for $p=0$ and $p=n$ and $H_{p}(S^n)=0$ otherwise. Hence, by definition, we have the statement.
> 2. $2=\chi(S^n)=k\chi(Y)$ where $k$ is the number of sheets, which can only be 1 or 2.
> 3. As $\mathbb{R}\mathbb{P}^n\cong S^n / (x\sim -x)$, we have that the quotient map $\pi:S^n\to \mathbb{R}\mathbb{P}^n$ is a $2$-covering. The rest follows from 2. 
> 4. $1=\chi(\mathbb{R}\mathbb{P}^n)=k\chi(Y)$. Hence, $k=1$. 
---
