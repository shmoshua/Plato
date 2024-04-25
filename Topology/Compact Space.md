#Definition #Topology 

> [!definition]
>  A [[topological space]] $X$ is ***compact***, if every open covering has a finite sub-covering, i.e. if $(U_{i})_{i\in I}$ is a collection of open sets  of $X$ s.t. $\bigcup_{i\in I}^{}U_{i}=X$, then there exists a finite subset $J \subseteq I$ s.t. $\bigcup_{i\in J}^{}U_{i}=X$.
- **Related definition**: A subset $A\subseteq X$ is ***compact*** if it is with the subspace topology.
---
##### Properties
> [!lemma] Proposition 1
> Let $X$ be an compact space and $Y$ a topological space. Then, 
> 1. for a continuous function $f:X\to Y$. $f(X)\subseteq Y$ is compact.
> 2. any closed set $A\subseteq X$ is compact.
> 3. if $Y$ is [[Hausdorff Space|Hausdorff]] and $A\subseteq Y$ is compact, $A$ is closed.
> 4. if $Y$ is [[Hausdorff Space|Hausdorff]] and $f:X\to Y$ is a continuous bijection, then $f$ is a [[homeomorphism]].

> [!proof]-
> We have: 
> 1. Let $(U_{\lambda})_{\lambda}$ be an open cover of $f(X)$. Then, $(f^{-1}(U_{\lambda}))_{\lambda}$ is an open cover of $X$ and there exists a finite cover $(f^{-1}(U_{n}))_{n\in [N]}$ and a finite subcover $(U_{n})_{n\in [N]}$ of $f(X)$. 
> 2. Let $(U_{\lambda})_{\lambda}$ be a family of open sets s.t. $A\subseteq \bigcup_{\lambda\in \Lambda}^{}U_{\lambda}$. Then, $(U_{\lambda}\cup X \backslash A)_{\lambda}$ is an open cover of $X$. Therefore, there exists a finite subcover $(U_{n}\cup X \backslash A)_{n}$ and we have that $(U_{n})_{n}$ is a finite subcover of $A$.
> 3. It suffices to show that $X \backslash A$ is closed. Let $x_{0}\in X \backslash A$. For any $x\in A$, we define $U_{x},V_{x}$ as the open neighborhoods that separate $x_{0}$ and $x$ respectively. Then, $\{ V_{x} \}_{x}$ is an open cover of $A$ and by compactness, there exists a finite $B\subseteq A$ s.t. $\{ V_{x} \}_{x\in B}$ is a cover of $A$. 
>    
>    Now, consider $U:=\bigcap_{x\in B}^{}U_{x}$. $U$ is an open neighborhood of $x_{0}$. We have that for $y\in U$, $y\notin V_{x}$ for all $x\in B$. Therefore, $y\notin A$ and $U\subseteq X \backslash A$. 
>4. It suffices to show that $f$ is closed. For a closed set $A\subseteq X$, $A$ is compact, $f(A)$ is compact, hence closed. 

---
> [!lemma] Lemma 2
> Let $X$ be compact space and $Y$ a metric space. Further, let $f:X\to Y$ locally bounded, i.e. for all $x\in X$, there exists neighborhood $U \ni x$ s.t. $f|_{U}\subseteq B_{<r}(0)$ for some $r>0$. Then, $f$ is bounded on $X$.

> [!proof]-
> Let $U_{x}$ be the open neighborhood of $x$ s.t. $f|_{U_{x}}\subseteq B_{<r_{x}}(0)$ for $x\in X$. Then, $\{ U_{x} \}_{x\in X}$ is an open cover of $X$. Then, there exists finite $J\subseteq X$ s.t. $\bigcup_{x\in J}^{}U_{x}=X$. Therefore, $$f(X)\subseteq B_{<\max_{x\in J} r_{x}}(0)$$
---
> [!lemma] Lemma 3
> Let $X$ be a compact Hausdorff space. Then, every $x\in X$ has a [[fundamental system]] of closed neighborhoods in $X$.

> [!proof]-
> Let $x\in X$ and $U$ an open neighborhood of $x$. Let $C:=X-U$. As $C$ is closed and $x\notin C$, there exists an open neighborhood $V$ of $x$ s.t. $\overline{V}\cap C=\varnothing$. Therefore, $\overline{V}\subseteq U$. 

---
> [!lemma] Theorem 4 (Tychonoff)
> For any arbitrary family of compact spaces $\{ X_{i} \}_{i\in I}$, $X:=\prod_{i\in I}^{}X_{i}$ is compact with respect to the [[product topology]].

> [!proof]-
> Let $\mathcal{F}$ be an ultrafilter on $X$. As $(\pi_{i})_{*}(\mathcal{F})$ is an ultrafilter on $X_{i}$ by [[Ultrafilter#^8bbcf9|Lemma 5]] and $X_{i}$ is compact, by [[Ultrafilter#^041e9b|Proposition 4]], $(\pi_{i})_{*}(\mathcal{F})$ converges for all $i\in I$. By [[Filter#^0214a6|Lemma 5]], $\mathcal{F}$ converges. 
> 
> Therefore, using Proposition 4 again, this means that $X$ is compact.

- **Remark**: This is equivalent to [[Axiom of Choice]].
---
##### Related Properties

![[Ultrafilter#^041e9b|clean lk-hvr]]

---
##### Examples
> [!h] Example 1
> A discrete topological space $X$ is compact if and only if $X$ is finite.

> [!proof]-
> If $X$ is finite and discrete, there are only finitely many open sets, so $X$ is compact. Conversely, if $X$ is infinite, $(\{ x \})_{x\in X}$ has no finite subcovers.
---
> [!h] Example 2
> Let $X$ be a topological space and $(x_{n})_{n}\subseteq X$ with $x_{n}\to y\in X$. Then, $$A:=\{ x_{n} \}_{n}\cup \{ y \}\subseteq X$$is compact.

> [!proof]-
> Let $A\subseteq \bigcup_{{\lambda\in \Lambda}}^{}U_{\lambda}$ where $U_{\lambda}$ is open in $X$.  Then, there is $\lambda_{0}\in \Lambda$ s.t. $y\in U_{\lambda_{0}}$. Therefore, there exists $N\in \mathbb{N}$ s.t. $x_{n}\in U_{\lambda_{0}}$ for $n\geq N$. Further, for $n\in [N-1]$, let $U_{\lambda_{n}}$ s.t. $x_{n}\in U_{\lambda_{n}}$. Then, $$A\subseteq \bigcup_{0\leq n <N}^{}U_{\lambda_{n}}$$
---
> [!h] Example 3 (Heine-Borel)
> Let $A\subseteq \mathbb{R}^n$ for $n\geq 0$. Then, the following are equivalent:
> 1. $A$ is compact.
> 2. $A$ is closed and bounded.

> [!proof]-
> We first show it for $n=1$. 
> 1. if $A$ is compact, $A$ is closed as $\mathbb{R}$ is Hausdorff. By Lemma 2 and the locally bounded map $$\begin{array}{cccc} {}&{A}&\to&{\mathbb{R}}\\&{x} &\mapsto & {x } \end{array}{}$$$A$ is bounded in $X$. 
> 2. Conversely, if $A$ is closed and bounded, there exists $a\in \mathbb{R}$ s.t. $A\subseteq[-a,a]\subseteq \mathbb{R}$. As $A$ is closed, it suffices to show that $[-a,a]$ is compact. This is done by showing that $[0,1]$ is compact as a continuous image of the [[Cantor set]], which is compact. Then, one can easily establish a homeomorphism between $[-a,a]$ and $[0,1]$.
---
> [!h] Example 4
> The unit ball in $L^2([0,1])$ is not compact.
---
