#Definition #Topology 

> [!definition]
> Let $X$ be a [[Topological Space|topological space]] and  $A \subseteq X$. The ***closure*** $\overline{A}$ of $A$ is defined as: $$\overline{A}:=\bigcap_{A\subseteq C, C\text{ closed}}^{}C$$
> 
 is a ***cluster point*** of $A \subseteq X$ if for every neighborhood $B$ of $x$, $$A \cap B\neq \varnothing$$
> Then, the ***closure*** of $A$ is defined as: $$\overline{A}:=\{ x\in A: x\text{ is a cluster point of }A \}$$
---
##### Properties
> [!lemma] Proposition 1
> $\overline{A}=X \backslash(X \backslash A)^\circ$

> [!proof]-
> We will first show that $\overline{A} \subseteq X \backslash (X \backslash A)^\circ$.  For $x\in \overline{A}$, $x$ is a cluster point of $A$. Then, for all $r>0$, $$B(x,r)\cap  A \neq \varnothing$$Therefore, $B(x,r) \not\subseteq X \backslash A$ and $x\in X \backslash (X \backslash A)^\circ$.
> 
> Conversely, assume $x\in X \backslash (X \backslash A)^\circ$. Let $B$ be wlog an open neighborhood of $x$. Then, there exists $r>0$ s.t. $B(x,r)\subseteq B$. As $B (x,r)\cap A \neq \varnothing$, we have $B\cap A\neq \varnothing$.

---
> [!lemma] Proposition 2
> For any $A\subseteq X$, $\overline{A}$ is the smallest closed set containing $A$.

> [!proof]-
> We have that $(X \backslash A)^\circ$ is the largest open set in $X \backslash A$. Therefore, $\overline{A}=X \backslash (X \backslash A)^\circ$ is the smallest closed set containing $X \backslash (X \backslash A)= A$, from [[Interior and Closure|Proposition 1]].
---
> [!lemma] Proposition 3
> For $A,B \subseteq X$,
> 1. $A$ is closed if and only if $A = \overline{A}.$
> 2. $\overline{\overline{A}}=\overline{A}$.
> 3. If $A \subseteq B$, then $\overline{A}\subseteq \overline{B}$
> 4. $\overline{A\cup B}=\overline{A}\cup \overline{B}$

> [!proof]-
> We have that: 
> 1. $A$ is closed if and only if $X \backslash A$ is open. This happens if and only if $(X \backslash A)^\circ=X \backslash A$, i.e. $\overline{A}=X \backslash (X \backslash A)^\circ=A$.
> 2. $\bar{A}$ is closed, therefore, $\overline{\overline{A}}=\overline{A}$.
> 3. If $A \subseteq B$, then $X  \backslash B \subseteq X \backslash A$. Then, $(X \backslash B)^\circ\subseteq (X\backslash A)^\circ$ and $\overline{A}\subseteq \overline{B}$.
> 4. We have that: $$\overline{A\cup B}=X \backslash (X \backslash A \cap X \backslash B)^\circ =X \backslash ((X \backslash A)^\circ  \cap (X \backslash B)^\circ)=\overline{A}\cup \overline{B}$$
---
> [!lemma] Proposition 4
> For non-empty $A\subseteq X$ and $x\in X$: $$x\in \overline{A}\iff d(x,A)=0$$In other words, $$\overline{A}=\bigcap_{r>0}^{}V_{r}(A)=\bigcap_{n\geq 1}^{}V_{1/n}(A)$$

> [!proof]-
> If $d(x,A)=0$, then for every $\varepsilon>0$, there exists $y\in A$ with $d(x,y)<\varepsilon$, i.e. for every $\varepsilon>0$, $B(x,\varepsilon)\cap A\neq \varnothing$. As every neighborhood contains an open ball inside, this proves that $x\in \overline{A}$.
>
> Conversely, if $x\in \overline{A}$, then for every $\varepsilon>0$, $B(x,\varepsilon)\cap A\neq \varnothing$, i.e. there exists $y\in A$ s.t. $d(x,y)<\varepsilon$. Therefore, $d(x,A)=0$.
- **Corollary**: Every closed set is the intersection of a decreasing sequence of open sets. 
- **Corollary**: Every open set is the union of an increasing sequence of closed sets. 
---
> [!lemma] Proposition 5
> For $A\subseteq X$, $$\overline{A}=\{ x\in X:\exists(x_{n})_{n}\subseteq A.\lim_{ n \to \infty } x_{n}=x \}$$

> [!proof]-
> Let $x\in X$ s.t. there exists $(x_{n})_{n}\subseteq A$ and $\lim_{ n \to \infty }x_{n}=x$. Then, for every neighborhood of $V$ in $x$, there exists $N\in \mathbb{N}$ s.t. $x_{n}\in V$ for $n\geq N$. This means that $V \cap A\neq \varnothing$. Therefore, $x\in \overline{A}$.
> 
> Conversely, if $x\in \overline{A}$, then for every positive integer $n$, $A\cap B(x, 1 / n)$ is non-empty. Let $x_{n}\in A\cap B(x, 1 / n)$. Then, $(x_{n})_{n}$ converges to $x$.
---