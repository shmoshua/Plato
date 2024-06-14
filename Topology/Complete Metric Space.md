#Definition #Topology 

> [!definition]
> A [[metric space]] $(X,d)$ is ***complete***, if every [[Cauchy Sequence|Cauchy sequence]] of points in $X$ has a limit that is also in $X$.
- **Equivalent definition**: $X$ is complete if for any $\{ F_{n} \}_{n}$ closed subsets with $F_{n+1}\subseteq F_{n}$ and $\text{diam}(F_{n})\to{0}$, $\bigcap_{n=1}^{\infty}F_{n}\neq \varnothing$.
---
##### Properties
> [!lemma] Theorem 1 (Baire Category Theorem)
> Let $(X,d)$ be a non-empty complete metric space. 
> 1. For a sequence $(C_{n})_{n}$ of close sets s.t. $C_{n}^\circ=\varnothing$, it holds that $\left( \bigcup_{n\geq 1}^{}C_{n} \right)^\circ=\varnothing$.
> 2. For a sequence $(U_{n})_{n}$ of open dense sets, $\bigcap_{n\geq 1}^{}U_{n}\subseteq X$ is dense.
> 3. Let $Y\subseteq X$ non-empty open. For $(U_{n})_{n}$ of open dense sets $U_{n}\subseteq Y$, $\bigcap_{n\geq 1}^{}U_{n}\subseteq Y$ is dense.
> 5. Let  $Y\subseteq X$ non-empty open. If $Y=\bigcup_{n\geq 1}^{}C_{n}$ with $C_{n}$ closed in $Y$, then there exists $n\geq 1$ s.t. $C_{n}^\circ\neq \varnothing$ in $Y$.

> [!proof]-
> We have:
> 1. Let $U_{0}$ be a non-empty open subset of $X$. We will construct a sequence $(U_{n})_{n\geq 1}$ of non-empty open sets as follows: For $n\geq 1$, as $C_{n}$ has an empty interior, there exists $x_{n}\in U_{n-1} \backslash C_{n}$. Then, $x_{n}\notin C_{n} \cup X\backslash U_{n-1}$ which is a closed set. As metric spaces are [[Normal Space|normal]], there exists $V_{n}\ni x_{n}$ open s.t. $\overline{V_{n}}\cap(C_{n}\cup X \backslash U_{n-1})=\varnothing$. Let $U_{n}:= V_{n}\cap B_{< \frac{1}{2n}}(x_{n})$. Then,
> 	- $\overline{U_{n}}\cap C_{n}=\varnothing$.
> 	- $\overline{U_{n}}\subseteq U_{n-1}$
> 	- for all $x,y\in U_{n}$, $d(x,y)\leq d(x,x_{n})+d(x_{n},y)< \frac{1}{n}$.
> 	
> 	Then, $(\overline{U_{n}})_{n}$ is a decreasing sequence of non-empty closed sets with $$\lim_{ n \to \infty }\text{diam}(\overline{U}_{n})=\lim_{ n \to \infty } \frac{1}{n}=0$$Therefore, $\bigcap_{n\geq 1}^{}\overline{U_{n}}\neq \varnothing$. Let  $x\in \bigcap_{n\geq 1}^{}\overline{U_{n}}$. Then, $x\notin C_{n}$ for all $n$ and $x\notin C:=\bigcup_{n\geq 1}^{}C_{n}$. However, $x\in\overline{U}_{1}\subseteq U_{0}$. Therefore, $x\in U_{0}\cap(X \backslash C)$. This shows that $X\backslash C$ is dense in $X$, i.e. $C$ has an empty interior. 
> 2. Take $C_{n}:= X \backslash U_{n}$. Then, $C_{n}^\circ=X \backslash \overline{U_{n}}=\varnothing$ and: $$\overline{\bigcap_{n\geq 1}U_{n}}=\overline{\bigcap_{n\geq 1}X \backslash C_{n}}=\overline{X \backslash \bigcup_{n\geq 1}C_{n}}=X \backslash C^\circ =X$$
> 3. Now, let $Y\subseteq X$ be any open set. Then, $U_{n}$ is also open in $X$ for all $n\geq 1$ and $U_{n}$ is also dense in $\overline{Y}$. We define $V:= X \backslash \overline{Y}$ and $(U_{n}\cup V)_{n}$ is a sequence of open, dense sets in $X$. Therefore, $V \cup \bigcap_{n\geq 1}^{}U_{n}$ is a dense set in $X$. 
>    
>    Now, for any non-empty open set $W$ in $Y$, $$W\cap \left[  V \cup \bigcap_{n\geq 1}^{}U_{n}\right]\neq \varnothing$$
> 	As $W \cap V=\varnothing$, we get that $W\cap \bigcap_{n\geq 1}^{}U_{n}\neq \varnothing$, which proves that $\bigcap_{n\geq 1}^{}U_{n}$ is dense in $Y$.
> 4. Assume for all $n\geq 1$ that $C_{n}^\circ=\varnothing$ in $Y$. Then, $U_{n}:= Y \backslash C_{n}$ is open and dense in $Y$. Therefore, from 3, $\bigcap_{n\geq 1}^{}U_{n}$ is dense in $Y$. Then,
> 	$$\bigcap_{n\geq 1}^{}U_{n}=\bigcap_{n\geq 1}^{}(Y \backslash C_{n})=Y \backslash \bigcup_{n\geq 1}^{}C_{n }=Y \backslash Y=\varnothing$$However, as $Y \neq \varnothing$, we have a contradiction.

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
---
> [!lemma] Theorem 4 (Fixed Point Theorem)
> Let $X$ be a non-empty complete metric space and let $f:X\to X$ be a continuous map such that $d(f(x),f(y))\leq\alpha d(x,y)$ for all $x,y\in X$ for some constant $\alpha<1$.
> 1. for any $x_{0}\in X$, the sequence $(x_{n})_{n}$ s.t. $x_{n+1}=f(x_{n})$ converges to $y\in X$ where  $f(y)=y$.
> 2. there exists a unique element $y\in X$ such that $f(y)=y$.

> [!proof]-
> We have that: 
> 1. we claim that $(x_{n})_{n}$ is Cauchy. As $d(x_{n},x_{n+1})\leq\alpha d(x_{n-1},x_{n})\leq\alpha^nd(x_{0},x_{1})$, for $\varepsilon>0$, there exists $N\geq 1$ s.t. $d(x_{N},x_{N+1})<\varepsilon$.  Then, for all $n\geq N$, $$d(x_{N},x_{n})\leq\left( \sum_{i=1}^{n-N}\alpha^{i-1} \right)d(x_{N},x_{N+1})=\frac{(1-\alpha)^{n-N}}{1-\alpha}d(x_{N},x_{N+1})<d(x_{N},x_{N+1})<\varepsilon$$Therefore, $(x_{n})_{n}\to y\in X$. Then, $f(y)=f(\lim_{ n \to \infty }x_{n})=\lim_{ n \to \infty }f(x_{n})=\lim_{ n \to \infty }x_{n+1}=y$.
> 2. Assume that there exists $y\neq z\in X$ s.t. $f(y)=y$ and $f(z)=z$. Then, $d(y,z)\neq0$ and $$d(y,z)=d(f(y),f(z))\leq\alpha d(y,z)<d(y,z)$$which is a contradiction.
---
##### Examples
> [!h] Example 1 (Product Metric Space)
> Let $(X_{n},d_{n})_{n\geq 1}$ be a sequence of complete metric spaces. Denote $X:=\prod_{n\geq 1}^{}X_{n}$. Then,
> 1. $X$ is a complete metric space.

> [!proof]+
> Let $(x^{(k)})_{k}\subseteq X$ be a Cauchy sequence in $X$. Then, for any $\varepsilon>0$, there exists $k\in \mathbb{N}$ s.t. for any $i,j\geq k$, $$d(x^{(i)},x^{(j)})=\sum_{n\geq 1}^{} \frac{1}{2^n} \frac{d_{n}(x^{(i)}_{n},x^{(j)}_{n})}{1+d_{n}(x^{(i)}_{n},x^{(j)}_{n})}<\varepsilon$$Therefore, for any $n\geq 1$, $\frac{d_{n}(x^{(i)}_{n},x^{(j)}_{n})}{1+d_{n}(x^{(i)}_{n},x^{(j)}_{n})}< \varepsilon 2^n$. Hence, $(x^{(k)}_{n})_{k}$ is a Cauchy sequence for all $n\geq 1$. Hence, it converges to $x_{n}\in X_{n}$. Let $x:=(x_{n})_{n}$. We only need to show that $x^{(k)}\to x$. Let $\varepsilon>0$. Then, 
---
##### Non-Examples
> [!h] Non-Example 1 (Completeness is a property of the metric and not of the topology)
> Let $X=[0,+\infty)$. Define a function $\delta:X\times X\to [0,+\infty),(x,y)\mapsto \left| e^{-x}-e^{-y} \right|$
> 1. $\delta$ is a distance on $X$ with the topology defined by $\delta$ on $X$ is the euclidean subspace topology.
> 3. $(X,\delta)$ is not complete, however $X$ is a complete space with the restriction of the euclidean distance.

> [!proof]-
> We have:
> 1. The non-negativity, symmetry and triangle inequality is inherited from the norm $\left| \cdot  \right|$ in the definition. The non-degeneracy is given by the injectivity of $e^{-x}$. 
>    
>    Let $x,y\in X$. Then, by the mean value theorem, it holds that: $$e^{-\max\{ x,y \}}\left| x-y \right| \leq\left| e^{-x}-e^{-y} \right| \leq e^{-\min\{ x,y \}}\left| x-y \right| $$This shows that the topology are equivalent.
> 3. Let $x_{n}=n$ for all $n\geq 1$. Then, for all $\varepsilon>0$, there exists $N$ s.t. $e^{-N}< \frac{\varepsilon}{2}$. As $e^{-x}$ is decreasing, for all $m,n\geq N$: $$\delta(x_{n},x_{m})=\left| e^{-n}-e^{-m} \right|\leq e^{-n}+e^{-m}<\varepsilon $$This shows that $(x_{n})_{n}$ is a Cauchy sequence which clearly doesn't have a limit.
>    
>    However, let $(x_{n})_{n}\subseteq X$ be a Cauchy sequence. Then, as $\mathbb{R}$ is complete with the euclidean distance, there exists a limit $x\in \mathbb{R}$. This has to be in $X$ as otherwise, as $X$ is closed.