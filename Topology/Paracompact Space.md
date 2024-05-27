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
> [!h] Example 2
> Any second countable [[locally compact Hausdorff space]] is paracompact.

> [!proof]+
> Let $X$ be such a space. We have that:
> 1. **Claim 1: there exists an open cover $\{ G_{i} \}_{i\geq 1}$ of relatively compact sets s.t. $\overline{G_{i}}\subseteq G_{i+1}$**
>    Let $\{ U_{i} \}_{i\geq 1}$ be the countable basis of $X$. Modulo taking a sub-collection, we can assume that $U_{i}$ is relatively compact. More specifically, for any $V\subseteq X$ open, there exists $U_{i}\subseteq V$ in the basis. As $X$ is locally compact Hausdorff, there exists $U_{j}$ in the basis s.t. $$

^8754e4

---
