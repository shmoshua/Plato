#Definition #Topology 

> [!definition]
> A [[topological space]] $X$ is ***paracompact*** if every open cover $\{ U_{\alpha} \}_{\alpha}$ has a refinement by a locally finite open cover $\{ V_{\beta} \}_{\beta}$, i.e.
> 1. for every $V_{\beta}$ there exists $\alpha$ s.t. $V_{\beta}\subseteq U_{\alpha}$.
> 2. for every $x\in X$, there exists a neighborhood $U\ni x$ s.t. $U\cap V_{\beta}=\varnothing$ for all but finitely many.
---
##### Properties
---
##### Examples
> [!h] Example 1
> Every [[compact space]] is paracompact.

> [!proof]-
> For an open cover $\{ U_{\alpha} \}\alpha$ and a compact space $X$, let $\{ U_{i} \}_{i=1}^n$ be the finite subcover. Then, the subcover is a locally finite refinement.
---
