#Definition #Topology 

> [!definition]
> Let $X,Y$ be [[Topological Space|topological spaces]]. A map $f:X\to Y$ is ***continuous***, if for any open set $U\subseteq Y$, $f^{-1}(U)\subseteq X$ is open.
---
##### Properties
> [!lemma] Lemma 1
> For topological spaces $X,Y,Z$, $f:X\to Y,g:Y\to Z$ continuous maps and $A\subseteq X$, 
> 1. $g\circ f$ is continuous.
> 2. the inclusion $j:A\hookrightarrow X$ is continuous w.r.t. the [[Topological Space|subspace topology]].
> 3. the identity map $i:X\to X$ is continuous.
> 4. the restriction $f|_{A}:A\to Y$ is continuous.

> [!proof]-
> We have: 
> 1. Let $U\subseteq Z$ open. Then, $$(g\circ f)^{-1}(U)=f^{-1}(g^{-1}(U))$$As $g^{-1}(U)$ is open, $f^{-1}(g^{-1}(U))$ is open.
> 2. Let $U\subseteq X$ open. Then, $j^{-1}(U)=U\cap A$ which is open.
> 3. Take $A=X$ in 2.
> 4. $f|_{A}=f\circ j$ and by 1,2.
---
> [!lemma] Lemma 2
> For topological spaces $X,Y$ and a map $f:X\to Y$. The following are equivalent:
> 1. $f$ is continuous.
> 2. $f^{-1}(U)$ is open in $X$ for every $U\in \mathcal{B}_{Y}$ in the [[Basis of a Topology|basis]] of $Y$.

> [!proof]-
> => is clear from the definition. Conversely, if $f^{-1}(U)$ is open for all open sets in the basis, for $V\subseteq Y$ open, there exists $\{ U_{\lambda} \}$ s.t. $V=\bigcup_{\lambda\in\Lambda}U_{\lambda}$ and: $$f^{-1}(V)=f^{-1}\left(\bigcup_{\lambda\in\Lambda}U_{\lambda}  \right)=\bigcup_{\lambda\in \Lambda}^{}f^{-1}(U_{\lambda}) $$
which is open.
---