#Definition #AlgebraicTopology 

> [!definition]
> Let $(X,A)$ be a pair of [[Topological Space|topological spaces]] with $A\subseteq X$. For an [[abelian group]] $G$,
> 1. the ***singular cochain complex*** of $X$ and $(X,A)$ are given by: $$S^k(X;G):=\text{Hom}(S_{k}(X),G),\quad S^k(X,A;G):=\text{Hom}(S_{k}(X,A),G)$$with $\delta:=\partial ^{*}$ where $S_{k}(X)$ and $S_{k}(X,A)$ are the [[Singular Homology|singular chain complex]]. (c.f. [[Cochain Complex|Example 2]])
> 2. the ***singular cohomology*** is the cohomology of the [[Cochain Complex|cochain complexes]] above, denoted as $H^{*}(X;G)$ and $H^{*}(X,A;G)$.

^0b465b

- **Remark**: If $G=\mathbb{Z}$, we drop the $G$ in the notation and write $H^{*}(X)$ and $H^{*}(X,A)$ instead. ^3c2ae9
- **Related notation**: For $\varphi\in S^k(X;G)$ and $\sigma\in S_{k}(X)$ a [[p-Simplex|singular $k$-simplex]], $$\braket{ \varphi , \sigma } := \varphi(\sigma)\in G$$ ^e3d114
- **Related definition**: For a continuous function $f:X\to Y$: ^ca7ab3
	1. $f_{c}:S_{*}(X)\to S_{*}(Y)$ is a chain map.
	2. $f^c:S^*(Y)\to S^{*}(X),\varphi\mapsto \varphi \circ f_{c}$ is a cochain map. (c.f. [[Cochain Complex|Example 2]])
	3. $f^{*}:H^{*}(Y;G)\to H^{*}(X;G)$

---
##### Properties
> [!lemma] Lemma 1
> Let $\varphi\in S^k(X;G)$ and $\tau: \Delta^{k+1}\to X$ be a singular $(k+1)$-simplex. Then, 
> 1. $\braket{ \delta\varphi , \tau }=\braket{  \varphi,  \partial \tau}=\sum_{i=0}^{k+1}(-1)^i\braket{ \varphi , \tau \circ  F_{i}^{k+1} }$.

^e6ca50

> [!proof]-
> We have:
> 1. Note that: $$\braket{ \delta\varphi , \tau } =\delta\varphi(\tau)=\varphi(\partial \tau)=\braket{ \varphi , \partial \tau }=\sum_{i=0}^{k+1}(-1)^i\braket{ \varphi , \tau \circ  F_{i}^{k+1} } $$

^76f5e7

---
> [!lemma] Proposition 2 (Zeroth Cohomology)
> We have that:
> 1. $H^0(X;G)\cong \prod_{c\in \pi_{0}(X)}^{}G$ where $\pi_{0}(X)$ is the set of path-connected components of $X$

^c2af52

> [!proof]-
>  Firstly, notice that $\varphi\in S^0(X;G)\cong G^X$. Now, let $\sigma:[e_{0},e_{1}]\to X$ be a singular $1$-simplex. Then, $$\braket{ \delta\varphi , \sigma } =\braket{ \varphi ,  \partial \sigma}=\varphi(\sigma(e_{1}))-\varphi(\sigma(e_{0})) $$Now if $\varphi$ is a cocycle, then $\delta\varphi=0$ and $\varphi(\sigma(e_{1}))=\varphi(\sigma(e_{0}))$ for all $\sigma:[e_{0},e_{1}]\to X$. Hence for all $c\in \pi_{0}(X)$, $\varphi|_{c}$ is constant. The converse is also trivially true and this shows that $H^0(X;G)\cong \prod_{c\in \pi_{0}(X)}^{}G$. 

^347df6

- **Remark**: Recall that $H_{0}(X;G)\cong \bigoplus_{c\in \pi_{0}(X)}G$. Hence, if $\pi_{0}(X)$ is finite $H_{0}(X;G)\cong H^0(X;G)$. However, if $\pi_{0}(X)$ is infinite, then $H^0(X;G)$ is a lot bigger than $H_{0}(X;G)$.  ^24d876
---
##### Examples
> [!h] Example 1
> Let $(X,A)$ be a pair of spaces and $i:A\to X$ the inclusion. 
> 1. $i^c:S^{*}(X)\to S^{*}(A),\alpha\mapsto \alpha|_{S_{*}(A)}$.

^bdcafc

---
