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

> [!proof]-
> Let $X$ be such a space. We have that:
> 1. **Claim 1: there exists an open cover $\{ G_{i} \}_{i\geq 1}$ of relatively compact sets s.t. $\overline{G_{i}}\subseteq G_{i+1}$**
>    Let $\{ U_{i} \}_{i\geq 1}$ be the countable basis of $X$. Modulo taking a sub-collection, we can assume that $U_{i}$ is relatively compact. More specifically, for any $V\subseteq X$ open, there exists $W\subseteq V$ open, relatively compact with $W\subseteq \overline{W}\subseteq V$, as $X$ is locally compact Hausdorff (by [[Locally Compact Hausdorff Space|Lemma 1]]). Then,  there exists $U_{i}$ in the basis s.t. $U_{i}\subseteq W$ and $\overline{U_{i}}\subseteq \overline{W}$ is compact as a closed subset. 
>    
>    Now, define $G_{1}:=U_{1}$ and $j_{1}:=1$. Let $j_{k+1}$ be the smallest positive integer greater than $j_{k}$ s.t. $$\overline{G_{k}}\subseteq \bigcup_{i=1}^{j_{k+1}}U_{i}$$and define $G_{k+1}:=\bigcup_{i=1}^{j_{k+1}}U_{i}$. 
> 2. **Proving that $X$ is paracompact**:
>    Let $\{ U_{\alpha} \}_{\alpha}$ is an open cover. Consider the compact set $\overline{G}_{k} \backslash G_{k-1}$ contained in ${G_{k+1}} \backslash \overline{G_{k-2}}$. Then, 
>    1. Choose a finite subcover of $\mathcal{B}_{k}:=\{ U_{\alpha}\cap {G_{k+1}} \backslash \overline{G_{k-2}}\}$ of $\overline{G}_{k} \backslash G_{k-1}$, which exists from compactness.
>    2. Choose a finite subcover of $\mathcal{B}_{2}:=\{ U_{\alpha}\cap G_{3} \}$ of $\overline{G_{2}}$, which exists from compactness. 
>    
>    Therefore, $\mathcal{B}:=\mathcal{B}_{2}\cup \bigcup_{k\geq 3}\mathcal{B}_{k}$ is a locally finite open cover refinement of $\{ U_{\alpha} \}$. 

^8754e4

---
