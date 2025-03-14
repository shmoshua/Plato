#Definition #Topology 

> [!definition]
>  A [[Topological Space]] $X$ is ***compact***, if every open covering has a finite sub-covering, i.e. if $(U_{i})_{i\in I}$ is a collection of open sets  of $X$ s.t. $\bigcup_{i\in I}^{}U_{i}=X$, then there exists a finite subset $J \subseteq I$ s.t. $\bigcup_{i\in J}^{}U_{i}=X$.
- **Related definition**: A subset $A\subseteq X$ is ***compact*** if it is with the subspace topology.
- **Related definition**: A subset $A\subseteq X$ is ***relatively compact*** if $\overline{A}$ is compact.
- **Related Definition**: $X$ is ***sequentially compact*** if every sequence $(x_{n})_{n}\subseteq X$ has a convergent subsequence.
- **Related Definition**:  A [[Metric Space]] $(X,d)$ is ***totally bounded/pre-compact*** if for every $\varepsilon>0$, there exists finite $J$ s.t. $\bigcup_{i\in J}^{}B(x_{i},\varepsilon)=X$. In other words, for every $\varepsilon>0$, there exists finite $A\subseteq X$ s.t. $d(x,A)<\varepsilon$ for all $x\in X$. Then, $A$ is called ***$\varepsilon$-net***.
---
##### Properties
> [!lemma] Proposition 1
> Let $X$ be an compact space and $Y$ a topological space. Then, 
> 1. for a continuous function $f:X\to Y$. $f(X)\subseteq Y$ is compact.
> 2. any closed set $A\subseteq X$ is compact.
> 3. for compact sets $A_{1},A_{2}\subseteq X$, $A_{1}\cup A_{2}$ is compact.
> 4. if $Y$ is [[Hausdorff Space|Hausdorff]] and $A\subseteq Y$ is compact, $A$ is closed.
> 5.  If $Y$ is [[Hausdorff Space|Hausdorff]] and $A_{1},A_{2}\subseteq Y$ compact, $A_{1}\cap A_{2}$ is compact.
> 6. if $Y$ is [[Hausdorff Space|Hausdorff]] and $f:X\to Y$ is a continuous bijection, then $f$ is a [[Homeomorphism]].

^2251ae

> [!proof]-
> We have: 
> 1. Let $(U_{\lambda})_{\lambda}$ be an open cover of $f(X)$. Then, $(f^{-1}(U_{\lambda}))_{\lambda}$ is an open cover of $X$ and there exists a finite cover $(f^{-1}(U_{n}))_{n\in [N]}$ and a finite subcover $(U_{n})_{n\in [N]}$ of $f(X)$. 
> 2. Let $(U_{\lambda})_{\lambda}$ be a family of open sets s.t. $A\subseteq \bigcup_{\lambda\in \Lambda}^{}U_{\lambda}$. Then, $(U_{\lambda}\cup X \backslash A)_{\lambda}$ is an open cover of $X$. Therefore, there exists a finite subcover $(U_{n}\cup X \backslash A)_{n}$ and we have that $(U_{n})_{n}$ is a finite subcover of $A$.
> 3. Let $(U_{i})_{i\in I}$ be an open cover of $A_{1}\cup A_{2}$. Then, it is also an open cover of $A_{1}$ and $A_{2}$ and there exist finite sets $J_{1},J_{2}\subseteq I$ s.t. $A_{1}\cup A_{2}\subseteq \bigcup_{i\in J_{1}\cup J_{2}}^{}U_{i}$. Therefore, $A_{1}\cup A_{2}$ is compact.
> 4. It suffices to show that $X \backslash A$ is open. Let $x_{0}\in X \backslash A$. For any $x\in A$, we define $U_{x},V_{x}$ as the open neighborhoods that separate $x_{0}$ and $x$ respectively. Then, $\{ V_{x} \}_{x}$ is an open cover of $A$ and by compactness, there exists a finite $B\subseteq A$ s.t. $\{ V_{x} \}_{x\in B}$ is a cover of $A$. 
>    
>    Now, consider $U:=\bigcap_{x\in B}^{}U_{x}$. $U$ is an open neighborhood of $x_{0}$. We have that for $y\in U$, $y\notin V_{x}$ for all $x\in B$. Therefore, $y\notin A$ and $U\subseteq X \backslash A$. 
>  5. Let $(U_{i})_{i\in I}$ be an open cover of $A_{1}\cap A_{2}$. As $Y$ is Hausdorff, $A_{1},A_{2}$ are closed and $\{ (X \backslash A_{1})\cup U_{i} \}_{i\in I}$ is an open cover of $A_{2}$ as: $$A_{2}\subseteq (X \backslash A_{1})\cup (A_{1}\cap A_{2})\subseteq \bigcup_{i\in I}^{}(X \backslash A_{1})\cup U_{i}$$Therefore, there exists $J\subseteq I$ s.t. $A_{2}\subseteq \bigcup_{i\in J}(X \backslash A_{1})\cup U_{i}$. It follows that $A_{1}\cap A_{2}\subseteq \bigcup_{i\in J}^{}U_{i}$. 
>6. It suffices to show that $f$ is closed. For a closed set $A\subseteq X$, $A$ is compact, $f(A)$ is compact, hence closed. 
- **Remark**: 3 does not hold without Hausdorff condition as any infinite set with cofinite topology has only compact subsets. (cf Example 4)
---
> [!lemma] Theorem 2 (Equivalence of Compactness)
> For a topological space $X$, the following are equivalent:
> 1. $X$ is compact.
> 2. Every collection of closed sets in $X$ with the finite intersection property has a non-empty intersection.
> 3. Every [[Ultrafilter]] $\mathcal{F}$ on $X$ converges.
> 4. for any family $(U_{x})_{x\in X}$ of open sets s.t. $U_{x}$ is an open neighborhood of $x$ for all $x\in X$, there exists a finite subset $S\subseteq X$ such that: $X=\bigcup_{x\in S}^{}U_{x}$.

> [!proof]-
> - (1 <=> 2): Let $(C_{i})_{i}$ be a collection of closed sets. It suffices to show that if $\bigcap_{i\in I}^{}C_{i}=\varnothing$, then it holds for some finite subset. Indeed, $(U_{i})_{i}$ is an open covering of $X$ and there exists finite $J\subseteq I$ s.t. $(U_{i})_{i\in J}$ covers $X$. Then, we have that $$\bigcap_{i\in J}^{}C_{j}=X \backslash \bigcup_{i\in J}^{}U_{j}=\varnothing$$This shows the statement.
> - (1<=>3): By [[Ultrafilter|Proposition 2]].
> - (1=>4): assume that $X$ is compact. Then, $(U_{x})_{x}$ is an open covering of $X$ and the property holds by assumption. 
> - (4=>1): assume that the property holds and let $(U_{i})_{i\in I}$ be an arbitrary open cover of $X$. For each $x\in X$, let $V_{x}$ be the open set in $(U_{i})_{i}$ s.t. $x\in V_{x}$, where such open set exists as $(U_{i})_{i}$ is an open cover of $X$. Then, $(V_{x})_{x\in X}\subseteq (U_{i})_{i\in I}$ and there exists a finite subset $S\subseteq X$ s.t. $X=\bigcup_{x\in S}^{}V_{x}$. Therefore, $(V_{x})_{x\in S}$ is a finite sub-cover of $X$ of our original open cover. 

---
> [!lemma] Lemma 3
> Let $X$ be compact space and $Y$ a metric space. 
> 1. If $f:X\to Y$ is locally bounded, then $f$ is bounded on $X$. 

> [!proof]-
> Let $U_{x}$ be the open neighborhood of $x$ s.t. $f|_{U_{x}}\subseteq B_{<r_{x}}(0)$ for $x\in X$. Then, $\{ U_{x} \}_{x\in X}$ is an open cover of $X$. Then, there exists finite $J\subseteq X$ s.t. $\bigcup_{x\in J}^{}U_{x}=X$. Therefore, $$f(X)\subseteq B_{<\max_{x\in J} r_{x}}(0)$$
---
> [!lemma] Theorem 4 (Tychonoff)
> For any arbitrary family of compact spaces $\{ X_{i} \}_{i\in I}$, $X:=\prod_{i\in I}^{}X_{i}$ is compact with respect to the [[Product Topology]].

^be969b

> [!proof]-
> Let $\mathcal{F}$ be an ultrafilter on $X$. As $(p_{i})_{*}(\mathcal{F})$ is an ultrafilter on $X_{i}$ by [[Ultrafilter|Lemma 5]] and $X_{i}$ is compact, by [[Ultrafilter|Proposition 2]], $(p_{i})_{*}(\mathcal{F})$ converges for all $i\in I$. By [[Filter|Lemma 5]], $\mathcal{F}$ converges. 
> 
> Therefore, using Proposition 2 again, this means that $X$ is compact.

^478057

- **Remark**: This is equivalent to [[Axiom of Choice]].
---
###### Compact Hausdorff Space
![[Continuous Function#^8efffd]]

---
![[Continuous Function#^e5bbc4]]
![[Continuous Function#^aa3f39|p]]

---
> [!lemma] Lemma 1
> Let $X$ be a compact Hausdorff space. Let $A\subseteq X$ be a closed subspace and $x\notin A$. Then, 
> 1. there exists an open neighborhood $U\ni x$ s.t. $\overline{U}\cap A=\varnothing$.

> [!proof]-
> Let $y\in A$. Then, $x\neq y$ and as $X$ is Hausdorff, there exists disjoint open neighborhoods $U_{y},V_{y}$ of $x$ and $y$ respectively. As $A$ is a closed subspace, $A$ is compact and $\{ V_{y} \}_{y\in A}$ is an open cover of $A$. Therefore, there exists a finite set $J\subseteq A$ s.t. $\bigcup_{y\in J}^{}V_{y}\supseteq A$. Let $U:=\bigcap_{y\in J}^{}U_{y}$ which is an open neighborhood of $x$. Then, we have that $U\cap \bigcup_{y\in J}^{}V_{j}=\varnothing$ and as both sets are open, $\overline{U}\cap A \subseteq \overline{U}\cap \bigcup_{y\in J}^{}V_{j}=\varnothing$. 
---
> [!lemma] Theorem (Baire Category Theorem for Compact Hausdorff Spaces)
> Let $X$ be a compact Hausdorff space. 
> 1. For a sequence $(C_{n})_{n}$ of closed sets s.t. $C_{n}^\circ=\varnothing$, it holds that $\left( \bigcup_{n\geq 1}^{}C_{n} \right)^\circ=\varnothing$.
> 2. For a sequence $(U_{n})_{n}$ of dense open sets, it holds that $\bigcap_{n\geq 1}^{}U_{n}$ is dense in $X$.

> [!proof]-
> We have:
> 1. Denote $C:=\bigcup_{n\geq 1}^{}C_{n}$. Let $U_{0}$ be a non-empty open subset of $X$. By induction we will construct a sequence $(U_{n})_{n\geq 1}$ of non-empty open sets. Let $n\geq 1$. As $C_{n}$ has an empty interior, there exists $x_{n}\in U_{n-1} \backslash C_{n}$. Then, $x_{n}\notin C_{n}\cup \partial U_{n-1}$ which is a closed set, hence compact Hausdorff. Therefore, by Lemma 1, there exists a neighborhood $U_{n}$ of $x$ s.t. $\overline{U_{n}}\cap (C_{n}\cup \partial U_{n-1})=\varnothing$. As $x_{n}\in U_{n-1}$, we have that:
> 	1. $\overline{U_{n}}\cap C_{n}=\varnothing$ and
> 	2. $\overline{U}_{n}\subseteq U_{n-1}$.
> 
> 	Then, as they are decreasing and non-empty, $(\overline{U}_{n})_{n}$ has the finite intersection property. Hence, by Theorem 2.2, $\bigcap_{n\geq 1}^{}\overline{U}_{n}\neq \varnothing$. Furthermore, $$U_{0}\cap(X \backslash C)=U_{0}\cap \bigcap_{n\geq 1}^{}(X \backslash C_{n})\supseteq\bigcap_{n\geq 1}^{}\overline{U}_{n}\neq \varnothing$$Hence, we have that for any non-empty open set $U_{0}$, $U_{0}\not\subseteq C$. Therefore, $C^\circ=\varnothing$.
> 2. Let $C_{n}:=X \backslash U_{n}$. Then, $C_{n}$ is closed and $C_{n}^\circ=(X \backslash U_{n})^{\circ}=X\backslash X=\varnothing$. Therefore, the interior of $C:=\bigcup_{n\geq 1}C_{n}$ is empty and: $$\overline{\bigcap_{n\geq 1}U_{n}}=\overline{X\backslash C}=X \backslash C^\circ =X$$

---
> [!lemma] Proposition 2
> Let $X$ be a compact Hausdorff space. Then, 
> 1. every $x\in X$ has a closed [[Local Base of Topology|local base]] in $X$.
> 2. for $Y\subseteq X$ open, $Y$ is [[Locally Compact Hausdorff Space|locally compact Hausdorff]].

> [!proof]+
> We have:
> 1. Let $x\in X$ and $U$ an open neighborhood of $x$. Let $C:=X\backslash U$. As $C$ is closed and $x\notin C$, there exists by Lemma 1 an open neighborhood $V$ of $x$ s.t. $\overline{V}\cap C=\varnothing$. Therefore, $\overline{V}\subseteq U$. 
> 2. for any $x\in Y$, as $Y$ is open, there exists a closed neighborhood $V$ of $x$ in $Y$. Then, $V$ is a compact neighborhood in $X$ and therefore compact in $Y$. Hence, any $x\in Y$ has a compact neighborhood and $Y$ is locally compact Hausdorff.

---
###### Compact Metric Spaces
> [!lemma] Theorem 1 (Equivalence of Compactness)
> For a metric space $(X,d)$, the following are equivalent:
> 1. $X$ is compact.
> 2. If $F_{1}\supseteq F_2\supseteq\dots$ is a decreasing sequence of non-empty closed sets in $X$, $\bigcap_{n=1}^{\infty}F_{n}\neq \varnothing$.
> 4. $X$ is sequentially compact.
> 5. $X$ is totally bounded and complete.

> [!proof]-
> - (1 => 2): A decreasing sequence  $(F_{i})_{i=1}^\infty$ has the finite intersection property. Therefore, holds by Theorem 2.
> - (2 => 3): Let $(x_{n})_{n=1}^\infty \subseteq X$. We then define, $$F_{n}:=\overline{\{ x_{n},x_{n+1},\dots \}}$$Then, $F_{1}\supseteq F_{2}\supseteq F_{3}\supseteq \dots$ are decreasing, non-empty and closed. Therefore, there exists $a\in X$ s.t. $a\in \bigcap_{n=1}^{\infty}F_{n}$. By [[Interior and Closure|Proposition 2]], it follows that there exists a subsequence converging to $a$.
> - (3 => 4): We first show that $X$ is complete. Let $(x_{n})\subseteq X$ be any Cauchy sequence. Then, $(x_{n})_{n}$ has a convergent subsequence converging to $a$. This however, means that the whole sequence converges to $a$. Therefore, $X$ is complete.
>   
>   Suppose $X$ is not totally bounded, i.e. there exists $r>0$ s.t. $X$ has no finite covering of open balls of radius $r$. Then, we can define a sequence $(x_{n})_{n}$ s.t. $d(x_{i},x_{j})\geq r$ for all $i\neq j$. Then, $(x_{n})_{n}$ has no convergent subsequence as if it had convergent subsequence $(x_{n_{k}})_{k}$ to $a$, it would have $k_{0}$ s.t. $d(x_{n_{k}},a)<r/2$ for all $k\geq k_{0}$ and by triangle identity, $$d(x_{n_{k}},x_{n_{k'}})<r$$ for all $k,k'\geq k_{0}$. However, this is a contradiction.
>   
>  - (4 => 1): Assume that $X$ is totally bounded and complete. Suppose $X$ is not compact, i.e. there exists an open covering $\{ U_{i} \}_{i}$ of $X$ s.t. there is no finite sub-covering. 
>    
>    Now, as $X$ is totally bounded, there is an $\varepsilon$-net $A_{\varepsilon}$ for all $\varepsilon>0$. Let $x_{1}\in A_{1 / 2}$ s.t. no finite sub-family of $(U_{i})_{i}$ is covering $B(x_{1}, 1/2)$. This has to exist as there is no finite sub-covering of $(U_{i})$. Then, let $x_{2}\in A_{1 /4}$ s.t. $B(x_{1},1 /2 )\cap B(x_{2}, 1/ 4)\neq\varnothing$ and there is no finite subcovering of $(U_{i})$. Continue analogously. Then, $$d(x_{n-1},x_{n})< \frac{1}{2^{n-1}}+\frac{1}{2^n}\leq \frac{1}{2^{n-2}}$$and for $m<n$: $$d(x_{m},x_{n})\leq \sum_{i=m}^{n-1}d(x_{i},x_{i+1})=\sum_{i=m}^{n-1} \frac{1}{2^{i-1}}\leq \frac{1}{2^{m-2}}$$which shows that $(x_{n})$ is a Cauchy sequence, i.e. it converges to a point $a$ as $X$ is complete. 
>    
>    Let $U_{k}$ be s.t. $a\in U_{k}$. Then, there exists $\varepsilon>0$ s.t. $B(a,\varepsilon)\subseteq U_{k}$. Then, by definition, there exists $x_{n}$ s.t. $d(x_{n},a)<\varepsilon / 2$ and also $1/2^n < \varepsilon/2$. It follows from the triangle inequality that: $$B(x_{n}, 1 / 2^n)\subseteq B(a, \varepsilon)\subseteq U_{k}$$ which is a contradiction.
---
> [!lemma] Proposition 2
> Every totally bounded metric space is [[Separable Space|separable]].

^4ba38b

> [!proof]-
> If $X$ is totally bounded, then there exists for each $n$ a finite subset $A_{n}\subseteq X$ s.t. for every $x\in X$: $d(x,A_{n})\leq 1/n$. If we let $A:= \bigcup_{n=1}^{\infty}A_{n}$, then $A$ is countable and for each $x\in X$, we have: $$d(x,A)\leq d(x,A_{n})\leq 1 / n$$ for all $n$. Therefore, $d(x,A)=0$ and $x\in  \overline{A}$. This shows that $A$ is dense in $X$.
---
> [!lemma] Theorem 3 (Lebesgue Covering Lemma)
> Let $X$ be a compact metric space and $\mathcal{U}:=\{ U_{\alpha} \}_{\alpha\in I}$ be an open cover. Then, there exists $\delta>0$ s.t. for every subset $S\subseteq X$ with $\text{diam}(S)<\delta$ there exists $\alpha\in I$ with $S\subseteq U_{\alpha}$.

 > [!proof]-
 > As $X$ is compact, there exists a finite subcover $\{ A_{1},..,A_{n} \}\subseteq \mathcal{U}$. If any of the $A_{i}$'s is equal to $X$, then the statement trivially holds. Otherwise, let $C_{i}:=X \backslash A_{i}$. As $C_{i}$ is not empty, we have a function $$f:X\to \mathbb{R},\quad x\mapsto \frac{1}{n}\sum_{i=1}^{n}d(x,C_{i})$$Since $f$ is continuous on a compact set, it attains a minimum $\delta>0$ as every $x$ is contained in some $A_{i}$. Let $S\subseteq X$ with $\text{diam}(S)<\delta$ and $x_{0}\in S$. Then, $S\subseteq B_{< \delta}(x_{0})$. 
 > 
 > Since $f(x_{0})\geq\delta$, there must exists at least one $i$ s.t. $d(x_{0},C_{i})\geq \delta$. However, this means that $S\subseteq B_{<\delta}(x_{0})\subseteq X \backslash C_{i}=A_{i}$.
---
##### Examples
> [!h] Example 1 (Discrete Space)
> A discrete space $X$ is compact if and only if $X$ is finite.

> [!proof]-
> If $X$ is finite and discrete, there are only finitely many open sets, so $X$ is compact. Conversely, if $X$ is infinite, $(\{ x \})_{x\in X}$ has no finite subcovers.
---
> [!h] Example 2 (Converging Sequence)
> Let $X$ be a topological space and $(x_{n})_{n}\subseteq X$ with $x_{n}\to y\in X$. Then, $$A:=\{ x_{n} \}_{n}\cup \{ y \}\subseteq X$$is compact.

> [!proof]-
> Let $A\subseteq \bigcup_{{\lambda\in \Lambda}}^{}U_{\lambda}$ where $U_{\lambda}$ is open in $X$.  Then, there is $\lambda_{0}\in \Lambda$ s.t. $y\in U_{\lambda_{0}}$. Therefore, there exists $N\in \mathbb{N}$ s.t. $x_{n}\in U_{\lambda_{0}}$ for $n\geq N$. Further, for $n\in [N-1]$, let $U_{\lambda_{n}}$ s.t. $x_{n}\in U_{\lambda_{n}}$. Then, $$A\subseteq \bigcup_{0\leq n <N}^{}U_{\lambda_{n}}$$
---
> [!h] Example 3 (Heine-Borel)
> Let $A\subseteq \mathbb{R}^n$ for $n\geq 0$. Then, the following are equivalent:
> 1. $A$ is compact.
> 2. $A$ is closed and bounded.

> [!proof]-
> We have that:
> 1. if $A$ is compact, $A$ is closed as $\mathbb{R^n}$ is Hausdorff. By Lemma 2 and the locally bounded map $$\begin{array}{cccc} {}&{A}&\to&{\mathbb{R}^n}\\&{x} &\mapsto & {x } \end{array}{}$$$A$ is bounded in $X$. 
> 2. Let $(x_{n})\subseteq A$. As $A$ is bounded, the sequence is bounded and by Bolzano-Weierstrass there exists a convergent subsequence. However, as $A$ is closed, the subsequence must converge in $A$. Therefore, any sequence in $A$ has a convergent subsequence in $A$ and $A$ is sequentially compact. As $A$ is metric, by Compact Metric Space Theorem 1 $A$ is compact.
---
> [!h] Example 4 (Cofinite Topology)
> Let $X$ be an infinite set equipped with the cofinite topology. Then, 
> 1. every subset $E\subseteq X$ is compact.

> [!proof]-
> Let $(U_{\alpha})_{\alpha}$ be an open covering of $E$. For fixed $\alpha_{0}$, $U_{\alpha_{0}}$ contains all but finitely many points of $E$. Therefore, there exist $U_{\alpha_{1}},\dots,U_{\alpha_{n}}$ that cover the finite points. 
---
> [!h] Example 5 (Product Metric Space)
> Let $(X_{n},d_{n})_{n\geq 1}$ be a sequence of compact metric spaces. Denote $X:=\prod_{n\geq 1}^{}X_{n}$. Then,
> 1. $X$ is compact metric.

> [!proof]-
> By [[Metric Space|Example 4]] we know that $X$ is metric. We will show that $X$ is sequentially compact. Let $(x_{m})_{m}\subseteq X$ be a sequence.  
> 
---
###### Non-Example
> [!h] Non-Example 1
> The unit ball in $L^2([0,1])$ is not compact.
---
