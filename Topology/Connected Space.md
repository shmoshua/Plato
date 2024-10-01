#Definition #Topology 

> [!definition]
> A [[Topological Space]] $X$ is ***connected*** if one of the following equivalent conditions hold:
> 1. Any [[Continuous Function|continuous map]] $f:X\to D$ for a discrete set $D$ is constant.
> 2. Any [[Continuous Function|continuous map]] $f:X\to \{ 0,1 \}$ is constant.
> 4. For all pair of disjoint open sets $U_{1},U_{2}\subseteq X$, if $U_{1}\sqcup U_{2}=X$ then, $U_{1}=\varnothing\lor U_{2}=\varnothing$.
> 5. For all pair of disjoint closed sets $C_{1},C_{2}\subseteq X$, if $C_{1}\sqcup C_{2}=X$ then, $C_{1}=\varnothing\lor C_{2}=\varnothing$.
> 6. The only sets that are both open and closed are $\varnothing$ and $X$.
- **Related definition**: A set $A\subseteq X$ is ***connected*** if $A$ is connected subspace of $X$. 
- **Related definition**: For $x,y\in X$, we define the equivalence relation $x\sim y$ if and only if there exists a connected set $A\subseteq X$ s.t. $\{ x,y \}\subseteq A$. Then, the equivalence classes define the ***connected components*** of $X$. Similarly for $x_{0}\in X$, the connected component of $x_{0}$ is the union of all connected subspaces of $X$ containing $x_{0}$, i.e. $\bigcup_{x_{0}\in A\subseteq X,A \text{ connected}}^{}A$.
- **Remark**: the connected component of $x_{0}$ is the largest connected set containing $x_{0}$.
- **Related definition**: $X$ is ***totally disconnected***, if for all $x_{0}\in X$, the connected component of $x_{0}$ is $\{ x_{0} \}$, e.g. $\mathbb{Q}$.
---
##### Properties

> [!lemma] Proposition 1
> For a topological space $X$, TFAE:
> 1. Any [[Continuous Function|continuous map]] $f:X\to D$ for a discrete set $D$ is constant.
> 2. Any [[Continuous Function|continuous map]] $f:X\to \{ 0,1 \}$ is constant.
> 4. For all pair of disjoint open sets $U_{1},U_{2}\subseteq X$, if $U_{1}\sqcup U_{2}=X$ then, $U_{1}=\varnothing\lor U_{2}=\varnothing$.
> 5. For all pair of disjoint closed sets $C_{1},C_{2}\subseteq X$, if $C_{1}\sqcup C_{2}=X$ then, $C_{1}=\varnothing\lor C_{2}=\varnothing$.
> 5. The only sets that are both open and closed are $\varnothing$ and $X$.

> [!proof]-
> We have that:
> 1. (1=>2): obvious as $\{ 0,1 \}$ is discretre.
> 2. (2=>3): let $\chi_{U_{1}}:X\to \{ 0,1 \}$. Then, $\chi_{U_{1}}$ is continuous and constant. If $\chi_{U_{1}}=0$, then $U_{1}=\varnothing$. If $\chi_{U_{1}}=1$, then $U_{1}=X$ and $U_{2}=\varnothing$.
> 3. (3=>4): Take $U_{1}:=X \backslash C_{1}$ and $U_{2}:=X \backslash C_{2}$. 
> 4. (4=>5): let $U\subseteq X$ be a proper subset that is both open and closed. Then, $X \backslash U$ is closed as well and $U,X \backslash U$ are disjoint closed partition of $X$, hence $U=\varnothing$.
> 5. (5=>1): Let $f:X\to D$ be a non-constant continuous map. Then, let $x\in f(X)$ with $U:=f^{-1}(\{ x \})$, which is open and is not $\varnothing$ or $X$. However, $X \backslash U=f^{-1}(D\backslash \{ x \})$ is also open. Therefore, $U$ is also closed.
---
> [!lemma] Lemma 2
> Let $X$ be a [[Topological Space]] and $(A_{i})_{i\in I}$ be any family of connected subsets of $X$. 
> 1. If $\bigcap_{i\in I}^{}A_{i}\neq \varnothing$, then $\bigcup_{i\in I}^{}A_{i}$ is connected.

> [!proof]-
> Let $f:\bigcup_{{i}}^{}A_{i}\to \{ 0,1 \}$ to be continuous. Then, $f|_{A_{i}}$ is continuous for each $i$ so constant. However, $\bigcap_{i\in I}^{}A_{i}\neq \varnothing$, hence $f$ is constant.
---

> [!lemma] Lemma 3
> For a connected set $A\subseteq X$ and $f:X\to Y$ continuous, 
> 1. $\overline{A}$ is connected.
> 2. $f(A)$ is connected.
> 3. For $x\in X$, the connected component of $x$ is closed.

> [!proof]-
> We have: 
> 1. Let $\overline{A}=U_{1}\sqcup U_{2}$ both open. Then, $A=(U_{1}\cap A)\sqcup(U_{2}\cap A)$ and by connectedness, $U_{1}\cap A=\varnothing$ or $U_{2}\cap A=\varnothing$. Wlog assume $U_{1}\cap A=\varnothing$. Then, $A\subseteq U_{2}$. Therefore, $$U_{1}=U_{1}\cap \overline{A}\subseteq U_{1}\cap \overline{U_{2}}=\varnothing$$
> 2. Let $f(A)=U_{1}\cup U_{2}$ where $U_{1},U_{2}$ are disjoint open. Then, $f^{-1}(U_{1}),f^{-1}(U_{2})$ are disjoint open and $A=f^{-1}(U_{1})\cup f^{-1}(U_{2})$. Therefore, wlog $f^{-1}(U_{1})=\varnothing$. Therefore, $U_{1}=\varnothing$.
> 3. Let $A$ be the connected component. Then, $\overline{A}$ is connected and contains $x$. However, as $A$ is the largest connected set containing $x$, $\overline{A}\subseteq A$ and $A$ is closed. 
- **Corollary (Intermediate Value Theorem):** if $f:\mathbb{R}\to \mathbb{R}$ is continuous and $f(a)<c<f(b)$, there exists $x$ between $a$ and $b$ s.t. $f(x)=c$.
---
> [!lemma] Lemma 4
> Let $A\subseteq X$ be a connected set and $B\subseteq X$. 
> 1. if $A\subseteq B\subseteq \overline{A}$, $B$ is connected.
> 1. if $A\cap \partial B$ is empty, $A\subseteq B^\circ$ or $A\subseteq (X \backslash B)^\circ=X \backslash \overline{B}$.
> 2. if $A\cap B$ and $A\cap(X \backslash B)$ are both non-empty, deduce that $A\cap \partial B\neq \varnothing$.
> 3. If $X$ is connected, and $B$ is not empty nor equal to $X$, show that $\partial B$ is not empty.

> [!proof]-
> We have:
> 1. Assume $A\subseteq B\subseteq \overline{A}$ but $B$ is not connected. Then, there exists disjoint open $U_{1},U_{2}$ with $B\subseteq U_{1}\cup U_{2}$ s.t. $B\cap U_{1},B\cap U_{2}\neq \varnothing$. Then, $A\subseteq U_{1}\cup U_{2}$ and $A\cap U_{1}$ and $A\cap U_{2}$ are disjoint. However, as $A$ is connected, we can assume wlog $A\subseteq U_{1}$. Therefore, $U_{2}^c$ is a closed set that contains $A$ and $\overline{A}\subseteq U_{2}^c$. This is a contradiction to $B\subseteq \overline{A}$. 
> 2. If $A\cap \partial B$ is empty, by [[Interior and Closure|Lemma 1.8]], $A\cap B^\circ$ and $A\cap(X \backslash B)^\circ$ are two open subsets that cover $B$. As $A$ is connected, we have that either $A\subseteq B^\circ$ or $A\subseteq(X \backslash B)^\circ$.
> 3. If $A\cap \partial B=\varnothing$ then either $A\subseteq B^\circ\subseteq B$ or $A\subseteq(X\backslash B)^\circ\subseteq (X \backslash B)$.
> 4. Apply 3 to $A=X$.
- **Remark**: If $X$ is not connected, there exists a non-empty proper subset $U\subsetneq X$ with $\partial U=\varnothing$.
---
##### Examples
> [!h] Example
> We have: 
> 1. A discrete space is connected if and only if it has $\leq 1$ elements.
> 2. In $\mathbb{R}$, $A\subseteq \mathbb{R}$ is connected if and only if $A$ is an interval.
> 3. $\mathbb{R}^n$ is connected.
> 4. $\mathbb{R}^n \backslash \{ 0 \}$ is connected for $n\geq 2$.
> 5. $S^n$ is connected if and only if $n\geq 1$.

> [!proof]-
> We have:
> 1. Let $A\subseteq \mathbb{R}$ be a connected set. If $\left| A \right|\leq 1$, then $A$ is an interval. Now assume $\left| A \right|\geq 2$ with $a<c<b$ where $a,b\in A$. Assume $c\notin A$. Then, $$A=[(-\infty,c)\cap A]\sqcup[(c,+\infty)\cap A]$$and either $(-\infty,c)\cap A=\varnothing$ or  $(c,+\infty)\cap A=\varnothing$, which is a contradiction as $a,b\in A$.
>    
>    Conversely, assume $A=[a,b]$ with $a\leq b$. Let $A=U_{1}\sqcup U_{2}$ with $U_{1},U_{2}$ open. Let wlog $a\in U_{1}$, we need to show that $A=U_{1}$. Let $c:=\sup_{{[a,t]\subseteq U_{1}}} t$. Then, we claim that $[a,c]\subseteq U_{1}$. Otherwise, $c\in U_{2}$ and as $U_{2}$ is open, there exists $\varepsilon>0$ s.t. $(c-\varepsilon,c+\varepsilon)\cap A\subseteq U_{2}$. Therefore, $c\leq c-\varepsilon$, which is a contradiction.
>    
>    Assume $c\neq b$. Then, there exists $\varepsilon>0$ s.t. $(c-\varepsilon,c+\varepsilon)\cap A\subseteq U_{1}$ and $c+\varepsilon<b$. This is a contradiction to the maximality of $c$, as $\left[ a,c+\frac{\varepsilon}{2} \right]\subseteq U_{1}$. 
>  2. We show it by induction on $n$. Consider the map: $$\rho:\mathbb{R}\times \mathbb{R}^{n-1}\to \mathbb{R}^n,\quad (x,v)\mapsto (x,v)$$which is clearly continuous. Now, define $\rho_{v}:\mathbb{R}\to \mathbb{R}^n, x\mapsto \rho(x,v)$ and $\rho_{x}:\mathbb{R}^{n-1}\to \mathbb{R}^n,v\mapsto \rho(x,v)$ which are also continuous. Given $f:\mathbb{R}^n\to \{ 0,1 \}$ continuous, $f\circ\rho_{v}$ is continuous and constant. Then,
> 	 1. $U_{0}:=\{ v\in \mathbb{R}^{n-1}:f\circ\rho_{v}=0 \}$
> 	 2. $U_{1}:=\{ v\in \mathbb{R}^{n-1}:f\circ\rho_{v}=1 \}$
> 	
> 	Then, $\mathbb{R}^{n-1}=U_{0}\sqcup U_{1}$. Further, $U_{i}=(f\circ\rho_{x})^{-1}(i)$ so they're both open and by induction hypothesis, $U_{0}=\varnothing$ or $U_{1}=\varnothing$. Therefore, $f$ is constant.
> 3. As $\mathbb{R}^n \backslash\{ 0 \}\cong (0,+\infty)\times S^1\times[0,\pi]^{n-2}$ and $(0,+\infty)$ and $S^1$ are connected, $\mathbb{R}^2 \backslash\{ 0 \}$ is connected. For $n\geq 3$, we can use induction similar to 2. 
> 4. $S^0=\{ -1,1 \}$ is a disconnected set from 1. For $n\geq 1$, we have that: $$\mathbb{R}^{n+1} \backslash\{ 0 \}\to S^{n},(r,\phi,\theta_{1},\dots,\theta_{n-1})\mapsto(1,\phi,\theta_{1},\dots,\theta_{n-1})$$which is clearly continuous and surjective. Therefore, $S^n$ is connected as a continuous image of a connected set.
---
> [!h] Example 2
> We have that: 
> 1. $\pi_{0}(\text{Homeo}(\mathbb{T}^{n}))\cong\text{GL}(n,\mathbb{Z})$
---
> [!h] Example 3
> We have that: 
> 1. $\text{O}(4,\mathbb{R})\leq \text{Diff}(S^3)$.
> 2. $\pi_{0}(\text{Diff}(S^3))\cong \mathbb{Z} / 2\mathbb{Z}$.
> 3. $\pi_{0}(\text{O}(4,\mathbb{R}))\cong \mathbb{Z} / 2\mathbb{Z}$.

> [!proof]-
> As $\det:\text{O}(4,\mathbb{R})\to \{ \pm 1 \}$ is a continuous map, $\pi_{0}(\text{O}(4,\mathbb{R}))$ has at least 2 elements. We can show that $\text{O}(4,\mathbb{R})\cap \text{SL}(4,\mathbb{R})$ are path-connected and therefore, $\pi_{0}(\text{O}(4,\mathbb{R}))\cong \mathbb{Z} / 2\mathbb{Z}$.
---
![[Locally Connected Space#^62ae51]]
![[Locally Connected Space#^35d8ef|p]]
---