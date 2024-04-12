#Definition #Topology 

> [!definition]
> A [[topological space]] $X$ is ***connected*** if one of the following equivalent conditions hold:
> 1. Any [[Continuous Function|continuous map]] $f:X\to D$ for a discrete set $D$ is constant.
> 2. Any [[Continuous Function|continuous map]] $f:X\to \{ 0,1 \}$ is constant.
> 3. For all topological spaces $X_{1},X_{2}$ s.t. $X$ is homeomorphic to $X_{1}\sqcup X_{2}$, then: $$X_{1}=\varnothing\lor X_{2}=\varnothing$$
> 4. For all pair of disjoint open sets $U_{1},U_{2}\subseteq X$, if $U_{1}\cup U_{2}=X$ then,$$U_{1}=\varnothing\lor U_{2}=\varnothing$$
> 5. The only sets that are both open and closed are $\varnothing$ and $X$.
- **Related definition**: A set $A\subseteq X$ is ***connected*** if $A$ is connected subspace of $X$. 
- **Related definition**: For $x,y\in X$, we define the equivalence relation $x\sim y$ if and only if there exists a connected set $A\subseteq X$ s.t. $\{ x,y \}\subseteq A$. Then, the equivalence classes define the ***connected components*** of $X$. 
---
##### Properties

> [!lemma] Lemma 1
> Let $X$ be a [[topological space]] and $(A_{i})_{i\in I}$ be any family of connected subsets of $X$. If $\bigcap_{i\in I}^{}A_{i}\neq \varnothing$, then $\bigcup_{i\in I}^{}A_{i}$ is connected.

> [!proof]-
> Let $f:\bigcup_{{i}}^{}A_{i}\to \{ 0,1 \}$ to be continuous. Then, $f|_{A_{i}}$ is continuous for each $i$ so constant. However, $\bigcap_{i\in I}^{}A_{i}\neq \varnothing$, hence $f$ is constant.
---

> [!lemma] Lemma 2
> For a connected set $A\subseteq X$ and $f:X\to Y$ continuous, 
> 1. $\overline{A}$ is connected.
> 2. $f(A)$ is connected.

> [!proof]-
> We have: 
> 1. Let $\overline{A}=U_{1}\cup U_{2}$ where $U_{1},U_{2}$ are disjoint. Then, $A=(U_{1}\cap A)\cup(U_{2}\cap A)$ and by connectedness, $U_{1}\cap A=\varnothing$ or $U_{2}\cap A=\varnothing$. Wlog assume $U_{1}\cap A=\varnothing$. Then, $A\subseteq U_{2}$. Therefore, $$U_{1}=U_{1}\cap \overline{A}\subseteq U_{1}\cap \overline{U_{2}}=\varnothing$$
> 2. Let $f(A)=U_{1}\cup U_{2}$ where $U_{1},U_{2}$ are disjoint open. Then, $f^{-1}(U_{1}),f^{-1}(U_{2})$ are disjoint open and $A=f^{-1}(U_{1})\cup f^{-1}(U_{2})$. Therefore, wlog $f^{-1}(U_{1})=\varnothing$. Therefore, $U_{1}=\varnothing$.
---
##### Examples
> [!h] Example
> We have: 
> 1. A discrete space is connected if it has $\leq 1$ elements.
> 2. In $\mathbb{R}$, $A\subseteq \mathbb{R}$ is connected if and only if $A$ is an interval.

> [!proof]-
> Let $A\subseteq \mathbb{R}$ be a connected set. If $\left| A \right|\leq 1$, then $A$ is an interval. Now assume $\left| A \right|\geq 2$ with $a<c<b$ where $a,b\in A$. Assume $c\notin A$. Then, $$A=[(-\infty,c)\cap A]\sqcup[(c,+\infty)\cap A]$$and either $(-\infty,c)\cap A=\varnothing$ or  $(c,+\infty)\cap A=\varnothing$, which is a contradiction as $a,b\in A$.
> 
> Conversely, assume $A=[a,b]$ with $a\leq b$. Let $A=U_{1}\sqcup U_{2}$ with $U_{1},U_{2}$ open. Let wlog $a\in U_{1}$, we need to show that $A=U_{1}$. Let $c:=\sup_{{[a,t]\subseteq U_{1}}} t$. Then, we claim that $[a,c]\subseteq U_{1}$. Otherwise, $c\in U_{2}$ and as $U_{2}$ is open, there exists $\varepsilon>0$ s.t. $(c-\varepsilon,c+\varepsilon)\cap A\subseteq U_{2}$. Therefore, $c\leq c-\varepsilon$, which is a contradiction.
> 
> Assume $c\neq b$. Then, there exists $\varepsilon>0$ s.t. $(c-\varepsilon,c+\varepsilon)\cap A\subseteq U_{1}$ and $c+\varepsilon<b$. This is a contradiction to the maximality of $c$, as $\left[ a,c+\frac{\varepsilon}{2} \right]\subseteq U_{1}$. 