#Definition #Topology #FunctionalAnalysis 

> [!definition]
> Let $X$ be a [[topological space]]. The ***one-point compactification*** of $X$ is the topological space $\alpha X$ where:
> 1. $\alpha X:=X\cup \{ \infty \}$ and
> 2. For any $U$ open in $X$, $U$ is open in $\alpha X$.
> 3. For any $K$ closed and compact in $X$, $(X \backslash K)\cup \{ \infty \}$ is open in $\alpha X$.
- **Remark**: if $X$ is Hausdorff, then condition 3 only requires compactness. 
---
##### Properties
> [!lemma] Proposition 1
> The topology on $\alpha X$ is well-defined, i.e. it is closed under arbitrary unions and finite intersections.

> [!proof]-
> It is sufficient to see that:
> 1. the union and finite intersection of $(X \backslash K)\cup \{ \infty \}$ are closed among themselves.
> 2. for $U,K\subseteq X$ where $U$ open and $K$ closed and compact in $X$, the union and intersection of $U$ and $(X \backslash K)\cup \{ \infty \}$ is again one of the two kinds. 
> 
> We have for finite $I$,
> 1. $$\bigcap_{i\in I}^{}(X \backslash K_{i}) \cup \{ \infty \}=\left( X \backslash \bigcup_{i\in I}^{}K_{i} \right) \cup \{ \infty \},\quad \bigcup_{\lambda\in \Lambda}^{}(X \backslash K_{\lambda})\cup \{ \infty \}= \left( X \backslash \bigcap_{\lambda\in \Lambda}^{}K_{\lambda} \right) \cup \{ \infty \} $$
> 2. $$U\cap((X \backslash K)\cup \{ \infty \})=(X \backslash C)\cap(X \backslash K)=X \backslash (C \cup K)$$
> 3. $$U\cup((X \backslash K)\cup \{ \infty \})=(X \backslash C)\cup(X\backslash K)\cup \{ \infty \}=(X \backslash (C\cap K))\cup \{ \infty \}$$
---
> [!lemma] Proposition 2
> $\alpha X$ is compact.

> [!proof]+
> 