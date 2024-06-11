#Definition #Topology 

> [!definition]
> Let $X$ be a [[Topological Space|topological space]] and  $A \subseteq X$. 
> 1. The ***interior*** $A^\circ$ of $A$ is defined as: $$A^\circ :=\bigcup_{U\subseteq A,\text{open}}^{}U$$
> 2. The ***closure*** $\overline{A}$ of $A$ is defined as: $$\overline{A}:=\bigcap_{A\subseteq C, C\text{ closed}}^{}C$$
> 3. The ***boundary*** $\partial A$ is defined as $\overline{A} \cap \overline{X \backslash A}$.
> 
- **Remark**: In a [[Metric Space|metric space]], $A^\circ=\{ x\in A:\exists r>0. B_{<r}(x)\subseteq A \}$.
- **Remark**: $A^\circ$ is the largest open set contained in $A$ and $\overline{A}$ is the smallest closed set that contains $A$.
---
##### Properties
> [!lemma] Lemma 1
> For $A\subseteq X$:
> 1. ${(X\backslash A)}^\circ=X \backslash \overline{A}$
> 2. $\overline{X\backslash A}=X \backslash A^\circ$
> 3. $\partial A= \overline{A} \backslash A^\circ$
> 4. $x\in A^\circ$ if and only if there is an open neighborhood $U\subseteq X$ of $x$ in $A$. 
> 5. $x\in \overline{A}$ if and only if for all neighborhood $U\subseteq X$ of $x$, $A\cap U\neq \varnothing$ 
> 6. $A^{\circ}=A$ if and only if $A$ is open.
> 7. $\overline{A}=A$ if and only if $A$ is closed.
> 8. $X=A^\circ\sqcup (X\backslash A)^\circ\sqcup \partial A$

> [!proof]-
> We have:
> 1. $(X \backslash A)^\circ=\bigcup_{U\subseteq X \backslash A, U\text{ open}}^{}U=\bigcup_{A\subseteq F, F\text{ closed}}^{}X \backslash F=X \backslash \bigcup_{A\subseteq F, F\text{ closed}} F=X \backslash \overline{A}$.
> 2. $\overline{X \backslash A}=\bigcap_{ X\backslash A\subseteq F, F\text{ closed}}^{}F=\bigcap_{U\subseteq A, U\text{ open}}^{}X \backslash U=X \backslash \bigcup_{U\subseteq A, U\text{ open}}^{}U=X \backslash A^\circ$
> 3. $\partial A=\overline{A}\cap \overline{X \backslash A}=\overline{A}\cap X \backslash A^\circ = \overline{A} \backslash A^\circ$.
> 4. $A^\circ$ is the largest open set contained in $A$. 
> 5. if $x\notin \overline{A}$ then $x\in X \backslash \overline{A}$ which is an open neighborhood of $x$. Conversely if for $U\ni x$, we have $A\cap U=\varnothing$, then $X \backslash U$ is closed and contains $A$. Therefore, $x\notin \overline{A}$.
> 6. As $A^\circ$ is open, $A$ is open. Conversely, if $A$ is open, $A^\circ\supseteq A$.
> 7. As $\overline{A}$ is closed, $A$ is closed. Conversely, if $A$ is closed, $\overline{A}\subseteq A$.
---
> [!lemma] Proposition 2
> Let $X$ be a topological space and assume every $x\in X$ has a countable [[Local Base of Topology|fundamental system]] of (open) neighborhoods. Then, for $A\subseteq X$, the following are equivalent:
> 1. $x\in \overline{A}$
> 2. there exists $(x_{n})_{n}\subseteq A$ for all $n$ s.t. $x_{n}\to x$.

> [!proof]-
> We have:
> - <=: Let $U$ be a neighborhood of $x$. Since $x_{n}\to x$, there exists $N\in \mathbb{N}$ s.t. $x_{n}\in U$ for $n\geq N$. Therefore, $x_{N}\in A \cap U$ and $x\in \overline{A}$.
> - =>: If $x$ has a countable fundamental system of neighborhoods, there exists by [[Local Base of Topology|Prop 1.1]] a decreasing fundamental system of open neighborhoods $(U_{n})_{n}$ of $x$. As $x\in \overline{A}$, $A\cap U_{n}\neq \varnothing$ and we find $(x_{n})_{n}$ s.t. $x_{n}\in A\cap U_{n}$. 
>   
>   Now for any neighborhood $U$ of $x$, let $N\in \mathbb{N}$ s.t. $U_{n}\subseteq U$ for all $n\geq N$. Then, for all $n\geq N$, $x_{n}\in U$. This proves the statement.
---
