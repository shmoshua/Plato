#Series  #Topology 

> [!def] Problem 1
> Let $X=[0,+\infty)$. Define a function $\delta:X\times X\to [0,+\infty),(x,y)\mapsto \left| e^{-x}-e^{-y} \right|$
> 1. Show that $\delta$ is a distance on $X$.
> 2. Show that the topology defined by $\delta$ on $X$ is the euclidean subspace topology.
> 3. Show that $(X,\delta)$ is not complete.
> 4. Show that $X$ is a complete space with the restriction of the euclidean distance.

We have:
1. The non-negativity, symmetry and triangle inequality is inherited from the norm $\left| \cdot  \right|$ in the definition. The non-degeneracy is given by the injectivity of $e^{-x}$. 
2. Let $x,y\in X$. Then, by the mean value theorem, it holds that: $$e^{-\max\{ x,y \}}\left| x-y \right| \leq\left| e^{-x}-e^{-y} \right| \leq e^{-\min\{ x,y \}}\left| x-y \right| $$This shows that the topology are equivalent.
3. Let $x_{n}=n$ for all $n\geq 1$. Then, for all $\varepsilon>0$, there exists $N$ s.t. $e^{-N}< \frac{\varepsilon}{2}$. As $e^{-x}$ is decreasing, for all $m,n\geq N$: $$\delta(x_{n},x_{m})=\left| e^{-n}-e^{-m} \right|\leq e^{-n}+e^{-m}<\varepsilon $$This shows that $(x_{n})_{n}$ is a Cauchy sequence which clearly doesn't have a limit.
4. Let $(x_{n})_{n}\subseteq X$ be a Cauchy sequence. Then, as $\mathbb{R}$ is complete with the euclidean distance, there exists a limit $x\in \mathbb{R}$. This has to be in $X$ as otherwise, as $X$ is closed.
---
> [!def] Problem 2
> In a metric space $(X,d)$, the diameter of a non-empty subset $Y\subseteq X$ is defined to be $$\text{diam}(Y):=\text{sup}\{ d(x,y):(x,y)\in Y^{2} \}$$ if this supremum exists in $\mathbb{R}$, or $+\infty$ otherwise. Let $X$ be a complete metric space. Let $(C_{n})_{n\geq 1}$ be closed subsets of $X$ such that $C_{n}\supseteq C_{n+1}$ for $n\geq 1$.
> 1. Assuming that $C_{n}\neq \varnothing$ and that $\lim_{ n \to \infty }\text{diam}(C_{n})=0$, show that $\bigcap_{n\geq 1}^{}C_{n}\neq \varnothing$.
> 2. Show that the conclusion is not always valid if $X$ is not complete.

We have:
1. as $C_{n}$ is non-empty, we can construct a sequence $(x_{n})_{n}$ where $x_{n}\in C_{n}$. We show that this is a Cauchy sequence. Let $\varepsilon>0$. Then, there exists $N\geq 1$ s.t. $\text{diam}(C_{n})<\varepsilon$ for all $n\geq N$. As $(C_{n})$ is decreasing, for all $n,m\geq N$:$$d(x_{n},x_{m})\leq \text{diam}(C_{N})<\varepsilon$$ Therefore, $x_{n}\to x\in X$. For any $C_{n}$, we have that $(x_{m})_{m\geq n}\subseteq C_{n}$ and as $C_{n}$ is closed, $x\in C_{n}$. This shows that the intersection is non-empty.
2. Consider $\mathbb{Q}$ with the euclidean subspace topology. Consider $C_{n}:=\left[ \pi-\frac{1}{n},\pi+\frac{1}{n} \right]\cap \mathbb{Q}$, which are closed and $\text{diam}(C_{n})\leq \frac{2}{n}$. However, $\bigcap_{n\geq 1}^{}C_{n}=\varnothing$ as $\pi \notin \mathbb{Q}$.
---
> [!def] Problem 3
> Let $X$ be a complete metric space. Let $(C_{n})_{n\geq 1}$ be a sequence of closed subsets of $X$, each with empty interior. Let $C$ be the union of the $C_{n}$ for $n\geq 1$. Let $U$ be a non-empty open subset of $X$.
> 1. Let $U_{0}=U$. Show that there exists a sequence $(U_{n})_{n\geq 1}$ of non empty open sets in $X$ such that the conditions 
> 	- $\overline{U_{n}}\cap C_{n}=\varnothing$
> 	- $\overline{U_{n}}\subseteq U_{n-1}$
> 	- $d(x,y)< \frac{1}{ n}$ for all $(x,y)\in U_{n}\times U_{n}$
> 
>      hold for $n\geq 1$.
>   2. Show that $\bigcap_{n\geq 1}^{}\overline{U_{n}}\neq \varnothing$.
>   3. Deduce that $U\cap(X \backslash C)\neq \varnothing$, and therefore that $C$ has empty interior.

We have: 
1. Let $U_{n-1}$ be a non-empty open set that meets the condition. As $C_{n}$ has an empty interior, there exists $x_{n}\in U_{n-1}\backslash C_{n}$. Then, $x_{n}\notin C_{n}\cup \partial U_{n-1}$ which is a closed set. Therefore, there exists a neighborhood $V_{n}$ of $x$ s.t. $\overline{V_{n}}\cap (C_{n}\cup \partial U_{n-1})=\varnothing$. As $x\in U_{n-1}$, $V_{n}$ meets the first two conditions. Lastly, we just take $U_{n}:=V_{n}\cap B_{< \frac{1}{2n}}(x_{n})$ and all the conditions are satisfied.
2. As $(\overline{U_{n}})_{n}$ is a decreasing sequence of non-empty closed sets with $\lim_{ n \to \infty } \text{diam}(\overline{U_{n}})=\lim_{ n \to \infty } \frac{1}{n}=0$Therefore, by the previous exercise, $\bigcap_{n\geq 1}^{}\overline{U_{n}}\neq \varnothing$.
3. Let $x\in \bigcap_{n\geq 1}^{}\overline{U_{n}}$. Then, $x\notin C_{n}$ for all $n$ and $x\notin C$. However, $x\in\overline{U}_{1}\subseteq U$. Therefore, $x\in U\cap(X \backslash C)$. This shows that $X\backslash C$ is dense in $X$, i.e. $C$ has an empty interior. 
---
> [!def] Problem 4
> Let $X$ be a non-empty complete metric space and let $f:X\to X$ be a continuous map such that $d(f(x),f(y))\leq\alpha d(x,y)$ for all $(x,y)\in X^{2}$ for some constant $\alpha<1$.
> 1. Show that for any $x_{0}\in X$, the sequence $(x_{n})_{n}$ defined by $x_{n+1}=f(x_{n})$ converges to a solution $y\in X$ of the equation $f(y)=y$.
> 2. Show that there is a unique element $y\in X$ such that $f(y)=y$.

We have that: 
1. we claim that $(x_{n})_{n}$ is Cauchy. As $d(x_{n},x_{n+1})\leq\alpha d(x_{n-1},x_{n})\leq\alpha^nd(x_{0},x_{1})$, for $\varepsilon>0$, there exists $N\geq 1$ s.t. $d(x_{N},x_{N+1})<\varepsilon$.  Then, for all $n\geq N$, $$d(x_{N},x_{n})\leq\left( \sum_{i=1}^{n-N}\alpha^{i-1} \right)d(x_{N},x_{N+1})=\frac{(1-\alpha)^{n-N}}{1-\alpha}d(x_{N},x_{N+1})<d(x_{N},x_{N+1})<\varepsilon$$Therefore, $(x_{n})_{n}\to y\in X$. Then, $f(y)=f(\lim_{ n \to \infty }x_{n})=\lim_{ n \to \infty }f(x_{n})=\lim_{ n \to \infty }x_{n+1}=y$.
2. Assume that there exists $y\neq z\in X$ s.t. $f(y)=y$ and $f(z)=z$. Then, $d(y,z)\neq0$ and $$d(y,z)=d(f(y),f(z))\leq\alpha d(y,z)<d(y,z)$$which is a contradiction.
---
> [!def] Problem 5
> Let $$X:=(\{ 0 \}\times[-1,1])\cup \bigcup_{n\geq 1}^{}\left\{  \frac{1}{n}  \right\}\times[-1,1]\cup([0,1]\times \{ 1 \})\subseteq \mathbb{R}^{2}$$ with the subspace topology from the euclidean topology of $\mathbb{R}^{2}$. It is a metric space.
> 1. Show that $X$ is connected.
> 2. Let $x_{0}=(0,0)\in X$. Explain why the sets $$U_{\delta}:=X \cap \{ (x,y)\in \mathbb{R}^{2}:\left| x \right| <\delta,\left| y \right| <\delta \}$$with $0<\delta<1$ form a fundamental system of open neighborhoods of $x_{0}$ in $X$.
> 3. Show that if $0<\delta<1$, then the connected component of $x_{0}$ in the neighborhood $U_{\delta}$ is $\{ 0 \}\times(-\delta,\delta)$.
> 4. Deduce that $X$ is not locally connected. 
> 5. Give an example of a locally connected space which is not connected.

We have:
1. 