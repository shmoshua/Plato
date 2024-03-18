#Series #Topology 

> [!def] Problem 1
> Let $X$ be a topological space. Show that $X$ is Hausdorff if and only if, for every $x\in X$, we have $$\bigcap_{x\in U}^{}\overline{U}=\{ x \}$$ where $U$ runs over all neighborhoods of $x$.

Assume that $X$ is Hausdorff. Indeed, $\{ x \}\subseteq \bigcap_{x\in U}^{}\overline{U}$ is trivial. Let $y\in \bigcap_{x\in U}^{}\overline{U}$ and assume $y\neq x$. Then, there exists disjoint open neighborhoods $U,V$ of $x,y$, respectively. However, $y\in \overline{U}$ by assumption and it follows that $U\cap V\neq\varnothing$, which is a contradiction. This shows the inclusion.

Conversely, assume that the condition holds. We will show that $X$ is Hausdorff. Let $x,y\in X$ s.t. $x\neq y$. Then, as $\bigcap_{x\in U}^{}\overline{U}=\{ x \}$, there exists open $U\ni x$ s.t. $y\notin\overline{U}$, i.e. there exists an open neighborhood $V$ of $y$ s.t. $U\cap V=\varnothing$. This proves the statement.

---
> [!def] Problem 2
> Let $X$ be a topological space. 
> 1. If $X$ is a Hausdorff space, show that a filter $\mathcal{F}$ on $X$ which converges has a unique limit.
> 2. Conversely, suppose a convergent filter $\mathcal{F}$ on $X$ always has a unique limit. Show that $X$ is a Hausdorff space. 

We have: 
1. Assume that $X$ is Hausdorff and that $\mathcal{F}$ converges to $x$ and $y$ s.t. $x\neq y$. Let $U,V$ be the disjoint open neighborhoods of $x,y$ and by convergence, there exists $W\in \mathcal{F}$ s.t. $W\subseteq U$ and $W\subseteq V$. (this is given as the filter is closed under intersection). As $\varnothing\notin \mathcal{F}$, we have that $U\cap V\neq \varnothing$, which is a contradiction.
2. Let $x,y\in X$ with $x\neq y$. We first consider the following set: $$\mathcal{F}:=\{\varnothing\neq A\subseteq X: A\supseteq V\cap W \text{ for some open neighborhood }V\text{ of }x \text{ and }W\text{ of }y \}$$Then, by definition $\varnothing \notin \mathcal{F}$ and for $A\in \mathcal{F}$ and $A\subseteq B$, $B\in \mathcal{F}$ with the same $V\cap W$. Lastly, consider $A,B\in \mathcal{F}$ with $V_{1},W_{1}$ and $V_{2},W_{2}$ as open neighborhoods. Then, $V_{1}\cap V_{2}$, $W_{1}\cap W_{2}$ are open neighborhoods of $x,y$ respectively and $A \cap B\supseteq (V_{1}\cap V_{2})\cap(W_{1}\cap W_{2})$. Therefore, $A\cap B\in \mathcal{F}$ and $\mathcal{F}$ is a filter. 
   
   Assume for all open neighborhoods $V,W$ of $x,y$ respectively, we have $V\cap W\neq \varnothing$. Then, for all open neighborhood $U$ of $x$, then $\varnothing \neq U\cap W\subseteq U$ for any open neighborhood $W$ of $y$. It follows that $\mathcal{F}$ converges to $x$ and by symmetry to $y$. This is a contradiction to $\mathcal{F}$ having a unique limit. Therefore, $X$ is Hausdorff.
---
> [!def] Problem 3
> Let $X,Y$ be topological spaces. Define a topology on $X\times Y$ by saying that $U\subseteq X\times Y$ is open if and only if, for every $(x,y)\in U$, there exist neighborhoods $V$ and $W$ of $x$ and $y$ respectively such that $V\times W\subseteq U$ (this is the product topology).
> 1. Check that this is a topology on $X\times Y$.
> 2. Show that $X$ is a Hausdorff space if and only if the diagonal $$\Delta:=\{ (x,x)|x\in X \}\subseteq X\times X$$ is closed in $X\times X$ (with the above topology for $Y=X$).
> 
> In the following points, let $Y$ be a Hausdorff space.
>1. For any topological space $X$ and any continuous maps $f:X\to Y$ and $g:X\to Y$, show that the sets $$\{ (x,y):f(x)=g(y) \},\quad \{ x\in X:f(x)=g(x) \}$$ are closed in $X\times X$ and in $X$, respectively. 
>2. For any topological space $X$ and any continuous maps $f:X\to Y$ and $g:X\to Y$, show that if $f(x)=g(x)$ for all $x$ in a dense set, then $f=g$.
>3. For any topological space $X$ and any continuous map $f:X\to Y$ , show that the graph $$\text{graph}(f):=\{ (x,y) :y=f(x)\}$$ of $f$ is closed in $X\times Y$.

We have:
1. $\varnothing$ is open by definition. Further, $X\times Y$ is open by taking $X,Y$ as the neighborhoods. For a family of open sets $(U_{\lambda})_{\lambda\in \Lambda}$, we have that for $(x,y)\in \bigcup_{\lambda\in \Lambda}^{}U_{\lambda}$, there exists $\alpha\in \Lambda$ s.t. $(x,y)\in U_{\alpha}$ and there exists neighborhoods $V,W$ of $x,y$ respectively s.t. $$V\times W\subseteq U_{\alpha}\subseteq \bigcup_{\lambda\in \Lambda}^{}U_{\lambda}$$
	Similarly, for $U_{1},U_{2}$ open s.t. $U_{1}\cap U_{2}\neq \varnothing$, let $(x,y)\in U_{1}\cap U_{2}$. Then, there exists open neighborhoods $V_{1},W_{1}$ and $V_{2},W_{2}$  s.t. $V_{1}\cap V_{2}$ and $W_{1}\cap W_{2}$ are open neighborhoods of $x$ and $y$ respectively and: $$(V_{1}\cap V_{2})\times(W_{1}\cap W_{2})\subseteq U_{1}\cap U_{2}$$ This shows that this is indeed a topology.
2. Assume $X$ is Hausdorff. We show that $U:=X\times X \backslash\Delta$ is open. Let $(x,y)\in U$. By definition $x\neq y$ and there exist disjoint open neighborhoods $V,W$ of $x,y$ respectively, i.e. $V\times W\subseteq X\times X \backslash \Delta$. 
   
   Conversely, assume that $\Delta$ is closed and let $x,y\in X$ with $x\neq y$. Then, $(x,y)\in X\times X \backslash \Delta$ and there exists open neighborhoods $V,W$ of $x,y$ respectively s.t. $V\times W\subseteq X \times X \backslash \Delta$, i.e. $V\cap W=\varnothing$. 
3. Let $x,y\in X$ s.t. $f(x)\neq g(y)$. Then, as $Y$ is Hausdorff, there exists $V,W\subseteq Y$ neighborhoods of $f(x),g(y)$ respectively s.t. $V\cap W=\varnothing$. Then, $f^{-1}(V)$ and $g^{-1}(W)$ are neighborhoods of $x,y$ respectively, s.t. $f^{-1}(V)\times g^{-1}(W)\subseteq X\times X \backslash\{ (a,b):f(a)=g(b) \}$. This shows that $\{ (x,y):f(x)=g(y) \}$ is closed.
   
   One can easily see from the definition of product topology that $X$ is homeomorphic to $\Delta$ w.r.t the subspace topology of the product topology. Then, as $$\{(x,x)\in X:f(x) =g(x)\}=\Delta \cap\{ (x,y):f(x)= g(y)  \}$$ is closed in $\Delta$, our set is closed in $X$.
4. Let $\overline{E}=X$ and for all $x\in E$, $f(x)=g(x)$. Now, let $y\in X$ and assume that $f(y)\neq g(y)$. As $Y$ is Hausdorff, then we have disjoint open neighborhoods $V,W$ of $f(y)$ and $g(y)$ respectively. Consequently, $f^{-1}(V)$ and $g^{-1}(W)$ are open neighborhoods of $y$. Therefore, $f^{-1}(V)\cap g^{-1}(W)$ is an open neighborhood of $y$. By the density of $E$, then there exists $x\in f^{-1}(V)\cap g^{-1}(W)$ s.t. $f(x)=g(x)\in V\cap W$, which is a contradiction.
5. Let $(x,y)\in X\times Y$ s.t. $f(x)\neq y$. Then, there exist disjoint open neighborhoods $V,W$ of $f(x)$ and $y$ respectively. Therefore, $f^{-1}(V)$ is an open neighborhood of $x$ and $f^{-1}(V)\times W\subseteq X\times Y \backslash \text{graph}(f)$. Indeed if otherwise, there exists $f(a)=b\in V\cap W$ which is a contradiction. 
---
> [!def] Problem 4
> Let $X=\mathbb{R}$ with the cofinite topology.
> 1. Show that for every $x\neq y$ in $X$, there exists a neighborhood $U$ of $x$ such that $y\notin U$, but that $X$ is not Hausdorff.
> 2. Show that the graph of the identity map $X\hookrightarrow X$ is not closed in $X\times X$ (with the product topology).
> 3. Show that a function $f:X\to X$ is continuous if either $f$ is constant, or if the equation $f(x)=y$ has at most finitely many solutions for arbitrary $y\in \mathbb{R}$. In particular, any bijection $X\to X$ is continuous.
> 4. Find examples of two bijections $f:X\to X$ and $g:X\to X$ such that $f-g$ is not continuous.
> 5. Deduce examples showing that the properties of (3) and (4) of the previous exercise are not always true if $X$ is not Hausdorff.

We have: 
1. For $x,y\in X$ with $x\neq y$, $U:=X \backslash \{ y \}$ is an open neighborhood of $x$ s.t. $y\notin U$. However, assume that we have open neighborhoods $U,V$ of $x,y$ respectively. Then, $U,V$ are both non-empty and therefore,  $X \backslash(U\cap V)=(X \backslash U) \cup (X \backslash V)$ is finite. Therefore, $U\cap V \neq \varnothing$.
2. Assume it is closed. Then, the complement is open and for $x\neq y\in X$, there exist neighborhoods $V,W\subseteq X$ of $x,y$ respectively s.t. $V\times W\subseteq X\times X \backslash \text{graph}(\text{id})$. This implies that $V\cap W=\varnothing$, which is a contradiction to 1.
3. If $f$ is constant, i.e. $f\equiv a$ for some $a\in X$, then, $$f^{-1}(U)=\begin{cases}X&1\in U\\\varnothing&1\notin U\end{cases}$$Therefore, $f$ is continuous. Assume now that for any $y\in X$, $f(x)=y$ has finitely many solutions. Then, for $U\subseteq X$ open, if $U=\varnothing$, then $f^{-1}(\varnothing)=\varnothing$ and otherwise: $$X \backslash f^{-1}(U)=\{ x\in X:f(x)\in X \backslash U \}=\bigcup_{y\in X \backslash U}^{}\{x\in X:f(x)= y  \}$$which is finite as a finite union of finite sets. This includes bijections as there exists exactly one solution to $f(x)=y$ for any $y\in X$.
4. Let for $f,g:X\to X$ with $g:x\mapsto x$ and $$f(x):=\begin{cases}x&x<0\\2x&x\geq 0\end{cases}$$Then, both are bijections and: $$(f-g)(x)=\begin{cases}0&x\leq 0\\x&x >0\end{cases}$$However, $f-g$ is not continuous as $(f-g)^{-1}(\{ 0 \})=(-\infty,0]$ is not closed. 
---
> [!def] Problem 5
> Let $X$ be a topological space. 
> 1. If $A_{1}$ and $A_{2}$ are compact subsets of $X$, show that $A_{1}\cup A_{2}$ is compact.
> 2. If $X$ is Hausdorff, show that $A_{1}\cap A_{2}$ is compact.

We have:
1. Let $(U_{i})_{i\in I}$ be an open cover of $A_{1}\cup A_{2}$. Then, it is also an open cover of $A_{1}$ and $A_{2}$ and there exist finite sets $J_{1},J_{2}\subseteq I$ s.t. $A_{1}\cup A_{2}\subseteq \bigcup_{i\in J_{1}\cup J_{2}}^{}U_{i}$. Therefore, $A_{1}\cup A_{2}$ is compact.
2. Let $(U_{i})_{i\in I}$ be an open cover of $A_{1}\cap A_{2}$. As $X$ is Hausdorff, $A_{1},A_{2}$ are closed and $\{ (X \backslash A_{1})\cup U_{i} \}_{i\in I}$ is an open cover of $A_{2}$ as: $$A_{2}\subseteq (X \backslash A_{1})\cup (A_{1}\cap A_{2})\subseteq \bigcup_{i\in I}^{}(X \backslash A_{1})\cup U_{i}$$Therefore, there exists $J\subseteq I$ s.t. $A_{2}\subseteq \bigcup_{i\in J}(X \backslash A_{1})\cup U_{i}$. It follows that $A_{1}\cap A_{2}\subseteq \bigcup_{i\in J}^{}U_{i}$. 
---
> [!def] Problem 6
> Let $X$ and $Y$ be topological spaces, with $Y$ compact and Hausdorff. Let $f:X\to Y$ be an arbitrary map such that $\text{graph}(f)$ is closed in $X\times Y$.
> 1. Let $x_{0}\in X$ and denote $y_{0}:= f(x_{0})$. For any $y\neq y_{0}$ in $Y$, show that there exist open neighborhoods $U_{y}$ of $x_{0}$ and $V_{y}$ of $y$ such that $$(U_{y}\times V_{y})\cap \text{graph}(f)=\varnothing$$
> 2. Let $V$ be an open neighborhood of $y_{0}$ in $Y$. Deduce from (1) that there exists an open neighborhood $U$ of $x_{0}$ such that $(U \times(Y \backslash V))\cap \text{graph}(f)=\varnothing$.
> 3. Prove that $f$ is continuous.

We have:
1. We know that for any $y\neq y_{0}$ in $Y$, $(x_{0},y)\notin \text{graph}(f)$. Therefore, by the definition of product topology, there exists open neighborhoods $U_{y}$