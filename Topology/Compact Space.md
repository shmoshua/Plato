#Definition #Topology 

> [!definition]
>  A [[topological space]] $X$ is ***compact***, if every open covering has a finite sub-covering, i.e. if $(U_{i})_{i\in I}$ is a collection of open sets  of $X$ s.t. $\bigcup_{i\in I}^{}U_{i}=X$, then there exists a finite subset $J \subseteq I$ s.t. $\bigcup_{i\in J}^{}U_{i}=X$.
- **Related definition**: A subset $A\subseteq X$ is ***compact*** if it is with the subspace topology.
---
##### Properties
> [!lemma]
> Let $X$ be compact space and $Y$ a metric space. Further, let $f:X\to Y$ locally bounded, i.e. for all $x\in X$, there exists neighborhood $U \ni x$ s.t. $f|_{U}\subseteq B_{<r}(0)$ for some $r>0$. Then, $f$ is bounded on $X$.

> [!proof]-
> Let $U_{x}$ be the open neighborhood of $x$ s.t. $f|_{U_{x}}\subseteq B_{<r_{x}}(0)$ for $x\in X$. Then, $\{ U_{x} \}_{x\in X}$ is an open cover of $X$. Then, there exists finite $J\subseteq X$ s.t. $\bigcup_{x\in J}^{}U_{x}=X$. Therefore, $$f(X)\subseteq B_{<\max_{x\in J} r_{x}}(0)$$
---
