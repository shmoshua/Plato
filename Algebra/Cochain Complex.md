#Definition #AlgebraicTopology 

> [!definition]
> Let $\{ C^i \}_{i\in \mathbb{Z}}$ be a graded [[abelian group]].
> 1. A ***cochain complex*** is a pair of $\{ C^i \}_{i\in \mathbb{Z}}$ and $\{ \delta:C^i\to C^{i+1} \}_{i\in \mathbb{Z}}$ s.t. $\delta^{2}=0$.

^7727cb

- **Remark**: Most properties are similar to a [[chain complex]]. ^12fba2
- **Related definition**: For a cochain complex $\mathcal{C}:=(\{ C^i\}_{i\in \mathbb{Z}},\delta)$, we have that: ^915852
	1. $Z^i(\mathcal{C}):=\text{ker}(\delta)$ for $\delta:C^i\to C^{i+1}$ are the ***cocycles***.
	2. $B^i(\mathcal{C}):=\text{im}(\delta)$ for $\delta:C^{i-1}\to C^i$ are the ***coboundaries***.
	3. $H^i(\mathcal{C}):=Z^i(\mathcal{C}) / B^i(\mathcal{C})$ is the ***cohomology*** of $\mathcal{C}$ in degree $i$, which is well-defined as $\delta^{2}=0$. 
- **Related definition**: For two cochain complexes $\mathcal{C}:=(\{ C^i \}_{i},\delta_{C})$ and $\mathcal{D}:=(\{ D^i \}_{i},\delta_{D})$, a ***cochain map*** $f:\mathcal{C}\to \mathcal{D}$ is a collection of group homomorphisms $f:C^i\to D^i$ for all $i\in \mathbb{Z}$ s.t. $f \circ \delta_{C}=\delta_{D} \circ f$ for all $i\in\mathbb{Z}$. 
 ^1d5d0b

- **Related definition**: Cochain complexes $\mathcal{A},\mathcal{B},\mathcal{C}$ form a ***short exact sequence (SES)*** with cochain maps $f:\mathcal{A}\to \mathcal{B}$ and $g:\mathcal{B}\to \mathcal{C}$, if $0\to A_{k}\xrightarrow{f}B_{k}\xrightarrow{g} C_{k}\to 0$ is a [[Exact Sequence|SES]] for all $k\in \mathbb{Z}$. ^e374e8
---

##### Properties
> [!lemma] Proposition 1 (Cochain maps induce Homomorphisms in Cohomology)
> Let $f:\mathcal{C}\to \mathcal{D}$ be a cochain map. Then, for all $i\in \mathbb{Z}$:
> 1. $f(Z^i(\mathcal{C}))\subseteq Z^i(\mathcal{D})$
> 2. $f(B^i(\mathcal{C}))\subseteq B^i(\mathcal{D})$
> 3. $f^{*}:H^{*}(\mathcal{C})\to H^{*}(\mathcal{D}),[c]\mapsto[f(c)]$ is a group homomorphism.

^347ad5

> [!proof]-
> We have that:
> 1. Let $c\in Z^i(\mathcal{C})$. Then, $\delta_{C} c=0$ and we have that $\delta_{D}(f(c))=f(\delta_{C}c)=f(0)=0$.
> 2. Let $c\in B^i(\mathcal{C})$. Then, there exists $c'\in C_{i-1}$ s.t. $\delta_{C}(c')=c$ and  $\delta_{D}(f(c'))=f(\delta_{C}(c'))=f(c)$.
> 3. We have that $f^{*}$ is well-defined as if $c-c'\in B^i(\mathcal{C})$, then $f(c)-f(c')\in B_{i}(\mathcal{D})$. Further, $f^{*}$ is a homomorphism as $f$ is. 

^26627c

---
> [!lemma] Proposition 2 (Functoriality of Cohomology)
> Let $f:\mathcal{A}\to \mathcal{B}$ and $g:\mathcal{B}\to \mathcal{C}$ be cochain maps. Then, 
> 1. $g \circ f$ is a cochain map.
> 2. $(g\circ f)^{*}=g^{*}\circ f^{*}$
> 3. $\text{id}:\mathcal{A}\to \mathcal{A}$ is a cochain map with $\text{id}^{*}=\text{id}_{H^{*}(\mathcal{A})}$.

^8cac80

> [!proof]-
> We have that:
> 1. $g\circ f$ is a homomorphism and we have that: $\delta_{C} \circ  g \circ  f=g \circ  \delta_{B} \circ  f=g \circ  f  \circ  \delta_{A}$.
> 2. For a cocycle $c\in Z^i(\mathcal{A})$, $$(g\circ f)^{*}([c])=[g(f(c))]=g^{*}([f(c)])=g^{*}(f^{*}([c]))$$
> 3. Obvious. 

^8e49fb

---
> [!lemma] Theorem 3 (Long Exact Sequence in Cohomology)
> Let $0\to \mathcal{A}\xrightarrow{f}\mathcal{B}\xrightarrow{g} \mathcal{C}\to 0$ be a SES of cochain complexes. Then, 
> 1. there exists $\delta ^{*}:H^i(\mathcal{C})\to H^{i+1}(\mathcal{A})$ for all $i\in \mathbb{Z}$ s.t.:
> $$\cdots\to H^{i-1}(\mathcal{C})\xrightarrow{\delta ^{*}}H^i(\mathcal{A})\xrightarrow{f^{*}}H^i(\mathcal{B})\xrightarrow{g^{*}}H^i(\mathcal{C})\xrightarrow{\delta ^{*}}H^{i+1}(\mathcal{A})\to\cdots$$is an [[exact sequence]].

^7f660e

> [!proof]-
> Analogous to [[Chain Complex|LES in homology]].

^cbaa04

---
> [!lemma] Theorem 4 (Homology and Cohomology)
> Let $(C,\partial)$ be a chain complex of free abelian groups and let $(\text{Hom}(C,G), \delta)$ be the homomorphism cochain complex. Then, 
> 1. for all $n\in \mathbb{Z}$, there exists a canonical map $h:H^n(C;G)\to \text{Hom}(H_{n}(C),G)$ that admits a right inverse. In particular, $h$ is surjective. 
> 2. $0\to \text{ker }h\to H^n(C;G)\xrightarrow{h} \text{Hom}(H_{n}(C),G)\to 0$ is split.

^232eea

> [!proof]-
> We have:
>  1. Let $\alpha\in H^n(C,G)$. Then, we have that $\alpha$ is represented by some $\varphi: C_{n}\to G$ s.t. $\delta(\varphi)=\varphi \circ \partial=0$, i.e. $B_{n}(C)\subseteq \text{ker }\varphi$.  Hence, $\varphi$ descends to $\overline{\varphi}:H_{n}(C)= Z_{n}(C) / B_{n}(C)\to G$. We define: $$h:H^n(C;G)\to \text{Hom}(H_{n}(C),G),\quad [\varphi]\mapsto \overline{\varphi}$$
> 	1. **Claim 1**: $h$ is well-defined. 
>    Let $[\varphi]=[\varphi']$. Then, $\varphi-\varphi'=\delta(\psi)=\psi \circ \partial$ for some $\psi: C_{n-1}\to G$. Hence, $(\varphi-\varphi')|_{Z_{n}}\equiv 0$. This shows that $\overline{\varphi}=\overline{\varphi'}$. 
> 	2. **Claim 2**: $h$ is linear.
>    $[\varphi]+[\psi]=[\varphi+\psi]$ where $\varphi+\psi$ are cocycles. Then, $\overline{\varphi+\psi}=\overline{\varphi}+\overline{\psi}$. 
>  
> 	 Now, we will construct the right inverse $s:\text{Hom}(H_{n}(C),G)\to H^n(C;G)$. Consider the SES: $$0\to Z_{n}(C)\xrightarrow{i}C_{n}\xrightarrow{\partial} B_{n-1}(C)\to 0$$As $B_{n-1}(C)\subseteq C_{n-1}$ and $C_{n-1}$ is free abelian, so is $B_{n-1}(C)$ and by [[Split Exact Sequence|Proposition 2]] the SES splits. 
>  
> 	 Hence, by [[Split Exact Sequence|Proposition 1]], there exists $p:C_{n}\to Z_{n}(C)$ with $p \circ i=\text{id}_{Z_{n}(C)}$. Now, for any $\varphi_{0}\in \text{Hom}(Z_{n}(C),G)$, we can extend this to $\varphi: = \varphi_{0} \circ p\in \text{Hom}(C_{n},G)$ as $\varphi|_{Z_{n}(C)}=\varphi_{0}$. 
>  
> 	 Let $\sigma\in \text{Hom}(H_{n}(C),G)$. Then, by composing with $Z_{n}(C)\to Z _n (C) / B_{n}(C)=H_{n}(C)$ we have: $$\sigma':Z_{n}(C)\to G,\quad \widehat{\sigma}:=p^{*}(\sigma')=\sigma' \circ  p\in \text{Hom}(C_{n},G)$$Further, we claim that $\delta(\widehat{\sigma})=0$. Indeed, $$\delta(\widehat{\sigma})=\widehat{\sigma} \circ  \partial=\sigma' \circ \underbrace{ p \circ  \partial }_{ =\partial } =\sigma' \circ  \partial=0$$
>  
> 	 Hence, we define the right inverse as: $$s:\text{Hom}(H_{n}(C),G)\to H^n(C;G),\quad \sigma\mapsto [\widehat{\sigma}]$$
> 	 3. **Claim 3**: $s$ is linear.
> 	$$[\widehat{\sigma}]+[\widehat{\rho}]=[\widehat{\sigma}+\widehat{\rho}]=[p^{*}(\sigma' + \rho')]=[p^{*}(\sigma + \rho)']=[\widehat{\sigma+\rho}]$$
> 	4. **Claim 4**: $h \circ s=\text{id}$. 
>    For any $\sigma\in \text{Hom}(H_{n}(C),G)$, we have: $h (s(\sigma))=h[\widehat{\sigma}]=\overline{\widehat{\sigma}}=\sigma$.
> 2. Follows from $h$ being surjective as $h \circ s = \text{id}$ and [[Split Exact Sequence|Proposition 1.3]]. 

^7c6d20

- **Example**: Let $\mathcal{C}$ be the cellular chain complex of $\mathbb{R}\mathbb{P}^3$. Then, it is represented as: $$\mathcal{C}:=(0 \to \mathbb{Z} \overset{ 0 }{ \to } \mathbb{Z} \overset{ \times 2 }{ \to  }\mathbb{Z} \overset{  0 }{ \to } \mathbb{Z}\to 0)$$with homology $H_{n}(\mathbb{R}\mathbb{P}^3)\cong(\mathbb{Z},\mathbb{Z} / 2\mathbb{Z},0,  \mathbb{Z})$
  

---
> [!lemma] Proposition 5 (Quasi-Isomorphism induces Isomorphism in Cohomology)
> Let $\mathcal{C,\mathcal{D}}$ be chain complexes of free abelian groups. 
> 1. For a [[Chain Complex|quasi-isomorphism]] $f:\mathcal{C}\to \mathcal{D}$, $f^{*}:\text{Hom}(\mathcal{D},G)\to \text{Hom}(\mathcal{C},G)$ induces an isomorphism in cohomology.

^d85926

> [!proof]-
> From the [[Ext|UCT]], we have that: $$\begin{CD} 0 @>>> \text{Ext}(H_{n-1}(\mathcal{C}),G) @>>> H^n(\mathcal{C};G)@>>> \text{Hom}(H_{n}(\mathcal{C}),G) @>>> 0\\ &@Af_{*}^{\text{ext}}AA@A(f^{*})^{*}AA@A(f_{*})^{*}AA\\0 @>>> \text{Ext}(H_{n-1}(\mathcal{D}),G) @>>> H^n(\mathcal{D};G)@>>> \text{Hom}(H_{n}(\mathcal{D}),G) @>>> 0\end{CD}$$However, $f_{*}^{\text{ext}}$ is an isomorphism as $f_{*}$ induces an isomorphism, and similarly so is $(f_{*})^{*}$. Therefore, by 5-lemma $(f^{*})^{*}$ is an isomorphism.

^8d28b4

---


##### Examples
> [!h] Example 1 
> Let $(\mathcal{C},\partial)$ be a [[chain complex]].
> 1. $(\mathcal{D},d)$ is a cochain complex where $D^i:=C_{-i}$ and $d:D^i\to D^{i+1}$ is $\partial:C_{-i}\to C_{-i-1}$. 

^806b31

> [!proof]-
> We have that: 
> 1. Obvious.

^66eb56


---
> [!h] Example 2 (Homomorphism Cochain)
>  Let $(\mathcal{C},\partial)$ be a chain complex and $G$ an abelian group $G$. Let:
>   $$D^i:= \text{Hom}(C_{i},G),\quad \delta:=\partial ^{*}:D^i\to D^{i+1},f\mapsto f \circ  \partial$$
>   1. $\mathcal{D}:=(D,\delta)$ is a cochain complex.
>   2. $f\in Z^i(\mathcal{D})$ if and only if $f|_{B_{i}(\mathcal{C})}\equiv 0$.
>   3. if $f\in B^i(\mathcal{D})$ then $f|_{Z^i(\mathcal{C})}\equiv 0$.
>   4. for a chain map $\varphi:\mathcal{C}\to \mathcal{C'}$, the map: $$\varphi ^{*}:\text{Hom}(C_{i}',G)\to \text{Hom}(C_{i},G),\quad f\mapsto f\circ  \varphi$$is a cochain map.

^846fe1

> [!proof]-
> We have:
> 1. Let $f\in D^i$. Then, $$\delta \circ  \delta(f)=\delta(f \circ  \partial) = f \circ  \underbrace{ \partial \circ  \partial }_{ =0 } = 0 $$Hence, it is a cochain complex.
> 2. Let $f\in Z^i(\mathcal{D})$. This is equivalent to $\delta(f) = f \circ \partial= f|_{\text{im }\partial}=f|_{B_{i}(\mathcal{C})}= 0$. 
> 3. Let $f\in B^i(\mathcal{D})$. Then, there exists $g\in D^{i-1}$ with $\delta(g)=g \circ \partial =f$. Hence, $$f|_{Z^i(\mathcal{C})}=g \circ  \partial|_{Z^i(\mathcal{C})}=0$$
> 4. For $f\in \text{Hom}(C'_{i},G)$: $$\varphi ^{*} ( \delta_{C'}(f))=f \circ  \partial_{C'} \circ  \varphi=f \circ  \varphi \circ  \partial_{C}=\delta_{C}(f \circ  \varphi)=\delta_{C}(\varphi ^{*}(f))$$


^fa5a91

---
