#Definition #Topology 

> [!definition]
> Let $X,Y$ be [[Topological Space|topological spaces]]. A map $f:X\to Y$ is ***continuous***, if for any open set $U\subseteq Y$, $f^{-1}(U)\subseteq X$ is open.
- **Related definition**: $f$ is ***continuous at $x$*** if for all neighborhoods $V\subseteq Y$ of $f(x)$, there exists a neighborhood $W\subseteq X$  of $x$ s.t. $f(W)\subseteq V$.
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
> 2. $f^{-1}(U)$ is open in $X$ for every $U\in \mathcal{G}_{Y}$ in the [[Base of Topology|subbase]] of $Y$.
> 3. $f^{-1}(U)$ is open in $X$ for every $U\in \mathcal{B}_{Y}$ in the [[Base of Topology|base]] of $Y$.
> 5. For all $x\in X$ and a neighborhood $V\subseteq Y$ of $f(x)$, there exists a neighborhood $W\subseteq X$  of $x$ s.t. $f(W)\subseteq V$.
> 6. For all $x\in X$ and a set $V$ in a [[Local Base of Topology|local base]] of $f(x)$, there exists a set $W$ in the local base of $x$ s.t. $f(W)\subseteq V$.

> [!proof]-
> We have: 
> - (1=>2): is clear from the definition. 
> - (2=>3): A basis is a subbasis.
> - (3=>1): If $f^{-1}(U)$ is open for all open sets in the basis, for $V\subseteq Y$ open, there exists $\{ U_{\lambda} \}$ s.t. $V=\bigcup_{\lambda\in\Lambda}U_{\lambda}$ and: $$f^{-1}(V)=f^{-1}\left(\bigcup_{\lambda\in\Lambda}U_{\lambda}  \right)=\bigcup_{\lambda\in \Lambda}^{}f^{-1}(U_{\lambda}) $$which is open.
> - (1=>4): Let $x\in X$ and $V\subseteq Y$ a neighborhood of $f(x)$. Then, there exists an open neighborhood $W\subseteq V$ with $f^{-1}(W)$ as an open neighborhood of $x$
> - (4=>1): Let $V\subseteq Y$ be open. Then, for every $x\in f^{-1}(V)$, there is an open neighborhood $W\subseteq X$ of $x$ s.t. $f(W)\subseteq V$, i.e. $W\subseteq f^{-1}(V)$.
> - (4=>5) clear.
> - (5=>4) Let $V\subseteq Y$ be a neighborhood of $f(x)$. Then, there exists $V_{1}\subseteq V$ in the fundamental system and $W\subseteq X$ s.t. $f(W)\subseteq V_{1}\subseteq V$.

---
> [!lemma] Lemma 3
> Let $X,Y$ be topological spaces and $f:X\to Y$ a continuous function. Then, for $A\subseteq Y$: $$\overline{f^{-1}(A)}\subseteq f^{-1}(\overline{A})$$

> [!proof]-
> Let $A\subseteq C$ where $C$ is closed. Then, $f^{-1}(A)\subseteq f^{-1}(C)$ and $\overline{f^{-1}(A)}\subseteq f^{-1}(C)$. Therefore, $$\overline{f^{-1}(A)}\subseteq \bigcap_{A\subseteq C,C\text{ closed}}^{}f^{-1}(C)=f^{-1}\left( \bigcap_{A\subseteq C,C\text{ closed}}^{}C \right) =f^{-1}(\overline{A})$$
---
##### Compact Hausdorff Spaces
> [!lemma] Theorem (Stone-Weierstrass)
> Let $X$ be a [[Compact Space|compact]] [[Hausdorff space]]. Let $\mathcal{F}\subseteq C(X,\mathbb{R})$ s.t. 
> 1. for $f,g\in \mathcal{F}$, $f+g,fg\in \mathcal{F}$
> 2. constants are in $\mathcal{F}$
> 3. for $x\neq y$, there exists $f\in \mathcal{F}$ with $f(x)\neq f(y)$
>    
>  Then, $\mathcal{F}\subseteq C(X,\mathbb{R})$ is dense w.r.t. the [[Topology of Pointwise and Uniform Convergence|topology of uniform convergence]]. 