#Definition #FunctionalAnalysis 

> [!definition]
> A [[Metric Space|metric space]] $(X,d)$ is ***compact***, if every open covering has a finite sub-covering. 
> 
> More formally, if $(U_{i})_{i\in I}$ is a collection of open sets  of $X$ s.t. $\bigcup_{i\in I}^{}U_{i}=X$, then there exists a finite subset $J \subseteq I$ s.t. $$\bigcup_{i\in J}^{}U_{i}=X$$
- **Related Definition**:  A metric space $(X,d)$ is ***sequentially compact*** if every sequence $(x_{n})_{n=1}^\infty \subseteq X$ has a convergent subsequence.
- **Related Definition**:  A metric space $(X,d)$ is ***totally bounded/pre-compact*** if for every $\varepsilon>0$, there exists finite $J$ s.t. $\bigcup_{i\in J}^{}B(x_{i},\varepsilon)=X$. In other words, for every $\varepsilon>0$, there exists finite $A\subseteq X$ s.t. $d(x,A)<\varepsilon$ for all $x\in X$. Then, $A$ is called ***$\varepsilon$-net***.
---
##### Properties
> [!lemma] Proposition 1
> A metric space $(X,d)$ is compact if and only if for every closed collection $\mathcal{F}=(C_{i})_{i\in I}\subseteq \mathcal{P}(X)$,  $$\bigcap_{i\in J}^{}C_{i}\neq \varnothing\quad \forall \text{finite}J\subseteq I \implies \bigcap_{i\in I}^{}C_{i}\neq \varnothing$$

> [!proof]-
> The condition can be also written as:
> $$\bigcap_{i\in I}^{}C_{i}= \varnothing\implies\bigcap_{i\in J}^{}C_{i}= \varnothing\quad \forall \text{finite }J\subseteq I$$
> Let $(U_{i})_{i\in I}$ is an open covering of $X$. Then, take $C_{i}:= U_{i}^c$. Then, $$\bigcap_{i\in I}^{}U^c_{i}=X^c=\varnothing$$and for every finite $J\subseteq I$, $\bigcup_{i\in J}^{}U_{i}=X$. 
---
> [!lemma] Theorem 2
> For a metric space $(X,d)$, the following are equivalent:
> 1. $X$ is compact.
> 2. Every collection of closed sets in $X$ with the finite intersection property (Proposition 1) has a non-empty intersection.
> 3. If $F_{1}\supseteq F_2\supseteq\dots$ is a decreasing sequence of non-empty closed sets in $X$, $\bigcap_{n=1}^{\infty}F_{n}\neq \varnothing$.
> 4. $X$ is sequentially compact.
> 5. $X$ is totally bounded and complete.

> [!proof]-
> - (1 => 2): Proposition 1
> - (2 => 3): A decreasing sequence  $(F_{i})_{i=1}^\infty$ has the finite intersection property.
> - (3 => 4): Let $(x_{n})_{n=1}^\infty \subseteq X$. We then define, $$F_{n}:=\overline{\{ x_{n},x_{n+1},\dots \}}$$Then, $F_{1}\supseteq F_{2}\supseteq F_{3}\supseteq \dots$ are decreasing, non-empty and closed. Therefore, there exists $a\in X$ s.t. $a\in \bigcap_{n=1}^{\infty}F_{n}$. It follows that there exists a subsequence converging to $a$.
> - (4 => 5): We first show that $X$ is complete. Let $(x_{n})\subseteq X$ be any Cauchy sequence. Then, $(x_{n})_{n}$ has a convergent subsequence converging to $a$. This however, means that the whole sequence converges to $a$. Therefore, $X$ is complete.
>   
>   Suppose $X$ is not totally bounded, i.e. there exists $r>0$ s.t. $X$ has no finite covering of open balls of radius $r$. Then, we can define a sequence $(x_{n})_{n}$ s.t. $d(x_{i},x_{j})\geq r$ for all $i\neq j$. Then, $(x_{n})_{n}$ has no convergent subsequence as if it had convergent subsequence $(x_{n_{k}})_{k}$ to $a$, it would have $k_{0}$ s.t. $d(x_{n_{k}},a)<r/2$ for all $k\geq k_{0}$ and by triangle identity, $$d(x_{n_{k}},x_{n_{k'}})<r$$ for all $k,k'\geq k_{0}$. However, this is a contradiction.
>   
>  - (5 => 1): Assume that $X$ is totally bounded and complete. Suppose $X$ is not compact, i.e. there exists an open covering $\{ U_{i} \}_{i}$ of $X$ s.t. there is no finite sub-covering. 
>    
>    Now, as $X$ is totally bounded, there is an $\varepsilon$-net $A_{\varepsilon}$ for all $\varepsilon>0$. Let $x_{1}\in A_{1 / 2}$ s.t. no finite sub-family of $(U_{i})_{i}$ is covering $B(x_{1}, 1/2)$. This has to exist as there is no finite sub-covering of $(U_{i})$. Then, let $x_{2}\in A_{1 /4}$ s.t. $B(x_{1},1 /2 )\cap B(x_{2}, 1/ 4)\neq\varnothing$ and there is no finite subcovering of $(U_{i})$. Continue analogously. Then, $$d(x_{n-1},x_{n})< \frac{1}{2^{n-1}}+\frac{1}{2^n}\leq \frac{1}{2^{n-2}}$$and for $m<n$: $$d(x_{m},x_{n})\leq \sum_{i=m}^{n-1}d(x_{i},x_{i+1})=\sum_{i=m}^{n-1} \frac{1}{2^{i-1}}\leq \frac{1}{2^{m-2}}$$which shows that $(x_{n})$ is a Cauchy sequence, i.e. it converges to a point $a$ as $X$ is complete. 
>    
>    Let $U_{k}$ be s.t. $a\in U_{k}$. Then, there exists $\varepsilon>0$ s.t. $B(a,\varepsilon)\subseteq U_{k}$. Then, by definition, there exists $x_{n}$ s.t. $d(x_{n},a)<\varepsilon / 2$ and also $1/2^n < \varepsilon/2$. It follows from the triangle inequality that: $$B(x_{n}, 1 / 2^n)\subseteq B(a, \varepsilon)\subseteq U_{k}$$ which is a contradiction.
---
> [!lemma] Proposition 3
> Every totally bounded metric space is separable.

> [!proof]-
> If $X$ is totally bounded, then there exists for each $n$ a finite subset $A_{n}\subseteq X$ s.t. for every $x\in X$: $d(x,A_{n})\leq 1/n$. If we let $A:= \bigcup_{n=1}^{\infty}A_{n}$, then $A$ is countable and for each $x\in X$, we have: $$d(x,A)\leq d(x,A_{n})\leq 1 / n$$ for all $n$. Therefore, $d(x,A)=0$ and $x\in  \overline{A}$. This shows that $A$ is dense in $X$.
---