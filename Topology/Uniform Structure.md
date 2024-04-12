#Definition #Topology 

> [!definition]
> Let $X$ be a set. A ***uniform structure*** on $X$ is a collection $\mathcal{U}$ of subsets of $X\times X$ s.t. 
> 1. $A\in \mathcal{U}$ and $A\subseteq B$, then $B\in \mathcal{U}$.
> 2. $A_{1},A_{2}\in \mathcal{U}$, then $A_{1}\cap A_{2}\in \mathcal{U}$.
> 3. $\Delta:=\{ (x,x): x\in X \}\subseteq A$ for all $A\in \mathcal{U}$.
> 4. if $A\in \mathcal{U}$, then $A^{-1}:=\{ (y,x):(x,y)\in A \}\in \mathcal{U}$.
> 5. if $A\in \mathcal{U}$, then there exists $B\in \mathcal{U}$ s.t. $\{ (x,y): \exists z,(x,z),(z,y)\in B \}\subseteq A$
- **Related definition**: A [[filter]] $\mathcal{F}$ on $X$ is a ***Cauchy filter***, if for all $A\in \mathcal{U}$, there exists $U\subseteq X$ s.t. $U\times U\subseteq A$ and $U\in \mathcal{F}$.
---
##### Properties
> [!lemma] Proposition 1
> Let $\mathcal{U}$ be a uniform structure on $X$. Consider the following topology, where $U\subseteq X$ is open if and only if $U$ is empty or for any $x\in U$ there exists $A\in \mathcal{U}$ s.t. $U=\{y\in X:(x,y)\in A \}$.

> [!proof]-
> We first have that $\varnothing$ is open. Further, $\Delta \subseteq X\times X\in \mathcal{U}$. Therefore, $X$ is open. Let $U_{1},U_{2}$ be open with $A_{1},A_{2}\in \mathcal{U}$ as the corresponding sets. Then, for $x\in U_{1}\cap U_{2}$, $$U_{1}\cap U_{2}=\{ y\in X:(x,y)\in A_{1} \}\cap\{ y\in X:(x,y)\in A_{2} \}=\{ y\in X:(x,y)\in A_{1}\cap A_{2} \}$$where $A_{1}\cap A_{2}\in\mathcal{U}$. Similarly, let $(U_{i})_{i\in I}$ be a family of open sets with $(A_{i})_{i\in I}\subseteq \mathcal{U}$. Then, for $x\in U:=\bigcup_{{i\in I}}^{}U_{i}$. Then, we let $A:=U\times U$ where 
---
> [!lemma] Theorem 2
> For a uniform space $(X,\mathcal{U})$, 
> 1. there exists a continuous map $i:X\to \widehat{X}$ with $\widehat{X}$ Hausdorff and complete s.t. $i(X)$ is dense in $\widehat{X}$ and $i:X\to i(X)$ is a homeomorphism.
> 2. for any other $j:X\to \widehat{X}'$ with the above properties, there exists a homeomorphism $f:\widehat{X}\to \widehat{X}'$ s.t. $f\circ i = j$.
---
##### Examples
> [!h] Example 1 (Metric Space)
> For a [[metric space]] $(X,d)$, $$\mathcal{U}:=\{ A\subseteq X\times X: \exists\delta>0,d(x,y)<\delta\implies (x,y) \in A\}$$is a uniform structure.
---
> [!h] Example 2 (Topological Group)
> For a [[topological group]] $X$, $$\mathcal{U}:=\{ A\subseteq X\times X: \exists U \text{ neighborhood of }1\text{ s.t. }\{ (x,y)|xy^{-1}\in U \}\subseteq A\}$$is a uniform structure.
---
> [!h] Example 2 (Compact Hausdorff Space)
> For a [[Compact sets|compact]] [[Hausdorff space]] $X$, $$\mathcal{U}:=\{ A\subseteq X\times X: \exists U\subseteq X\times X\text{ open s.t. }U\subseteq A\}$$is a uniform structure.
---
