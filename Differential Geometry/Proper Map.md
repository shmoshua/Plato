#Definition #Topology 
> [!definition]
> A [[continuous function]] $f:X\to Y$ is ***proper*** if 
> 1. for all closed $C\subseteq X$, $f(C)$ is closed.
> 1. for all [[Compact Space|compact]] $K\subseteq Y$, $f^{-1}(K)\subseteq X$ is compact.
---
##### Properties
> [!lemma] Proposition 1
> Let $X$ be Hausdorff and $Y$ be locally compact Hausdorff. Then, TFAE:
> 1. $f:X\to Y$ is proper.
> 1. for all compact $K\subseteq Y$, $f^{-1}(K)\subseteq X$ is compact.

> [!proof]-
> We have:
> 1. (1=>2): by definition.
> 2. (2=>1): Let $C\subseteq X$ be closed. We want to show that $f(C)$ is closed. Let $y\in Y \backslash f(C)$. Then, there exists an open neighborhood $U\ni y$ s.t. $\overline{U}$ is compact. Then, by properness, we have that $f^{-1}(\overline{U})$ is compact and so is $C\cap f^{-1}(\overline{U})$. Therefore, $$f(C\cap f^{-1}(\overline{U}))=f(C)\cap \overline{U}$$which is compact and is closed in $\overline{U}$. Therefore, $V:= U \backslash (f(C)\cap \overline{U})=U \backslash f(C)$ is an open neighborhood of $y$ not intersecting $f(C)$. This shows that $f(C)$ is closed.
---
