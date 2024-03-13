#Series #Topology 

> [!def] Problem 1
> Let $X=\mathcal{F}(\mathbb{R},\mathbb{C})$ with the topology $\mathcal{T}_{p}$.
> 1. Let $A\subseteq X$ be any subset. Show that $0\in \bar{A}$ if and only if, for any $N\geq 1$, $(x_{n})_{n}\in \mathbb{R}^N$ and $\varepsilon>0$, there exists $f\in A$ such that $\left| f(x_{n}) \right|<\varepsilon$ for all $n$.
> 2. Let $A\subseteq X$ be the subset of monic polynomials with real coefficients. Show that $0\notin A$ and that $0\in \overline{A}$. Show that the same holds for $A$ the subset of the indicator functions of the complements of finite sets (i.e $f_{S}:=1-\chi_{S}$, with $S$ finite).
> 3. For the set $A$ with the indicator functions, show that there exists no sequence $(f_{n})_{n}\subseteq A$ s.t. $f_{n}\to 0$.

We have: 
1. Let $0\in \overline{A}$. Then, for any neighborhood $U$ of $0$, $U\cap A\neq \varnothing$. Therefore, for any $N\geq 1$, $(x_{n})_{n}\in \mathbb{R}^N$ and $\varepsilon >0$, $\{ g\in \mathcal{F}(\mathbb{R},\mathbb{C}):\left| g(x_{n}) \right| <\varepsilon,\forall n\in [N] \}$ is an open neighborhood of $0$ and there exists $$f\in \{ g\in \mathcal{F}(\mathbb{R},\mathbb{C}):\left| g(x_{n}) \right| <\varepsilon,\forall n\in [N] \}\cap A$$Conversely, suppose for all $N\geq 1$, $(x_{n})_{n}\in \mathbb{R}^N$ and $\varepsilon>0$ there exists $f\in A$ s.t. $\left| f(x_{n}) \right|<\varepsilon$ for all $n$. Let $U$ be any neighborhood of $0$. Then, there exists $(x_{n})_{n}\in \mathbb{R}^N$ and $\varepsilon>0$ s.t. $$V:=\{ f\in \mathcal{F}(\mathbb{R},\mathbb{C}):\left| f(x_{n}) \right| <\varepsilon,\ \forall n\in [N] \}\subseteq U$$By assumption, we have $f\in V\cap A\subseteq U\cap A$. Therefore, $U\cap A\neq \varnothing$ and $0\in\overline{A}$.
2. We know that $0$ is not monic by definition, so $0\notin A$. However, for any $N\geq 1$, $(x_{n})_{n}\in \mathbb{R}^N$ and $\varepsilon>0$, $$f(x):=\prod_{n=1}^{N}(x-x_{n})$$is a monic polynomial s.t. $\left| f(x_{n}) \right|<\varepsilon$. Therefore, from 1, $0\in \overline{A}$.
   
   For the indicator functions, $f_{S}\neq 0$ as $S\subseteq \mathbb{R}$ is finite. Therefore, $0\notin A$.  Further, for any $N\geq 1$, $(x_{n})_{n}\in \mathbb{R}^N$ and $\varepsilon>0$, define $S:=\{ x_{n} \}_{n}$ and $f_{S}(x_{n})=0$ for all $n\in [N]$. This proves the statement.
3. Let $(f_{S_{n}})_{n}$ be a sequence of such indicator functions s.t. $f_{S_{n}}(x)\to 0$ where $S_{n}$ is finite for all $n$. As $f_{S_{n}}(\mathbb{R})\subseteq\{ 0,1 \}$ this means that for each $x\in \mathbb{R}$, there exists $n$ s.t. $x\in S_{n}$ for all $n\geq N$. However, from the finiteness of $S_{n}$, this means we can construct a countable sequence $(x_{n})_{n}=\mathbb{R}$, i.e. $\mathbb{R}$ is countable. Indeed, this is a contradiction. 
---
> [!def] Problem 2
> Let $X$ be the space of all functions from $\mathbb{C}$ to $\mathbb{C}$, and denote by $\mathcal{T}_{p}$ and $\mathcal{T}_{u}$ the topologies of pointwise convergence and uniform convergence, respectively. Let $A\subseteq X$ be the subset of polynomial functions $f:\mathbb{C}\to \mathbb{C}$.
> 1. Show that $A$ is dense in $(X,\mathcal{T}_{p})$.
> 2. Show that $A^\circ$ is empty in $(X,\mathcal{T}_{p})$.
> 3. Show that for any $f\in X$, the sets $$V_{f,n}:=\{ g\in X:\left| f(x)-g(x) \right| <1/n,\quad \forall x\in \mathbb{C} \}$$for $n\geq 1$ form a countable fundamental system of neighborhoods of $f$ in $(X,\mathcal{T}_{u})$.
> 4. Show that the subset: $$A_{0}:=\{ f\in A:f(0)=0 \}$$is discrete in $(X,\mathcal{T}_{u})$, i.e., the subspace topology on $A_{0}$ induced by the topology $\mathcal{T}_{u}$ is the discrete topology.

We have:
1. let $f\in X$ and $U$ be an open neighborhood of $f$ w.r.t $\mathcal{T}_{p}$. Let $x\in \mathbb{C}$ then there exists $F\subseteq\mathbb{C}$ finite and $\varepsilon>0$ s.t. $$\{ g\in X :\left| g(x)-f(x) \right| <\varepsilon, \forall x\in F\}\subseteq U$$Now there exists a polynomial $p$ that interpolates $\{ (x,f(x)) \}_{x\in F}$. Then, $p\in U\cap A$. Therefore, $f\in \overline{A}$, i.e. $X=\overline{A}$.
2. Let $U$ be an open set s.t. $U\subseteq A$. If $f\in U$, then there exists $F\subseteq \mathbb{C}$ finite and $\varepsilon>0$ s.t. $$\{ g\in X:\left| g(x)-f(x) \right|<\varepsilon, \forall x\in F \}\subseteq U$$However, consider $h(x)=\begin{cases}f(x)&x\in F\\0&x\notin F&\end{cases}$. Then, $h\notin A$ but $\left| h(x_{0})-f(x_{0}) \right|=0$. Therefore, this is a contradiction and $U$ has to be empty. As $U$ is arbitrary, $A^\circ=\varnothing$.
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
   $$A_{1}\cup A_{2}=\{ x\in \mathbb{C}^n:f_{i}(x)g_{j}(x)=0,\quad \forall i\in I,j\in J \}$$Let $x\in A_{1}\cup A_{2}$. Then, wlog assume that $x\in A_{1}$. Indeed, $f_{i}(x)g_{j}(x)=0$ for all $i\in I$ and $j\in J$ as $f_{i}(x)=0$ for all $i\in I$. Conversely, if $x\notin A_{1}\cup A_{2}$, then $x\notin A_{1}$ and $x\notin A_{2}$. Therefore, there exists $f_{i}$ and $g_{j}$ s.t. $f_{i}(x)g_{j}(x)\neq 0$. This proves the claim, i.e. $A_{1}\cup A_{2}$ is algebraic.
   
   Let $(A_{n})_{n}$ be an arbitrary family of algebraic sets with $(f_{n,i})_{i\in I_{n}}$ as the associated polynomials. Then, $$\bigcap_{n=1}^{\infty}A_{n}=\{ x\in \mathbb{C}^n:f_{n,i}(x)=0,\quad \forall n\geq 1,i\in I_{n} \}$$Therefore, any arbitrary intersection is also algebraic.
   
   This shows the statement.
2. We have from above that $\mathbb{C}$ is algebraic. Now, for any $x_{0}\in \mathbb{C}$, let $f(x)=x-x_{0}$ and $$\{ x_{0} \}=\{ x\in \mathbb{C}^n:f(x)=0 \}$$Therefore, $\{ x_{0} \}$ is closed w.r.t the Zariski topology and thereby any finite set. If $A\subseteq \mathbb{C}^n$ is infinite with $A\neq \mathbb{C}$, then there exists a non-zero $f\in \mathbb{C}[X]$ with infinitely many roots which is a contradiction. Therefore, no non-$\mathbb{C}$ infinite set is algebraic.
3. Let $A\subseteq \mathbb{C}^m$ be algebraic with $(g_{i})_{i\in I}$ as its associated polynomials. Then, $(g_{i}\circ f)_{i\in I}$ is a set of polynomials and: $$f^{-1}(A)=\{ x\in \mathbb{C}^n:(g_{i}\circ f)(x)=0,\quad\forall i\in I \}$$If for $x\in \mathbb{C}^n$ $(g_{i}\circ f)(x)=0$ for all $i\in I$, $f(x)\in A$. Similarly, if $x\in f^{-1}(A)$, then $g_{i}(f(x))=0$ for all $i\in I$. Therefore, $f$ is continuous.
4. Let $A_{1},A_{2}$ be algebraic sets s.t. $A_{1}\neq \mathbb{C}\neq A_{2}$ with $(f_{i})_{i\in I},(g_{j})_{j\in J}$ respectively. Then, we know that $A_{1},A_{2}$ are both finite as a system of polynomials only admit finite number of solutions over an infinite field. Therefore, for $x,y\in \mathbb{C}^n$ with $x\neq y$, if there exists open neighborhoods $U,V$ of $x,y$ respectively, $X \backslash U$ and $X \backslash V$ are algebraic and finite. In other words, $(X \backslash U)\cup(X \backslash V)$ is finite and $U\cap V\neq \varnothing$. This shows that the space is not Hausdorff.
5. Assume that $A$ is not dense. Then, there exists $x\in \mathbb{C}^n$ and an open neighborhood $U$ of $x$ s.t. $U\cap A=\varnothing$. In other words, $A\subseteq X \backslash U=:F$ which is algebraic, i.e. there exists $(f_{i})_{i\in I}$ s.t. $$A\subseteq\{  y\in \mathbb{C}^n:f_{i}(y)=0,\quad \forall i\in I\}$$Notice that if $f_{i}=0$ for all $i\in I$, then $f_{i}(x)=0$ for all $i\in I$ and $x\in F$, which is a contradiction. 
   
   On the other hand, if such function $f$ exists, then $\{ x\in \mathbb{C}^n:f(x)=0 \}\subsetneq\mathbb{C}^n$ is a closed set and $\overline{A}\subsetneq \mathbb{C}^n$.
6. It is clear that there exists no non-zero polynomial $f\in \mathbb{C}[X]$ s.t. $f(z)=0$ for every $z\in \mathbb{Z}$. Therefore, by 5, $\mathbb{Z}$ is dense in $\mathbb{C}$. Now assume $n\geq 2$ and $\mathbb{Z}^{n-1}$ is dense in $\mathbb{C}^{n-1}$. If $\mathbb{Z}^{n}$ is not dense in $\mathbb{C}^n$, there exists $f\in \mathbb{C}[X_{1},\dots,X_{n}]$ s.t. $f(x)=0$ for all $x\in \mathbb{Z}^n$. Now, we write: $$f(x)=f_{m}(x_{1:n-1})x_{n}^{m}+\dots+f_{1}(x_{1:n-1})x_{n}+f_{0}(x_{1:n-1})$$ where $f_{i}\in \mathbb{C}[X_{1},\dots,X_{n-1}]$. Then, consider $x\in \mathbb{Z}^{n-1}\times \{ 0 \}$. We have that: $$f(x)=f_{0}(x_{1:n-1})=0$$ Therefore, there exists a function $f_{0}\in \mathbb{C}[X_{1},\dots,X_{n-1}]$ s.t. for all $z\in \mathbb{Z}^{n-1}$, $f_{0}(z)=0$, i.e. $\mathbb{Z}^{n-1}$ is not dense in $\mathbb{C}^{n-1}$, a contradiction.
---
> [!def] Problem 4
> Let $n\geq 1$ be an integer. The goal of this exercise is to show that if $U\subseteq \mathbb{C}^n$ is any non-empty open set for the Zariski topology, then $U$ is dense for the Zariski topology. We argue by contradiction, so assume that $\overline{U}\neq \mathbb{C}^n$.
> 1. Show that there exist closed sets $A_{1}\neq \mathbb{C}^n$ and $A_{2}\neq \mathbb{C}^n$ s.t. such that $A_{1}\cup A_{2}=\mathbb{C}^n$.
> 2. Let $$I_{i}:=\{ f\in\mathbb{C}[X_{1},\dots,X_{n}]:f(x)=0,\quad \forall x\in A_{i} \}$$ for $i\in \{ 1,2 \}$. Show that $I_{1}\cap I_{2}=\{ 0 \}$. 
> 3. Deduce that either $I_{1}=\{ 0 \}$ or $I_{2}=\{ 0 \}$, and derive a contradiction.

We have:
1. As $\overline{U}\neq \mathbb{C}^n$, we have $A_{1}=\overline{U}$ and $A_{2}= \mathbb{C}^n \backslash U$ are closed sets and $$A_{1}\cup A_{2}=\overline{U}\cup (\mathbb{C}^n \backslash U)=\mathbb{C}^n$$
2. Assume we have $f\in I_{1}\cap I_{2}$ where $f\not\equiv 0$. Then, $f(x)=0$ for all $x\in A_{1}\cup A_{2}=\mathbb{C}^n$, which is a contradiction.
3. Assume that there exists non-zero $f,g\in \mathbb{C}[X_{1},\dots,X_{n}]$ s.t. $f\in I_{1}$ and $g\in I_{2}$. Then, $fg$ is non-zero and $f(x)g(x)=0$ for all $x\in A_{1}\cup A_{2}$. Therefore, $fg\in I_{1}\cap I_{2}$, which is a contradiction. Therefore, $I_{1}=\{ 0 \}$ or $I_{2}=\{ 0 \}$.
   
   However, as $U$ is not dense, there exists non-zero $f\in \mathbb{C}[X_{1},\dots,X_{n}]$ s.t. $$\overline{U}\subseteq \{ x\in \mathbb{C}^n:f(x)=0 \}$$i.e. $f\in I_{1}$, which implies that $I_{2}=\{ 0 \}$. Then, $\mathbb{C}^n \backslash U$ is dense and $\mathbb{C}^n \backslash U = \mathbb{C}^n$, which implies that $U=\varnothing$. This is a contradiction.
---
> [!def] Problem 5
> Let $n\geq 1$ be an integer. 
> 1. Show that $\text{GL}_{n}(\mathbb{C})\subseteq \text{M}_{n,n}(\mathbb{C})$ is open.
> 2. Deduce that any polynomial function of the entries of a matrix which vanishes for all invertible matrices is the zero polynomial, so vanishes for all matrices.

Notice that $\det:\mathbb{\mathbb{C}}^{n^{2}}\to \mathbb{C}$ is a polynomial $\text{det}\in \mathbb{C}[X_{1},\dots,X_{n^{2}}]$. Then, $$\text{M}_{n,n}(\mathbb{C}) \backslash \text{GL}_{n}(\mathbb{C})=\{ A\in \mathbb{C}^{n^{2}}:\det(A)=0 \}$$Therefore, $\text{M}_{n,n}(\mathbb{C}) \backslash \text{GL}_{n}(\mathbb{C})$ is algebraic and $\text{GL}_{n}(\mathbb{C})$ is open and non-empty as $\text{id}\in \text{GL}_{n}(\mathbb{C})$. Therefore, $\text{GL}_{n}(\mathbb{C})$ is dense in $\text{M}_{n,n}(\mathbb{C})$. Now let $f:\mathbb{C}^{n^{2}}\to \mathbb{C}$ be a polynomial s.t. $f(A)=0$ for all $A\in \text{GL}_{n}(\mathbb{C})$. Then, $$\text{GL}_{n}(\mathbb{C})\subseteq \{ A\in \text{M}_{n,n}(\mathbb{C}):f(A)=0 \}$$and as the set is closed, $\text{M}_{n,n}(\mathbb{C})=\{ A\in \text{M}_{n,n}(\mathbb{C}):f(A)=0 \}$.

---

