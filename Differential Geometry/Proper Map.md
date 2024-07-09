#Definition #DifferentialGeometry 
> [!definition]
> Let $X,Y$ be [[Hausdorff Space|Hausdorff]] and $f\in C(M,N)$. Then, $f$ is ***proper*** if 
> 1. for all [[Compact Space|compact]] $K\subseteq N$, $f^{-1}(K)\subseteq M$ is compact.
---
##### Properties
> [!lemma] Proposition 1
> Let $f:X\to Y$ be a proper map:
> 1. If $Y$ is locally compact, then $f$ is closed.

> [!proof]-
> We have:
> 1. Let $C\subseteq X$ be closed and we want to show that $f(C)$ is closed. Let $y\in Y\backslash f(C)$. Then, there exists an open neighborhood $U\ni y$ s.t. $\overline{U}$ is compact. Then, by properness, $f^{-1}(\overline{U})$ is compact and $C\cap f^{-1}(\overline{U})$ is compact as well. Therefore, we have that: $$f(C\cap f^{-1}(\overline{U}))=f(C)\cap \overline{U}\subseteq Y$$is compact from continuity and is closed in $\overline{U}$. Therefore, $$V:=U \backslash(f(C)\cap \overline{U})=U \backslash f(C)$$is an open neighborhood of $y$ not intersecting $f(C)$. This shows that $f$ is closed.
---
