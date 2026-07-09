#Definition #Algebra 

> [!definition]
> Let $R$ be a commutative [[ring]]. We have that the ***spectrum*** $\text{Spec}(R)$ is defined as the set of all [[Prime Ideal|prime ideals]] of $R$ equipped with the [[Zariski topology]], i.e. the basis is given by $\{ X_{f} \}_{f\in R}$ where: $$X_{f}:=\text{Spec}(R) \backslash \{  P : f\in P \}$$
- **Remark**: Let $V(E):=\{ P: E\subseteq P \}$. 
---
##### Properties
> [!lemma] Proposition 1
> Let $f,g\in R$.
> 1. $X_{f}$ form the basis of the Zariski topology.
> 2. $X_{f}\cap X_{g}=X_{fg}$
> 3. $X_{f}=\varnothing$ if and only if $f$ is nilpotent.
> 4. $X_{f}=\text{Spec}(R)$ if and only if $f$ is a unit.
> 5. $X_{f}=X_g$ if and only if $\sqrt{ (f) }=\sqrt{ (g) }$.
> 6. $X$ is quasi-compact.

> [!proof]-
> We have that:
> 1. Obvious.
> 2. This is equivalent to $V(f)\cup V(g)=V(fg)$. Let $P\in V(f)\cup V(g)$. Then, $f\in P$ or $g\in P$. Hence, $fg\in P$ and $P\in V(fg)$. Conversely, if $fg\in P$, as $P$ is prime $f\in P$ or $g\in P$. This proves the statement.
> 3. $\sqrt{ (0) }=\bigcap_{P}^{}P$. Hence, $f\in\sqrt{ (0) }$ if and only if $V(f)=\text{Spec}(R)$.
> 4. $f$ is a unit if and only if it is not contained in any prime ideal.
> 5. By [[Radical (Ring)|Lemma 2]], we have that $\sqrt{ (f) }=\bigcap_{(f)\subseteq P}^{}P$. Hence, if $X_{f}=X_{g}$, then $V(f)=V(g)$ and: $$\sqrt{ (f) }=\bigcap_{P\in V(f)}^{}P=\bigcap_{P\in V(g)}^{}P=\sqrt{ (g) }$$Conversely, if $\sqrt{ (f) }=\sqrt{ (g) }$, then let $P\in V(f)$, i.e. $f\in P$ and as we have that $g^n = af$ for some $a\in R$, $g^n\in P$. Hence, $g\in P$. By symmetry we have our statement.
> 6. Let $X = \bigcup_{f\in I}^{}X_{f}$. Hence, $\varnothing = \bigcap_{f\in I}^{}V(f)=V(I)$. Hence, $(I)=R$. Therefore, $1=r_{1}f_{1}+\dots+r_{n}f_{n}$ for some $f_{1},\dots,f_{n}\in I$. We have that $V(I)=V(f_{1},\dots,f_{n})$. Hence, $X=\bigcup_{i}^{}X_{f_{i}}$. 
> 