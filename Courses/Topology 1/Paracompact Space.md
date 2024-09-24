#Definition #Topology 

> [!definition]
> A [[Topological Space]] $X$ is ***paracompact*** if every open cover $\{ U_{\alpha} \}_{\alpha}$ has a refinement by a locally finite open cover $\{ V_{\beta} \}_{\beta}$, i.e.
> 1. for every $V_{\beta}$ there exists $\alpha$ s.t. $V_{\beta}\subseteq U_{\alpha}$.
> 2. for every $x\in X$, there exists a neighborhood $U\ni x$ s.t. $U\cap V_{\beta}=\varnothing$ for all but finitely many.
---
##### Properties
> [!lemma] Theorem 1 (Dieudonné)
> Let $X$ be a paracompact Hausdorff space. Then,
> 1. $X$ is regular. 
> 2. $X$ is normal.

> [!proof]-
> We have:
> 1. Let $x\in X$ and $A\subseteq X$ a closed set that does not contain $x$. Then, for any $y\in A$, by Hausdorffness, we can define $U_{y},V_{y}$ disjoint open neighborhoods of $x$ and $y$ respectively. Therefore, $\{ V_{y} \}_{y\in A}\cup \{ X \backslash A \}$ is an open cover of $X$ and by paracompactness, there exists a locally finite refinement $\{ W_{\alpha} \}_{\alpha}$ s.t. without loss of generality $W_{y}\subseteq V_{y}$.
>    
>    By defining $W:=\bigcup_{y\in A}^{}W_{y}$ we have an open neighborhood of $A$. However, by local finiteness, there exists an open neighborhood $U\ni x$ and finite subset $K\subseteq A$ s.t. $U\cap V_{y}$ for all $y\in K$. Therefore, by defining $V:=U\cap \bigcap_{y\in K}^{}U_{y}$ we have that: $$V\cap W=\varnothing$$which shows the regularity.
>  2. Let $A,B\subseteq X$ be disjoint closed subsets. For every $a\in A$, there exist disjoint open sets $U_{a}\ni a$ and $V_{a}\supseteq B$ by regularity. Similarly, we have an open cover $\{ U_{a} \}_{a\in A}\cup \{ X \backslash A \}$ and a locally finite refinement $\{ V_{a} \}_{a\in A}$ that cover $A$. Let $V:=\bigcup_{a\in A}^{}V_{a}$. 
>     
>     For any $b\in B$, there exists open $W_{b}\ni b$ and a finite set $K\subseteq A$ s.t. $W_{b}\cap U_{a}= \varnothing$ for $a\notin K$. Then, $D_{b}:=W_{b}\cap \bigcap_{a\in K}^{}V_{a}$ does not intersect $V$.
>     
>	Therefore, $W:=\bigcup_{b\in B}^{}D_{b}$ is an open neighborhood of $B$ s.t. $V\cap W=\varnothing$.  This shows the normality.  	
---
##### Examples
> [!h] Example 1
> Every [[Compact Space]] is paracompact.

> [!proof]-
> For an open cover $\{ U_{\alpha} \}\alpha$ and a compact space $X$, let $\{ U_{i} \}_{i=1}^n$ be the finite subcover. Then, the subcover is a locally finite refinement.
---
> [!h] Example 2
> Any second countable [[Locally Compact Hausdorff Space]] is paracompact.

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
