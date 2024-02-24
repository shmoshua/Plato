#Definition #Topology 

> [!definition]
> A [[topological space]] $X$ is ***connected*** if one of the following equivalent conditions hold:
> 1. For all topological spaces $X_{1},X_{2}$ s.t. $X$ is homeomorphic to $X_{1}\sqcup X_{2}$, then: $$X_{1}=\varnothing\lor X_{2}=\varnothing$$
> 2. For all pair of disjoint open sets $U_{1},U_{2}\subseteq X$, if $U_{1}\cup U_{2}=X$ then,$$U_{1}=\varnothing\lor U_{2}=\varnothing$$
> 3. The only sets that are both open and closed are $\varnothing$ and $X$.
---
##### Properties
> [!lemma] Lemma 1
> For a connected set $A\subseteq X$ and $f:X\to Y$ continuous, 
> 1. $\overline{A}$ is connected.
> 2. $f(A)$ is connected.

> [!proof]+
> We have: 
> 1. Let $\overline{A}=U_{1}\cup U_{2}$ where $U_{1},U_{2}$ are disjoint. Then, $A=(U_{1}\cap A)\cup(U_{2}\cap A)$ and by connectedness, $U_{1}\cap A=\varnothing$ or $U_{2}\cap A=\varnothing$. Wlog assume $U_{1}\cap A=\varnothing$. Then, $A\subseteq U_{2}$. Therefore, $$U_{1}=U_{1}\cap \overline{A}\subseteq U_{1}\cap \overline{U_{2}}=\varnothing$$
> 2. Let $f(A)=U_{1}\cup U_{2}$ where $U_{1},U_{2}$ are disjoint open. Then, $f^{-1}()$
---

