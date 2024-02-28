#Definition #Topology 

> [!definition]
> A [[metric space]] $(X,d)$ is ***complete***, if every [[Cauchy Sequence|Cauchy sequence]] of points in $X$ has a limit that is also in $X$.
- **Equivalent definition**: $X$ is complete if for any $\{ F_{n} \}_{n}$ closed subsets with $F_{n+1}\subseteq F_{n}$ and $\text{diam}(F_{n})\to{0}$, $\bigcap_{n=1}^{\infty}F_{n}\neq \varnothing$.
---
##### Properties
> [!lemma] Theorem 1 (Baire Category Theorem)
> Let $(X,d)$ be a complete metric space with $X \neq \varnothing$. Further, let non-empty $Y\subseteq X$ be open.
> 1. let $(U_{j})_{j}$ be a sequence of open and dense sets $U_{j}\subseteq Y$, then $\mathcal{U}:=\bigcap_{j\geq 1}^{}U_{j}$ is dense in $Y$.
> 2. let $(F_{j})_{j}$ be a sequence of closed sets $F_{j}\subseteq X$ with $\left( \bigcup_{j\geq 1}^{}F_{j} \right)^\circ\neq \varnothing$, then $F_{j}^\circ\neq \varnothing$ for some $j\geq 1$.
> 3. let $Y=\bigcup_{j\geq 1}^{}F_{j}$ with $F_{j}$ closed in $Y$, then there exists $j\geq 1$ s.t. $F_{j}^\circ\neq \varnothing$ in $Y$.

> [!proof]-
> We show that:
> 1. We first show the statement for $Y = X$. Especially, we will show that for any $x\in X$ and $r>0$, $B_{<r}(x)\cap \mathcal{U}\neq \varnothing$. 
>    1. **Constructing the Cauchy sequence $(x_{k})_{k}$**
>    We will construct a sequence $(x_{k},r_{k})_{k}$ as follows. 
> 	   - $x_{1}\in B_{<r}(x)\cap U_{1}$ and $r_{1}<2^{-1}$ s.t. $B_{<2r_{1}}(x_{1})\subseteq B_{<r}(x)\cap U_{1}$ (as it is open)
> 	   - $x_{2}\in B_{<r_{1}}(x_{1})\cap U_{2}$ and $r_{2}<2^{-2}$ s.t. $B_{<2r_{2}}(x_{2})\subseteq B_{<r_{1}}(x_{1})\cap U_{2}$
> 	     
> 	   Then, we iteratively define a decreasing sequence of closed balls $(B_{\leq r_{k}}(x_{k}))_{k}$ where:
> 	$$B_{\leq r_{k}}(x_{k})\subseteq B_{<2r_{k}}(x_{k})\subseteq B_{<r}(x)\cap\bigcap_{i=1}^{k}U_{1}$$and $0<r_{k}< 2^{-k}$. Further, for all $\ell>k\geq 1$, $d(x_{\ell},x_{k})\leq r_{k}<2^{-k}$. It follows that $(x_{k})_{k}$ is a Cauchy sequence.
> 	
> 	2. **Showing the limit meets the properties**:
> 	    Since $X$ is complete, there exists  $y=\lim_{ n \to \infty }x_{n}\in X$. We further observe that for all $n\geq 1$, $(x_{k})_{k\geq n}\subseteq B_{\leq r_{n}}(x_{n})$. Therefore, $y\in B_{\leq r_{n}}(x_{n})$. It follows that $$y\in \bigcap_{n=1}^{\infty}\overline{B}_{\leq r_{n}}(x_{n})\subseteq B(x,r)\cap \bigcap_{n= 1}^{\infty}U_{n}$$This proves the statement.
> 	3. **Showing for general open subset $Y\subseteq X$**:
> 	   Now, let $Y\subseteq X$ be any open set. Then, $U_{j}$ is also open in $X$ for all $j\geq 1$ and $U_{j}$ is also dense in $\overline{Y}$. We define $V:= X \backslash \overline{Y}$ and $(U_{j}\cup V)_{j}$ is a sequence of open, dense sets in $X$. Therefore, $V \cup \bigcap_{j\geq 1}^{}U_{j}$ is a dense set in $X$. Now, for any non-empty open set $W$ in $Y$, $$W\cap \left[  V \cup \bigcap_{j\geq 1}^{}U_{j}\right]\neq \varnothing$$
> 	As $W \cap V=\varnothing$, we get that $W\cap \bigcap_{j\geq 1}^{}U_{j}\neq \varnothing$, which proves that $\bigcap_{j\geq 1}^{}U_{j}$ is dense.
> 2. Let $Y := \left( \bigcup_{j\geq 1}^{}F_{j} \right)^\circ$. Then, $F_{j}\cap Y$ is closed in $Y$ for $j\geq 1$ and $Y = \bigcup_{j\geq 1}^{}F_{j}\cap Y$. Therefore, there exists $j_{0}$ s.t. there exists $W\subseteq F_{j_{0}}\cap Y$, which is open in $Y$. Therefore, $W$ is open in $X$ and $W\subseteq F_{j_{0}}$. This proves the statement.
> 3. Assume for all $j\geq 1$ that $F_{j}^\circ=\varnothing$. Then, by [[Dense Subset|Lemma 2]], $U_{j}:= Y \backslash F_{j}$ are open and dense. Therefore, from 1, $\bigcap_{j\geq 1}^{}U_{j}$ is dense in $Y$. However,
> 	$$\bigcap_{j\geq 1}^{}U_{j}=\bigcap_{j\geq 1}^{}(Y \backslash F_{j})=Y \backslash \bigcup_{j\geq 1}^{}F_{j}=Y \backslash Y=\varnothing$$However, as $Y \neq \varnothing$, we have a contradiction.
- **Corollary**: A complete non-empty metric space $X$ is [[Meager Set|non-meager]], as is any of its non-empty open subsets.
- **Corollary**: A [[Meager Set|generic]] subset of a complete metric space $X$ is [[Dense Subset|dense]]. This holds for any of its non-empty open subsets.
---
> [!lemma] Theorem 2
> Let $(X,d)$ be a complete metric space and $f_{n}: X\to \mathbb{C}$ continuous functions s.t. $$f(x):=\lim_{ n \to \infty } f_{n}(x)$$for all $x\in X$. Then, $\{ x\in X:f\text{ is continuous at }x \}$ is [[Meager Set|generic]].

> [!proof]-
> Stein-Shakarshi 4.1.1

---
> [!lemma] Proposition 3 (Principle of Uniform Boundedness)
> Let $(X,d)$ be a complete metric space and $f_{\lambda}:X \to \mathbb{C}$ be continuous functions for $\lambda\in \Lambda$ s.t. $$\sup_{\lambda\in \Lambda}\left| f_{\lambda}(x) \right| <+\infty$$for all $x\in X$. Then, there exists $r>0$ and $y\in X$ s.t. $$\sup_{\lambda\in \Lambda}\sup_{x\in B(y,r)}\left| f_{\lambda}(x) \right| <+\infty$$

> [!proof]-
> For every $n\geq 1$, let $$A_{n}:=\{ x\in X:\sup_{\lambda\in \Lambda}\left| f_{\lambda}(x) \right| \leq n \}=\bigcap_{\lambda\in \Lambda}^{}\{ x\in X:\left| f_{\lambda}(x) \right| \leq n \}$$which is closed. Then, by Baire Category Theorem 3, there exists $n_{0}\geq 1$ s.t. $$A_{n_{0}}^\circ \neq \varnothing$$Let $y\in A^\circ_{n_{0}}$ and $r>0$ with $B_{<r}(y)\subseteq A_{n_{0}}$.