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
3. Let $x\in \bigcap_{n\geq 1}^{}\overline{U_{n}}$. Then, $x\notin C_{n}$ for all $n$ and $x\notin C$. However, $x\in\overline{U}_{1}\subseteq U$. Therefore, $x\in U\cap(X \backslash C)$. 