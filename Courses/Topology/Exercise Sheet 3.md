#Series #Topology 

> [!def] Problem 1
> Let $X=\mathcal{F}(\mathbb{R},\mathbb{C})$ with the topology $\mathcal{T}_{p}$.
> 1. Let $A\subseteq X$ be any subset. Show that $0\in \bar{A}$ if and only if, for any $x\in \mathbb{R}$ and any $\varepsilon>0$, there exists $f\in A$ such that $\left| f(x) \right|<\varepsilon$.
> 2. For $t\in \mathbb{R}$, let $g_{t}\in X$ be the function defined by $g_{t}(x)=x-t$. Let $A=\{ g_{t}|t\in \mathbb{R} \}$. Show that $0\notin A$ and that $0\in\overline{A}$.
> 3. Show that there exists no sequence $(f_{n})_{n}$ with $f_{n}\in A$ for all $n$ such that $f_{n}\to 0$ as $n\to +\infty$ (for the topology $\mathcal{T}_{p}$).

We have: 
1. let $0\in \overline{A}$. Then, then for any neighborhood $U$ of $0$, $U\cap A\neq \varnothing$. Therefore, for any $x\in \mathbb{R}$ and $\varepsilon>0$, there exists $f\in \{ g\in \mathcal{F}(\mathbb{R},\mathbb{C}):\left| g(x) \right|<\varepsilon \}\cap A$. 
   
   Conversely, suppose for all $x\in \mathbb{R}$ and $\varepsilon>0$, there exists $f\in A$ s.t. $\left| f(x) \right|<\varepsilon$. Then, for any (open) neighborhood $U$ of $0$ and $x\in U$, there exists $\varepsilon>0$ s.t. $$\{ g\in \mathcal{F}(\mathbb{R},\mathbb{C}):\left| g(x) \right| <\varepsilon \}\subseteq U$$As $f\in U\cap A$, $0\in\overline{A}$.
2. There cannot be $t\in \mathbb{R}$ s.t. $g_{t}(x)=x-t=0$ for all $x\in \mathbb{R}$. Therefore, $0\notin A$. However, for any $x\in \mathbb{R}$ and $\varepsilon>0$, $g_{x}\in A$ and $\left| g_{x}(x) \right|=0<\varepsilon$. Therefore, by 1, $0\in \overline{A}$.
3. Let $(g_{t_{n}})_{n}\subseteq A$ s.t. $g_{t_{n}}\to{0}$ in $\mathcal{T}_{p}$. This means that for all $x\in \mathbb{R}$, $g_{t_{n}}(x)=x-t_{n}\to 0$, i.e. $\lim_{ n \to \infty }t_{n}=x$ for all $x\in \mathbb{R}$, which is a contradiction.
---
> [!def] Problem 2
> Let $X$ be the space of all functions from $\mathbb{C}$ to $\mathbb{C}$, and denote by $\mathcal{T}_{p}$ and $\mathcal{T}_{u}$ the topologies of pointwise convergence and uniform convergence, respectively. Let $A\subseteq X$ be the subset of polynomial functions $f:\mathbb{C}\to \mathbb{C}$.
> 1. Show that $A$ is dense in $(X,\mathcal{T}_{p})$.
> 2. Show that $A^\circ$ is empty in $(X,\mathcal{T}_{p})$.
> 3. Show that for any $f\in X$, the sets $$V_{f,n}:=\{ g\in X:\left| f(x)-g(x) \right| <1/n,\quad \forall x\in \mathbb{C} \}$$for $n\geq 1$ form a countable fundamental system of neighborhoods of $f$ in $(X,\mathcal{T}_{u})$.
> 4. Show that the subset: $$A_{0}:=\{ f\in A:f(0)=0 \}$$is discrete in $(X,\mathcal{T}_{u})$, i.e., the subspace topology on $A_{0}$ induced by the topology $\mathcal{T}_{u}$ is the discrete topology.

We have:
1. let $f\in X$ and $U$ be an open neighborhood of $f$ w.r.t $\mathcal{T}_{p}$. Let $x\in \mathbb{C}$ then there exists $x\in \mathbb{C}$ and $\varepsilon>0$ s.t. $$\{ g\in X :\left| g(x)-f(x) \right| <\varepsilon\}\subseteq U$$Now choose $g\equiv f(x)$. Then, $g\in U\cap A$. Therefore, $f\in \overline{A}$, i.e. $X=\overline{A}$.
2. Let $U$ be an open set s.t. $U\subseteq A$. If $f\in U$, then there exists $x_{0}\in \mathbb{C}$ and $\varepsilon>0$ s.t. $$\{ g\in X:\left| g(x_{0})-f(x_{0}) \right|<\varepsilon \}\subseteq U$$However, consider $h(x)=\begin{cases}f(x)&x=x_{0}\\0&x\neq x_{0}&\end{cases}$. Then, $h\notin A$ but $\left| h(x_{0})-f(x_{0}) \right|=0$. Therefore, this is a contradiction and $U$ has to be empty. As $U$ is arbitrary, $A^\circ=\varnothing$.
3. Let $V$ be a neighborhood of $f$ in $(X,\mathcal{T}_{u})$. Then, there is an open set $f\in U\subseteq V$. Therefore, there exists $\varepsilon>0$ and $n\geq 1$ (e.g. $\frac{1}{n}<\varepsilon$) s.t. $V_{f,n}\subseteq\{ g\in X:\sup_{x\in\mathbb{C}}\left| f(x)-g(x) \right|<\varepsilon \}\subseteq U\subseteq V$.
4. Let $f\subseteq A_{0}$. It suffices to show that $\{ f \}$ is open w.r.t. the subspace topology.  