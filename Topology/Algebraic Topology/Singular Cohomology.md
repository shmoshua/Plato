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

^faa1c5

> [!proof]-
> We have that:
> 1. Given as $S^k(X,A)$ is free abelian, $$0\to S_{k}(A)\to S_{k}(X)\to S_{k}(X,A)\to 0$$is a split SES and so is its dual.
> 2. The LES is given by the SES from 1. 
>    
>    Let $\Phi:S^n(X;G)$. Then, $\delta ^{*}([\Phi|_{S_{n}(A)}])=[\Psi]$ for $\Psi\in S^{n+1}(X,A;G)$ where $\Psi \circ q=\Phi \circ \partial$ with $q:S_{n+1}(X)\to S_{n+1}(X,A)$. Therefore, $$(h \circ \delta ^{*})([\Phi|_{S_{n}(A)}])=h[\Psi]=\overline{\Psi}$$Similarly, $h([\Phi|_{S_{n}(A)}])=\overline{\Phi|_{Z_{n}(A)}}$ and for $[c]\in H_{n+1}(X,A)$, there exists $b\in S_{n+1}(X)$ and $a\in S_{n}(A)$ s.t. $a=\partial b$ and $q(b)=c$. $$\overline{\Phi|_{Z_{n}(A)}} \circ \partial_{*}([c])=\overline{\Phi|_{Z_{n}(A)}} ([a])=\Phi(a)=\Phi \circ  \partial(b)=\Psi \circ  q(b)=\Psi(c)=\overline{\Psi}([c])$$This proves the statement.

^b8c240

---
> [!lemma] Proposition 4 (Singular Cohomology Properties)
> Let $X,Y$ be topological spaces. 
> 1. **(homotopy invariance):** if $f,g:(X,A)\to (Y,B)$ and $f\simeq g$, then $f^{*}=g^{*}$.
> 2. **(excision):** for $Z\subseteq A$ with $\overline{Z}\subseteq A^\circ$, $$i^{*}:H^n(X,A;G)\overset{ \cong }{ \to }H^n(X \backslash Z, A \backslash Z;G)$$is an isomorphism where $i:(X \backslash Z, A \backslash Z)\to (X, A)$ is the inclusion map.
> 3. **(Mayer-Vietoris):** for $A,B\subseteq X$ s.t. $A^\circ \cup B^\circ =X$, there exists a LES: $$\dots\to H^n(X;G)\to H^n(A;G)\oplus H^n(B;G)\to H^n(A\cap B;G)\to H^{n+1}(X;G)\to \cdots $$

^081c9f

> [!proof]-
> We have that:
> 1. If $f\simeq g$, then $f_{c}$ and $g_{c}$ are chain homotopic, i.e. $f_{c}\sim g_{c}$. In other words, $f^c\sim g^c$, i.e. $f^c$ and $g^c$ are cochain homotopic. Hence, $f^{*}=g^{*}$.
> 2. Let $i_{*}:H_{n}(X \backslash Z, A \backslash Z)\to H_{n}(X, A)$ be the map in homology, which is an isomorphism from [[Singular Homology|Theorem 3]]. Hence, by UCT: $$\begin{CD} 0 @>>>\text{Ext}(H_{n-1}(X \backslash Z, A\backslash Z),G)@>>> H^n(X \backslash Z, A\backslash Z;G)@>>> \text{Hom}(H_{n}(X \backslash Z, A \backslash Z),G)@>>>  0\\ & @A(i_{*})^\text{ext}A\cong A@Ai^{*}AA@A(i_{*})^{*}A\cong A\\  0 @>>>\text{Ext}(H_{n-1}(X , A),G)@>>> H^n(X , A;G)@>>> \text{Hom}(H_{n}(X , A ),G)@>>>  0\end{CD}$$and by 5-Lemma we have the statement.
> 3. Let $S^{A,B}_{n}(X)\subseteq S_{n}(X)$ be the group of chains that are linear combinations of chains in $S_{n}(A)$ and $S_{n}(B)$. Then, $S_{n}^{A,B}(X)$ is free abelian and: $$0\to S_{n}(A\cap B)\to S_{n}(A)\oplus S_{n}(B)\to S_{n}^{A,B}(X) \to 0$$from [[Singular Homology|Mayer-Vietoris]] splits. Hence, we can take the dual and we get: $$0\to S^n_{A,B}(X;G)\overset{ \Psi }{ \to } S^n(A;G)\oplus S^n(B;G)\overset{ \Phi }{ \to } S^n(A\cap B;G)\to 0$$where: $\Psi(h)=(h|_{S_{n}(A)},h|_{S_{n}(B)})$ and $\Phi(f,g)=f|_{S_{n}(A\cap B)}-g|_{S_{n}(A\cap B)}$. Now, therefore, we get the LES: $$\dots \to H^n_{A,B}(X;G)\to H^n(A;G)\oplus H^n(B;G)\to H^n(A\cap B;G)\to H^{n+1}_{A,B}(X;G)\to \cdots$$However, as $i:S^{A,B}_{n}(X)\to S_{n}(X)$ is a quasi isomorphism from [[Singular Homology|Theorem 4]], we have by [[Cochain Complex|Proposition 5]] that $i^{*}:S^n(X)\to S^n_{A,B}(X)$ induces an isomorphism in cohomology. This proves the statement.

^c2872e

---
> [!lemma] Proposition 5 (Cohomological Cross Product)
> Let $R$ be a [[ring|commutative ring]] and $X,Y$ topological spaces.
> 1. there exists a cochain map $$\times:\mathcal{S}^{*}(X;R)\otimes_{\mathbb{Z}}\mathcal{S}^{*}(Y;R)\to \mathcal{S}^{*}(X\times Y;R)$$ that is natural via maps $X\to X'$ and $Y\to Y'$.
> 2. $\times$ induces a map $\times:S^{p}(X;R)\otimes_{R}S^{q}(Y;R)\to S^{p+q}(X\times Y;R)$.
> 3. $\times$ induces a map in cohomology: $\times ^{*}:H^p(X;R)\otimes_{R}H^q(Y;R)\to H^{p+q}(X\times Y;R)$ which is independent of the choice of $\Theta$.

^fe2e9a


> [!proof]-
> We have that:
> 1. Let $\varphi\in S^p(X;R)$ and $\psi\in S^q(X;R)$ s.t. $p+q=n$. Let $\Theta:\mathcal{S}_{*}(X\times Y)\to \mathcal{S}_{*}(X)\otimes_{\mathbb{Z}} \mathcal{S}_{*}(Y)$ be a choice of a map from [[Singular Homology|Eilenberg-Zilberg]]. As $\varphi \otimes \psi:S^p(X)\otimes_{\mathbb{Z}}S^q(Y)\to R\otimes_{\mathbb{Z}}R$, by extending with $R\otimes_{\mathbb{Z}}R\to R,(x\otimes y)\mapsto xy$, we have a map: $$\varphi \otimes  \psi:S^p(X)\otimes_{\mathbb{Z}}S^q(X) \to R$$Extending this to a homomorphism: $$\varphi \otimes  \psi:(\mathcal{S}^{*}(X)\otimes _{\mathbb{Z}} \mathcal{S}^{*}(Y))_{n}\to R$$by filling the rest with $0$, we can define $\varphi \times \psi:=(\varphi \otimes \psi)\circ\Theta\in S^n(X\times Y;R)$. Further, 
> 	1. **For $f:X\to X'$ and $g:Y\to Y'$, the following diagram commutes:**$$\begin{CD}S^p(X';R)\otimes  S^q(Y';R) @>\times>> S^{p+q}(X'\times Y';R)\\ @Vf^c \otimes  g^cVV&@VV(f\times g)^cV\\S^p(X;R)\otimes  S^q(Y;R) @>>\times> S^{p+q}(X\times Y;R)\end{CD}$$
> 		
> 		Let $\varphi\in S^p(X';R)$ and $\psi\in S^q(Y';R)$. Then, for $\mu\in S_{p+q}(X\times Y)$, $$\begin{aligned}(f\times g)^c(\varphi \times \psi)&=(\varphi \times \psi)\circ (f\times g)_{c}=(\varphi \otimes  \psi)\circ  \Theta\circ (f\times g)_{c}\\&=(\varphi \otimes  \psi)\circ (f_{c}\otimes  g_{c})\circ  \Theta\\&=((\varphi \circ  f_{c})\otimes  (\psi \circ g_{c}))\circ \Theta\\&=(\varphi \circ  f_{c})\times(\psi \circ  g_{c})\\&=\times (f^c(\varphi)\otimes g^c(\psi))\end{aligned}$$
> 	2. **$\times$ is a cochain map**: 
> 	   For $\varphi\in S^p(X;R)$ and $\psi\in S^q(Y;R)$: $$\begin{aligned}\delta_{X\times Y}(\varphi \times \psi)&=(-1)^{p+q+1}(\varphi \times \psi)\circ \partial_{X\times Y}\\&=(-1)^{p+q+1}(\varphi \otimes  \psi)\circ  \Theta\circ \partial_{X\times Y}\\&=(-1)^{p+q+1}(\varphi \otimes  \psi)\circ  (\partial_{X}\otimes  \text{id}+\text{id}\otimes  \partial_{Y})\circ  \Theta\\&=(-1)^{p+q+1}((-1)^{q}(\varphi \circ \partial_{X})\otimes  \psi+\varphi \otimes \psi \circ \partial_{Y})\circ  \Theta\\&=((-1)^{p+1}(\varphi \circ \partial_{X})\otimes  \psi+(-1)^{p+q+1}\varphi \otimes \psi \circ \partial_{Y})\circ  \Theta\\&=\delta_{X}\varphi\times  \psi+(-1)^{p}\varphi \times \delta_{Y}\psi\\&=\times \circ (\delta_{X}\otimes  \text{id}+\text{id}\otimes  \delta_{Y})(\varphi \otimes  \psi)\end{aligned}$$
> 2. Notice that $\times:S^p(X;R)\times S^q(Y;R)\to S^{p+q}(X\times Y;R),(\varphi,\psi)\mapsto \varphi \times \psi$ is bilinear in $R$. This shows the statement.
> 3. We have that: $$\times:H^p(\mathcal{S}^{*}(X;R))\otimes H^q(\mathcal{S}^{*}(Y;R))\overset{ h }{ \to } H^{p+q}(\mathcal{S}^{*}(X;R)\otimes_{R}  \mathcal{S}^{*}(Y;R))\overset{ \times ^{*} }{ \to } H^{p+q}(\mathcal{S}^{*}(X\times Y;R))$$where $h([\varphi],[\psi])=[\varphi \otimes \psi]$. The independence follows from the fact that $\Theta$ is unique up to chain homotopy, hence $\times ^{*}$ is unique in cohomology.
> 	   

^f4e05c

- **Remark**: For $c\in S_{n}(X\times Y)$, $\varphi\in S^p(X;R)$ and $\psi\in S^q(Y;R)$, we have for $\Theta c=:\sum_{r+s=n}^{}\sum_{i,j}^{}a_{i}^r\otimes b_{j}^s$, $$\braket{ \varphi \times \psi , c } =\left\langle  \varphi \otimes  \psi , \sum_{i,j} a_{i}^p\otimes  b^q_{j}\right\rangle=\sum_{i,j}^{}(-1)^{pq}\varphi(a_{i}^p)\cdot  \psi(b^q_{j})  $$ ^083b5c
---

##### Examples
> [!h] Example 1
> Let $(X,A)$ be a pair of spaces and $i:A\to X$ the inclusion. 
> 1. $i^c:S^{*}(X)\to S^{*}(A),\alpha\mapsto \alpha|_{S_{*}(A)}$.

^bdcafc

---
