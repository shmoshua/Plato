#Definition #Topology 

> [!definition]
> Let $X$ be a [[Topological Space|topological space]] and  $A \subseteq X$. 
> 1. The ***interior*** $A^\circ$ of $A$ is defined as: $$A^\circ :=\bigcup_{U\subseteq A,\text{open}}^{}U$$
> 2. The ***closure*** $\overline{A}$ of $A$ is defined as: $$\overline{A}:=\bigcap_{A\subseteq C, C\text{ closed}}^{}C$$
> 3. The ***boundary*** $\partial A$ is defined as $\overline{A} \cap \overline{X \backslash A}$.
> 
- **Remark**: In a [[Metric Space|metric space]], $A^\circ=\{ x\in A:\exists r>0. B_{<r}(x)\subseteq A \}$
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
---
> [!lemma] Proposition 1
> For any set $A\subseteq X$, $A^\circ$ is the largest open set contained in $A$.

> [!proof]-
> We first show that $A^\circ$ is open. For any $x\in A^\circ$, let $r>0$ s.t. $B(x,r)\subseteq A$. For any $y\in B(x,r)$, then $B(y,r-d(x,y))\subseteq B(x,r)\subseteq A$. Therefore, $y\in A^\circ$ and $B(x,r)\subseteq A^\circ$. This shows that $A^\circ$ is open.
> 
> Now, we show that if $B\subseteq A$ is open, then $B\subseteq A^\circ$. For any $x\in B$, there exists $r>0$ s.t. $B(x,r)\subseteq B\subseteq A$. Therefore, $x\in A^\circ$. Therefore, $B \subseteq A^\circ$. 
---
> [!lemma] Proposition 2
> For $A,B\subseteq X$:
> 1. $A$ is open if and only if $A=A^\circ$.
> 2. $(A^\circ)^\circ=A^\circ$.
> 3. If $A\subseteq B$, then $A^\circ \subseteq B^\circ$.
> 4. $(A\cap B)^\circ=A^\circ \cap B^\circ$

> [!proof]-
> We prove as follows: 
> 1. If $A=A^\circ$, then $A$ is open by Proposition 1. Conversely, if $A$ is open, $A$ is the largest open set contained in $A$, i.e. $A=A^\circ$.
> 2. $A^\circ$ is open, therefore, $A^\circ=(A^\circ)^\circ$.
> 3. Let $x\in A^\circ$. Then, there exists $r>0$ s.t. $B(x,r)\subseteq A\subseteq B$. Therefore, $x\in B^\circ$ and $A^\circ \subseteq B^\circ$.
> 4. Let $x\in (A\cap B)^\circ$. Then, there exists $r>0$ s.t. $B(x,r)\subseteq A\cap B$. Therefore, $B(x,r)\subseteq A$ and $B(x,r)\subseteq B$. It follows that $x\in A^\circ \cap B^\circ$.
>    
>    Conversely, if $A^\circ \cap B^\circ$, we have that $A^\circ \cap B^\circ \subseteq A\cap B$ and $A^\circ \cap B^\circ$ is open. Therefore, $$A^\circ  \cap B^\circ  = (A^\circ  \cap B^\circ )^\circ  \subseteq (A \cap B)^\circ $$
> 	   It follows that $(A \cap B)^\circ =A^\circ \cap B^\circ$.
---
> [!lemma] Proposition 4
> Let $X$ be a topological space and assume every $x\in X$ has a countable [[Fundamental System|fundamental system]] of (open) neighborhoods. Then, for $A\subseteq X$, the following are equivalent:
> 1. $x\in \overline{A}$
> 2. there exists $(x_{n})_{n}\subseteq A$ for all $n$ s.t. $x_{n}\to x$.

> [!proof]+
> We have:
> - <=: Let $U$ be a neighborhood of $x$. Since $x_{n}\to x$, there exists $N\in \mathbb{N}$ s.t. $x_{n}\in U$ for $n\geq N$. Therefore, $x_{N}\in A \cap U$ and $x\in \overline{A}$.
> - =>: If $x$ has a countable fundamental system of neighborhoods, there exists a