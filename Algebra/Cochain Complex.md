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

^846fe1

> [!proof]-
> We have:
> 1. Let $f\in D^i$. Then, $$\delta \circ  \delta(f)=\delta(f \circ  \partial) = f \circ  \underbrace{ \partial \circ  \partial }_{ =0 } = 0 $$Hence, it is a cochain complex.
> 2. Let $f\in Z^i(\mathcal{D})$. This is equivalent to $\delta(f) = f \circ \partial= f|_{\text{im }\partial}=f|_{B_{i}(\mathcal{C})}= 0$. 
> 3. Let $f\in B^i(\mathcal{D})$. Then, there exists $g\in D^{i-1}$ with $\delta(g)=g \circ \partial =f$. Hence, $$f|_{Z^i(\mathcal{C})}=g \circ  \partial|_{Z^i(\mathcal{C})}=0$$

^fa5a91

---
