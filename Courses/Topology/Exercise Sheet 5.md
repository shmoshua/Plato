#Series #Topology 

> [!def] Problem 1
> Let $X$ be a topological space.
> 1. If $X$ is Hausdorff, show that $\{ x \}$ is closed in $X$ for all $x\in X$.
> 
> We define a set $\tilde{X}:=X\cup \{ \infty \}$, where $\infty$ is any mathematical object not in $X$. We define a topology on $\tilde{X}$ so that $U$ is open if and only if either $U=\varnothing$, or $U=V\cup \{ \infty \}$ for some open set $V\subseteq X$.
> 1. Check that this defines a topology, and that the inclusion map $X\hookrightarrow \tilde{X}$ is continuous.
> 2. Show that the closure of $\{ \infty \}$ is equal to $\tilde{X}$, i.e., that the single point $\infty$ is dense in $\tilde{X}$.

We have that: 
1. Let $y\in \overline{\{ x \}}$. Then, for every neighborhood $U$ of $y$, $x\in U$. This implies that $x=y$ as $X$ is Hausdorff. Therefore, $\{ x \}$ is closed.
2. It is trivial to see that $\varnothing,\tilde{X}$ are open. Let $\{ U_{i} \}_{i\in I}$ now be open sets in $\tilde{X}$. Wlog we may assume that none of these are empty sets. Therefore, $\bigcup_{i\in I}^{}U_{i}=\bigcup_{i\in I}^{}V_{i}\cup \{ \infty \}=\left( \bigcup_{i\in I}^{}V_{i} \right)\cup \{ \infty \}$ which is open. Similarly, for $U_{1},U_{2}$ open, if one of them is $\varnothing$, the intersection is open. If both are non-empty, then $U_{1}\cap U_{2}=(V_{1}\cap V_{2})\cup \{ \infty \}$ which is open.
   
   Now, for any open $U\subseteq \tilde{X}$, the preimage of the inclusion is empty if $U$ is empty or $V$ if $U=V\cup \{ \infty \}$This shows that the inclusion is continuous.
3. Let $y\in X$ and $U$ an open neighborhood of $y$ in $\tilde{X}$. Then, by definition, $\infty\in U$. Therefore, $y\in \overline{\{ \infty \}}$. As $y$ was arbitrary, this proves the statement.
---
> [!def] Problem 2
> Let $X$ be a compact Hausdorff space. Let $(C_{n})_{n}$ be a sequence of closed subsets of $X$ with empty interior for all $n$. Denote $C:=\bigcup_{n\geq 1}^{}C_{n}$. Let $U$ be a non-empty open subset of $X$.
> 1. Let $x\in X$ and $A\subseteq X$ be a closed subspace with $x\notin A$. Show that there exists a neighborhood $U$ of $x$ s.t. $\overline{U}\cap A=\varnothing$.
> 1. Let $U_{0}=U$. Show that one can construct by induction a sequence of open set $(U_{n})_{n\geq 1}$ such that, for all $n\geq 1$, the properties $$\begin{cases}\overline{U}_{n}\cap C_{n}=\varnothing\\\overline{U}_{n}\subseteq U_{n-1}\end{cases}$$ are satisfied.
> 2. Show that: $$\bigcap_{n\geq 1}^{}\overline{U_{n}}\neq \varnothing$$and deduce that $U\cap(X \backslash C)\neq\varnothing$.
> 3. Deduce that the interior of $C$ is empty.
> 4. Show that if $(V_{n})$ is a sequence of dense open sets in $X$, the intersection $$\bigcap_{n\geq 1}^{}V_{n}$$ is still dense in $X$.
> 5. Give an example of a sequence $(V_{n})_{n}$ of dense open sets in the compact space $[0,1]$ such that the intersection of the $V_{n}$’s is not open.

We have: 
1. Let $y\in A$. Then, $x\neq y$ and as $X$ is Hausdorff, there exists disjoint open neighborhoods $U_{y},V_{y}$ of $x$ and $y$ respectively. As $A$ is a closed subspace, $A$ is compact and $\{ V_{y} \}_{y\in A}$ is an open cover of $A$. Therefore, there exists a finite set $J\subseteq A$ s.t. $\bigcup_{y\in J}^{}V_{y}\supseteq A$. Let $U:=\bigcap_{y\in J}^{}U_{y}$ which is an open neighborhood of $x$. Then, we have that $U\cap \bigcup_{y\in J}^{}V_{j}=\varnothing$ and as both sets are open, $\overline{U}\cap A \subseteq \overline{U}\cap \bigcup_{y\in J}^{}V_{j}=\varnothing$. 
2. As $C_{1}$ does not contain any non-empty open set, there exists $x_{1}\in U$ s.t. $x_{1}\notin C_{1}$. Therefore, there exists a neighborhood $U_{1}$ of $x_{1}$ modulo taking the intersection with $U$, s.t. $\overline{U_{1}}\cap C_{1} =\varnothing$ and $\overline{U_{1}}\subseteq U$.