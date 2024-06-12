#Definition #Topology 

> [!definition]
> Let $X$ be a set. A ***uniform structure*** on $X$ is a collection $\mathcal{U}$ of subsets of $X\times X$ s.t. 
> 1. $A\in \mathcal{U}$ and $A\subseteq B$, then $B\in \mathcal{U}$.
> 2. $A_{1},A_{2}\in \mathcal{U}$, then $A_{1}\cap A_{2}\in \mathcal{U}$.
> 3. $\Delta:=\{ (x,x): x\in X \}\subseteq A$ for all $A\in \mathcal{U}$.
> 4. if $A\in \mathcal{U}$, then $A^{-1}:=\{ (y,x):(x,y)\in A \}\in \mathcal{U}$.
> 5. if $A\in \mathcal{U}$, then there exists $B\in \mathcal{U}$ s.t. $B^{2}:=\{ (x,y): \exists z,(x,z),(z,y)\in B \}\subseteq A$
- **Related definition**: A [[filter]] $\mathcal{F}$ on $X$ is a ***Cauchy filter***, if for all $A\in \mathcal{U}$, there exists $U\in \mathcal{F}$ s.t. $U\times U\subseteq A$.
---
##### Properties
> [!lemma] Proposition 1
> Let $\mathcal{U}$ be a uniform structure on $X$. 
> 1.  The topology of uniform spaces has $U\subseteq X$ open if and only if $U=\varnothing$ or for all $x\in U$ there exists $A\in \mathcal{U}$ s.t. $U\supseteq\{y\in X:(x,y)\in A \}$.

> [!proof]-
> We first have that $\varnothing$ is open. Further, $\Delta \subseteq X\times X\in \mathcal{U}$. Therefore, $X$ is open. 
> 
> Let $U_{1},U_{2}$ be non-empty open. Then, for $x\in U_{1}\cap U_{2}$ let $A_{1},A_{2}$ be the corresponding sets. Hence, $$U_{1}\cap U_{2}\supseteq\{ y\in X:(x,y)\in A_{1} \}\cap\{ y\in X:(x,y)\in A_{2} \}=\{ y\in X:(x,y)\in A_{1}\cap A_{2} \}$$where $A_{1}\cap A_{2}\in\mathcal{U}$. 
> 
> Similarly, let $(U_{i})_{i\in I}$ be a family of open sets. Then, for $x\in U:=\bigcup_{{i\in I}}^{}U_{i}$. If $x\in U_{i}$, then let $A_{i}$ be the corresponding set. Therefore, $$U\supseteq U_{i}\supseteq\{ y\in X:(x,y)\in A_{i} \}$$
> 
---
> [!lemma] Theorem 2
> For a uniform space $(X,\mathcal{U})$, 
> 1. there exists a continuous map $i:X\to \widehat{X}$ with $\widehat{X}$ Hausdorff and complete s.t. $i(X)$ is dense in $\widehat{X}$ and $i:X\to i(X)$ is a homeomorphism.
> 2. for any other $j:X\to \widehat{X}'$ with the above properties, there exists a homeomorphism $f:\widehat{X}\to \widehat{X}'$ s.t. $f\circ i = j$.
---
##### Examples
> [!h] Example 1 (Metric Space)
> For a [[metric space]] $(X,d)$, $$\mathcal{U}:=\{ A\subseteq X\times X: \exists\delta>0,d(x,y)<\delta\implies (x,y) \in A\}$$is a uniform structure. Let $(x_{n})_{n}\subseteq X$ and $\mathcal{F}$ be the [[Filter|elementary filter]]. Then, TFAE:
> 1. $(x_{n})_{n}$ is a [[Cauchy sequence]].
> 2. $\mathcal{F}$ is a Cauchy filter.

> [!proof]+
> We have that:
> 1. To show that it is a uniform structure:
> 	1. Holds with the same $\delta$.
> 	2. Holds with $\delta:=\min\{ \delta_{1},\delta_{2} \}$.
> 	3. For any $A\in \mathcal{U}$, we have that $d(x,x)=0<\delta$. Therefore, $(x,x)\in A$.
> 	4. The uniform structure is symmetric.
> 	5. For $A\in \mathcal{U}$ with $\delta>0$, let $B:=\{ (x,y)\in X\times X:d(x,y)<\delta /2 \}$. Then, $B\in \mathcal{U}$ and, for any $(x,y),(y,z)\in B$, $d(x,z)\leq d(x,y)+d(y,z)<\delta$ and $(x,z)\in A$.
> 2. To show the equivalence:
>    Let $(x_{n})_{n}$ be Cauchy. Let $A\in \mathcal{U}$ with $\delta>0$. Then, there exists $N$ s.t. $d(x_{N},x_{n})<\delta /2$ for all $n\geq N$. Hence, if we set $U:=B_{<\delta /2}(x_{N})$, $U\in \mathcal{F}$ and $U\times U\subseteq A$ as for $x,y\in U$: $$d(x,y)\leq d(x,x_{N})+d(x_{N},y)<\delta$$and $(x,y)\in A$.
>    
>    Conversely, if $\mathcal{F}$ is a Cauchy filter, for $\delta>0$, Let $A:=\{ (x,y)\in X\times X: d(x,y)<\delta / 2 \}\in \mathcal{U}$ and $U\in \mathcal{F}$ s.t. $U\times U\subseteq A$. 
---
> [!h] Example 2 (Topological Group)
> For a [[topological group]] $X$, $$\mathcal{U}:=\{ A\subseteq X\times X: \exists U \text{ neighborhood of }e\text{ s.t. }\{ (x,y)|xy^{-1}\in U \}\subseteq A\}$$is a uniform structure.

> [!proof]-
> We have:
> 1. For $A\in \mathcal{U}$ with neighborhood $U$ use $U$ for $B\supseteq A$.
> 2. Use the intersection.
> 3. For $A\in \mathcal{U}$ with neighborhood $U$, $xx ^{-1}=e\in U$ and $(x,x)\in A$.
> 4. Take $U^{-1}$.
> 5. For $A\in \mathcal{U}$ with neighborhood $U$, if $U$ is a neighborhood of $e$, by [[Topological Group|Proposition 2]], there exists an open symmetric neighborhood $V$ of $e$ s.t. $V^{2}\subseteq U$. Let $B:=\{ (x,y): xy^{-1}\in V \}$. Then, for $(x,y),(y,z)\in B$, $$xz^{-1}=xy^{-1}yz^{-1}\in V^{2}\subseteq U$$
---
> [!h] Example 3 (Compact Hausdorff Space)
> For a [[Compact Space|compact]] [[Hausdorff space]] $X$, $$\mathcal{U}:=\{ A\subseteq X\times X: \exists U\subseteq X\times X\text{ open s.t. }\Delta \subseteq U\subseteq A\}$$is a uniform structure.

> [!proof]-
> We have:
> 1. Obvious with the same $U$.
> 2. Take the intersection.
> 3. By definition.
> 4. Take $U^{-1}$.
> 5. Let $A\in \mathcal{U}$ with $U$. Then, for any $x\in X$, there exists $B$ open s.t. $(x,x)\in B\times B\subseteq U$. By the [[Normal Space|normality]] of $X$, there exists $A\ni x$ open s.t. $\overline{A}\subseteq B$. By compactness, there exists $A_{1},\dots,A_{n}$ s.t. $\mathcal{A}:=\{ A_{i} \}_{i}$ is a finite cover of $X$. Let $\mathcal{A}_{i}:=\{ X \backslash \overline{A_{i}},B_{i} \}$ be also a finite open cover of $X$. We now define: $$\mathcal{V}:=\left\{  V\cap \bigcap_{i}^{}V_{i}:V\in\mathcal{A},V_{i}\in \mathcal{A}_{i}  \right\}$$Lastly, define $W:=\bigcup_{S\in \mathcal{V}}^{}S\times S$. Then, $W$ is open and $\Delta \subseteq W$. Therefore, $W\in \mathcal{U}$. Finally, for $(x,y),(y,z)\in W$, then $x,y\in A_{i}$ for some $i$. Then, $y,z\in B_{i}$. Therefore, $$(x,z)\in B_{i}\times B_{i}\subseteq U$$  
---
