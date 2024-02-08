#Definition #Topology 

> [!definition]
> For a [[Metric Space|metric space]] $(X,d)$ and a subset $Y \subseteq X$, $(Y,d|_{Y\times Y})$ is a ***metric subspace*** of $(X,d)$.

---
##### Properties
> [!lemma] Lemma 1
> A set $B\subseteq Y$ is open in the subspace $Y$ if and only if there exists an open set $A\in X$ s.t. $$B=A \cap Y$$

> [!proof]-
> If $A$ is open in $X$ and $y\in A\cap Y$, then, there exists $r>0$ s.t. $B(y,r)\subseteq A$ and $y\in B(y,r)\cap Y\subseteq A\cap Y$. Therefore, $A \cap Y$ is open in $Y$.
> 
> Conversely, if $B \subseteq Y$ is open in the subspace $Y$, for $y\in B$ there exists $r(y)>0$ s.t. $B(y,r(y))\cap Y\subseteq B$. Therefore, $$B=\bigcup_{y\in B}^{}(B(y),r(y)\cap Y)=\left( \bigcup_{y\in B}^{}B(y,r(y)) \right) \cap Y$$
> This proves the statement.
---
