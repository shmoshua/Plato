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
4. Let $f\subseteq A_{0}$. It suffices to show that $\{ f \}$ is open w.r.t. the subspace topology. Let $\varepsilon>0$ and we will show that $\{ f \}:=\{ g\in X:\sup_{x\in \mathbb{C}}\left| f(x)-g(x) \right|<\varepsilon \}\cap A_{0}$. Assume there exists $g\in \{ g\in X:\sup_{x\in \mathbb{C}}\left| f(x)-g(x) \right|<\varepsilon \}\cap A_{0}$. As $g$ is a polynomial, $f-g$ is a polynomial and from $\left| (f-g)(x) \right|<\varepsilon$, $f-g$ is constant, i.e. $f(x)=g(x)+k$ for some $k$ for all $x\in \mathbb{C}$. However, as $f(0)=0=g(0)$, $k=0$ and $g=f$. 
   
   Indeed, $\{ g\in X:\sup_{x\in \mathbb{C}}\left| f(x)-g(x) \right|<\varepsilon \}$ is open and this shows that $A_{0}$ is discrete.
----
> [!def] Problem 3
> Let $n\geq 0$ be an integer. A subset $A\subseteq \mathbb{C}^n$ is called ***algebraic*** if there exists a set $I$ (potentially arbitrary) and a family $(f_{i})_{i\in I}$ of polynomials $f_{i}\in\mathbb{C}[X_{1},\dots,X_{n}]$ s.t. $$A=\{ x\in \mathbb{C}^n:f_{i}(x)=0,\quad \forall i\in I \}$$ 
> 1. Show that there is a topology $\mathcal{T}_{Z}$ (the “Zariski topology”) on $\mathbb{C}^n$ such that $A\subseteq \mathbb{C}^n$ is closed if and only if $A$ is algebraic.
> 2. Show that for $n=1$, the Zariski topology on $\mathbb{C}$ is identical with the topology $\mathcal{T}_{\text{fin}}$ with closed sets given by $\mathbb{C}$ and finite sets.
> 3. Let $m\geq 0$ be an integer and let $f:\mathbb{C}^n\to \mathbb{C}^m$ be a polynomial map. Show that $f$ is continuous for the Zariski topologies.
> 4. For $n\geq 1$, show that the Zariski topology on $\mathbb{C}^n$ is not Hausdorff.
> 5. Show that $A\subseteq \mathbb{C}^n$ is dense for the Zariski topology unless there exists $f\in \mathbb{C}[X_{1},..,X_{n}]$, $f\neq 0$, s.t. $A\subseteq \{ x\in \mathbb{C}^n:f(x)=0 \}$
> 6. Show that $\mathbb{Z}^n$ is dense in $\mathbb{C}^n$ for the Zariski topology. (Hint: use the previous question, and argue by induction on $n$, writing a polynomial $f$ vanishing on $\mathbb{Z}^n$ as a polynomial in $X_{n}$ with coefficients in $C[X_{1},\dots,X_{n-1}]$ for the induction step.)

We have:
1. Firstly, for $f\equiv{1}$, $\varnothing=\{ x\in \mathbb{C}^n:f(x)=0 \}$. For $f\equiv 0$, $\mathbb{C}^n=\{ x\in \mathbb{C}^n:f(x)=0 \}$. Therefore, $\varnothing,X$ are algebraic, closed and thereby open.
   
   Let $A_{1},A_{2}$ be two algebraic sets with $(f_{i})_{i\in I},(g_{j})_{j\in J}$ as the associated sets respectively. Then, consider $\{ f_{i}g_{j}: i\in I,j\in J \}$. We claim that:
   $$A_{1}\cup A_{2}=\{ x\in \mathbb{C}^n:f_{i}(x)g_{j}(x)=0,\quad \forall i\in I,j\in J \}$$Let $x\in A_{1}\cup A_{2}$. Then, wlog assume that $x\in A_{1}$. Indeed, $f_{i}(x)g_{j}(x)=0$ for all $i\in I$ and $j\in J$ as $f_{i}(x)=0$ for all $i\in I$. Conversely, if $x\notin A_{1}\cup A_{2}$, then $x\notin A_{1}$ and $x\notin A_{2}$. Therefore, there exists $f_{i}$ and $g_{j}$ s.t. $f_{i}(x)g_{j}(x)\neq 0$. This proves the claim.
   
   Let $(A_{n})_{n}$ be an arbitrary family of algebraic sets with $(f_{n,i})_{i\in I_{n}}$ as the associated polynomials. Then, $$\bigcap_{n=1}^{\infty}A_{n}=\{ x\in \mathbb{C}^n: \}$$
