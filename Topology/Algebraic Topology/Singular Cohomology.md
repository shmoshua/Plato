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
> [!lemma] Proposition 2 (Zeroth and First Cohomology)
> We have that:
> 1. $H^0(X;G)\cong \prod_{c\in \pi_{0}(X)}^{}G$ where $\pi_{0}(X)$ is the set of path-connected components of $X$
> 2. $H^1(X;G)\cong \text{Hom}(H_{1}(X),G)$. 
> 3. If $X$ is path connected, then $H^1(X;G)\cong \text{Hom}(\pi_{1}(X),G)$

^c2af52

> [!proof]-
>  Firstly, notice that $\varphi\in S^0(X;G)\cong G^X$. Now, let $\sigma:[e_{0},e_{1}]\to X$ be a singular $1$-simplex. Then, $$\braket{ \delta\varphi , \sigma } =\braket{ \varphi ,  \partial \sigma}=\varphi(\sigma(e_{1}))-\varphi(\sigma(e_{0})) $$Now if $\varphi$ is a cocycle, then $\delta\varphi=0$ and $\varphi(\sigma(e_{1}))=\varphi(\sigma(e_{0}))$ for all $\sigma:[e_{0},e_{1}]\to X$. Hence for all $c\in \pi_{0}(X)$, $\varphi|_{c}$ is constant. The converse is also trivially true and this shows that $H^0(X;G)\cong \prod_{c\in \pi_{0}(X)}^{}G$. 

> [!proof]- Proof using UCT
> By [[Ext|UCT]]:
> 1.  we have the split SES: $$0 \to \text{Ext}(\underbrace{ H_{-1}(X) }_{ =0 },G) \to H^0(X;G)\to \text{Hom}(H_{0}(X),G) \to 0$$Hence, $\text{Ext}(H_{-1}(X) ,G) =0$ and $H^0(X;G)\cong \text{Hom}(H_{0}(X),G)$. However, as $H_{0}(X)\cong \bigoplus_{c\in \pi_{0}(X)}\mathbb{Z}$, we have the desired claim.
> 2. we have the split SES: $$0\to \text{Ext}(H_{0}(X),G)\to H^1(X;G)\to \text{Hom}(H_{1}(X),G)\to 0$$As $H_{0}(X)$ is free abelian, $\text{Ext}(H_{0}(X),G)=0$. Hnece, $$H^1(X;G)\cong \text{Hom}(H_{1}(X),G)$$
> 3. if $X$ is path connected, by [[p-Simplex|Hurewicz]] $H_{1}(X)\cong \pi_{1}(X)^\text{ab}$. However, as $G$ is abelian as well, $$H^1(X;G)\cong \text{Hom}(\pi_{1}(X)^{\text{ab}},G)\cong \text{Hom}(\pi_{1}(X),G)$$

^347df6

- **Remark**: Recall that $H_{0}(X;G)\cong \bigoplus_{c\in \pi_{0}(X)}G$. Hence, if $\pi_{0}(X)$ is finite $H_{0}(X;G)\cong H^0(X;G)$. However, if $\pi_{0}(X)$ is infinite, then $H^0(X;G)$ is a lot bigger than $H_{0}(X;G)$.  ^24d876
---
> [!lemma] Proposition 3
> Let $X$ be a topological space and $A\subseteq X$. 
> 1. $0\to S^k(X,A;G)\to S^k(X;G)\to S^k(A;G)\to 0$ is a split SES.
> 2. for the LES: $$\cdots \to H^{n-1}(A;G)\overset{ \delta ^{*} }{ \to }H^n(X,A;G)\to H^n(X;G)\to H^n(A;G)\overset{ \delta ^{*} }{ \to  }H^{n+1}(X,A;G)\to \cdots$$We have that: $$\begin{CD}0 @>>>\text{Ext}(H_{n-1}(A),G) @>>> H^n(A;G)@>h>>\text{Hom}(H_{n}(A),G) @>>> 0\\ & @VVV& @V\delta ^{*}VV& @V(\partial_{*})^{*}VV\\ 0 @>>>\text{Ext}(H_{n}(X,A),G) @>>> H^{n+1}(X,A;G)@>>h>\text{Hom}(H_{n+1}(X,A),G) @>>> 0\end{CD}$$commutes where $\partial_{*}:H_{n+1}(X,A)\to H_{n}(A)$.

> [!proof]+
> We have that:
> 1. Given as $S^k(X,A)$ is free abelian, $$0\to S_{k}(A)\to S_{k}(X)\to S_{k}(X,A)\to 0$$is a split SES and so is its dual.
> 2. The LES is given by the SES from 1. Then, let $[\varphi]\in H^n(A;G)$ where $\varphi: S_{n}(A)\to G$. Then, $$((\partial_{*})^{*} \circ h)([\varphi])=(\partial_{*})^{*}(\overline{\varphi})=\overline{\varphi} \circ  \partial_{*}$$where for $[\psi]\in H_{n+1}(X,A)$ with $\psi\in S_{n+1}(X,A)$ with $\partial \psi=0$. Then, it holds by definition that there exists $\psi'\in S_{n+1}(X)$ and $\phi\in S_{n}(A)$ s.t. $\phi=\partial \psi'$ and $q(\psi')=\psi$ s.t. $$\partial_{*}([\psi])=[\phi]$$We get that $((\partial_{*})^{*} \circ h)([\varphi])[\psi]=\overline{\varphi}([\phi])=\varphi(\phi)$.
>    
>    Let $\Phi:S^n(X;G)$. Then, $\delta ^{*}([\Phi|_{S_{n}(A)}])=[\Psi]$ for $\Psi\in S^{n+1}(X,A;G)$ where $\Psi \circ q=\Phi \circ \partial$
>    
>    Similarly, for $\delta ^{*}([\varphi])$, 
---
##### Examples
> [!h] Example 1
> Let $(X,A)$ be a pair of spaces and $i:A\to X$ the inclusion. 
> 1. $i^c:S^{*}(X)\to S^{*}(A),\alpha\mapsto \alpha|_{S_{*}(A)}$.

^bdcafc

---
