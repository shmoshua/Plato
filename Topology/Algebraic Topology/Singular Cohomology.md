#Definition #AlgebraicTopology 

> [!definition]
> Let $(X,A)$ be a pair of [[Topological Space|topological spaces]] with $A\subseteq X$. For an [[abelian group]] $G$,
> 1. the ***singular cochain complex*** of $X$ and $(X,A)$ are given by: $$S^k(X;G):=\text{Hom}(S_{k}(X),G),\quad S^k(X,A;G):=\text{Hom}(S_{k}(X,A),G)$$with $\delta:=\partial ^{*}$ where $S_{k}(X)$ and $S_{k}(X,A)$ are the [[Singular Homology|singular chain complex]]. (c.f. [[Cochain Complex|Example 2]])
> 2. the ***singular cohomology*** is the cohomology of the [[Cochain Complex|cochain complexes]] above, denoted as $H^{*}(X;G)$ and $H^{*}(X,A;G)$.

- **Remark**: If $G=\mathbb{Z}$, we drop the $G$ in the notation and write $H^{*}(X)$ and $H^{*}(X,A)$ instead.
- **Related notation**: For $\varphi\in S^k(X;G)$ and $\sigma\in S_{k}(X)$ a [[p-Simplex|singular $k$-simplex]], $$\braket{ \varphi , \sigma } := \varphi(\sigma)\in G$$

---
##### Properties
> [!lemma] Lemma 1
> Let $\varphi\in S^k(X;G)$ and $\tau: \Delta^{k+1}\to X$ be a singular $(k+1)$-simplex. Then, 
> 1. $\braket{ \delta\varphi , \tau }=\braket{  \varphi,  \partial \tau}=\sum_{i=0}^{k+1}(-1)^i\braket{ \varphi , \tau \circ  F_{i}^{k+1} }$.

> [!proof]-
> We have:
> 1. Note that: $$\braket{ \delta\varphi , \tau } =\delta\varphi(\tau)=\varphi(\partial \tau)=\braket{ \varphi , \partial \tau }=\sum_{i=0}^{k+1}(-1)^i\braket{ \varphi , \tau \circ  F_{i}^{k+1} } $$

---
> [!lemma] Proposition 2 (Zeroth Cohomology)
> We have that:
> 1. $\varphi\in S^0(X;G)\cong G^X$.
> 2. Let $\sigma:[e_{0},e_{1}]\to X$ be a singular $1$-simplex. Then, $$\braket{ \delta\varphi , \sigma } =\braket{ \varphi ,  \partial \sigma}=\varphi(\sigma(e_{1}))-\varphi(\sigma(e_{0})) $$
> 3. $H^0(X;G)=Z^0(X ; G)$.