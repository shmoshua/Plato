#Definition #Topology 
> [!definition]
> A [[Topological Space]] $(X,\mathcal{T})$ is ***Hausdorff***, if for all $x,y\in X$ with $x\neq y$, there exist disjoint open neighborhoods of $x,y$.
---
##### Properties
> [!lemma] Proposition 1 (Equivalent Conditions of Hausdorff)
> For a topological space $X$, TFAE:
> 1. $X$ is Hausdorff.
> 2. for every $x\in X$, $\bigcap_{U\in \mathcal{F}_{x}}^{}\overline{U}=\{ x \}$ where $\mathcal{F}_{x}$ is the [[Filter]] of all neighborhoods of $x$.
> 4. every convergent filter $\mathcal{F}$ on $X$ has a unique limit.
> 5. the diagonal $\Delta:=\{ (x,x): x\in X \}\subseteq X\times X$ is closed.

> [!proof]-
> We have:
> 1. (1=>2): Assume that $X$ is Hausdorff. Indeed, $\{ x \}\subseteq \bigcap_{x\in U}^{}\overline{U}$ is trivial. Let $y\in \bigcap_{x\in U}^{}\overline{U}$ and assume $y\neq x$. Then, there exist disjoint open neighborhoods $U,V$ of $x,y$, respectively. However, $y\in \overline{U}$ by assumption and it follows that $U\cap V\neq\varnothing$, which is a contradiction. This shows the inclusion.
> 2. (2=>1): Assume that the condition holds. We will show that $X$ is Hausdorff. Let $x,y\in X$ s.t. $x\neq y$. Then, as $\bigcap_{x\in U}^{}\overline{U}=\{ x \}$, there exists open $U\ni x$ s.t. $y\notin\overline{U}$, i.e. there exists an open neighborhood $V$ of $y$ s.t. $U\cap V=\varnothing$. This proves the statement.
> 3. (1=>3): Let $\mathcal{F}$ be a convergent filter to $x,y\in X$ where $x\neq y$. Let $U,V$ be the disjoint open neighborhoods of $x,y$ and by convergence, there exists $W\in \mathcal{F}$ s.t. $W\subseteq U$ and $W\subseteq V$. (this is given as the filter is closed under intersection). As $\varnothing\notin \mathcal{F}$, we have that $U\cap V\neq \varnothing$, which is a contradiction.
> 4. (3=>1): Let $x,y\in X$ with $x\neq y$. We first consider the following set: $$\mathcal{F}:=\{\varnothing\neq A\subseteq X: A\supseteq V\cap W \text{ for some open neighborhood }V\text{ of }x \text{ and }W\text{ of }y \}$$Then, by definition $\varnothing \notin \mathcal{F}$ and for $A\in \mathcal{F}$ and $A\subseteq B$, $B\in \mathcal{F}$ with the same $V\cap W$. Lastly, consider $A,B\in \mathcal{F}$ with $V_{1},W_{1}$ and $V_{2},W_{2}$ as open neighborhoods. Then, $V_{1}\cap V_{2}$, $W_{1}\cap W_{2}$ are open neighborhoods of $x,y$ respectively and $A \cap B\supseteq (V_{1}\cap V_{2})\cap(W_{1}\cap W_{2})$. Therefore, $A\cap B\in \mathcal{F}$ and $\mathcal{F}$ is a filter. 
>    
>    Assume for all open neighborhoods $V,W$ of $x,y$ respectively, we have $V\cap W\neq \varnothing$. Then, for all open neighborhood $U$ of $x$, then $\varnothing \neq U\cap W\subseteq U$ for any open neighborhood $W$ of $y$. It follows that $\mathcal{F}$ converges to $x$ and by symmetry to $y$. This is a contradiction to $\mathcal{F}$ having a unique limit. Therefore, $X$ is Hausdorff.
>  5. (1=>4): Assume $X$ is Hausdorff. We show that $U:=X\times X \backslash\Delta$ is open. Let $(x,y)\in U$. By definition $x\neq y$ and there exist disjoint open neighborhoods $V,W$ of $x,y$ respectively, i.e. $V\times W\subseteq X\times X \backslash \Delta$. 
>  6. (4=>1): assume that $\Delta$ is closed and let $x,y\in X$ with $x\neq y$. Then, $(x,y)\in X\times X \backslash \Delta$ and there exists open neighborhoods $V,W$ of $x,y$ respectively s.t. $V\times W\subseteq X \times X \backslash \Delta$, i.e. $V\cap W=\varnothing$. 
---
> [!lemma] Proposition 2
> Let $X$ be Hausdorff. Then, 
> 1. $\{ x \}$ is closed for all $x\in X$.

> [!proof]-
> We have:
> 1. Let $y\in \overline{\{ x \}}$. Then, for all $U\ni y$, $U\cap \{ x \}\neq\varnothing$ and $x\in U$. Therefore $y=x$, as $X$ is Hausdorff. Hence, $\{ x \}=\overline{\{ x \}}$.
---
##### Examples
> [!h] Example 1
> Any [[Metric Space]] is Hausdorff.

> [!proof]-
> Let $x\neq y$. Then, $\delta:=d(x,y)>0$. Therefore, $B_{< \delta /2}(x),B_{< \delta /2}(y)$ are the two desired open sets.
---
> [!h] Example 2
> The [[Topology of Pointwise and Uniform Convergence]] is Hausdorff.
---
###### Non-Hausdorff Spaces
> [!h] Non-example 1
> Let $X$ be infinite and: $$\mathcal{T}:=\{ U\subseteq X:X \backslash U\text{ is finite or }U=\varnothing \}$$Then, $(X,\mathcal{T})$ is not Hausdorff.

> [!proof]-
> Let $x,y\in X$ and $U\ni x$ open. Then, $X \backslash U$ is finite. Similarly, $V\ni y$ open with $X \backslash V$ finite. Then, $$X \backslash(U\cap V)=X \backslash U\cup X \backslash V$$which is finite. Therefore, $U\cap V\neq \varnothing$. 
---
> [!h] Non-example 2
> Let $X=\mathbb{R}$ with the [[Topological Space|cofinite topology]]. Further, let $f:X\to X$ continuous.
> 1. for every $x\neq y$ in $X$, there exists a neighborhood $U$ of $x$ such that $y\notin U$.
> 2. $X$ is not Hausdorff.
> 3. Either $f$ is constant, or the equation $f(x)=y$ has at most finitely many solutions for arbitrary $y\in \mathbb{R}$. In particular, any bijection $X\to X$ is continuous.
> 5. Find examples of two bijections $f:X\to X$ and $g:X\to X$ such that $f-g$ is not continuous.
> 6. Deduce examples showing that the properties of (3) and (4) of the previous exercise are not always true if $X$ is not Hausdorff.

> [!proof]-
>  We have:
>  1. For $x,y\in X$ with $x\neq y$, $U:=X \backslash \{ y \}$ is an open neighborhood of $x$ s.t. $y\notin U$. 
>  2. From Non-example 1.
>  3. If $f$ is constant, i.e. $f\equiv a$ for some $a\in X$, then, $$f^{-1}(U)=\begin{cases}X&1\in U\\\varnothing&1\notin U\end{cases}$$Therefore, $f$ is continuous. Suppose $f$ is not constant. Then the preimage of any point is never the whole $\mathbb{R}$, and hence must be a finite set by continuity as the proper closed sets are precisely the finite sets. This precisely means that the equation $f(x)=y$ has only finitely many solutions for any $y\in \mathbb{R}$. 
>     
>     Assume now that for any $y\in X$, $f(x)=y$ has finitely many solutions. Then, for $U\subseteq X$ open, if $U=\varnothing$, then $f^{-1}(\varnothing)=\varnothing$ and otherwise: $$X \backslash f^{-1}(U)=\{ x\in X:f(x)\in X \backslash U \}=\bigcup_{y\in X \backslash U}^{}\{x\in X:f(x)= y  \}$$which is finite as a finite union of finite sets. This includes bijections as there exists exactly one solution to $f(x)=y$ for any $y\in X$.
> 3. Let for $f,g:X\to X$ with $g:x\mapsto x$ and $$f(x):=\begin{cases}x&x<0\\2x&x\geq 0\end{cases}$$Then, both are bijections and: $$(f-g)(x)=\begin{cases}0&x\leq 0\\x&x >0\end{cases}$$However, $f-g$ is not continuous as $(f-g)^{-1}(\{ 0 \})=(-\infty,0]$ is not closed. 
---
> [!h] Non-Example 3
> Let $X=\mathbb{R}\times \{ -1,1 \}$. We define an equivalence relation on $X$ so that $(x,1)\sim(x,-1)$ if $x\neq 0$, and there are no further equivalences except equality. (In particular, the equivalence classes $o_{+}$ and $o_{-}$ of the points $(0,1)$ and $(0,-1)$ have only one element, and give different points in $Y$.) 
> 
> Let $p:X\to X / _\sim$ be the projection.
> 1. For $\varepsilon\in\{ -1,1 \}$, define a map $i_{\varepsilon}:\mathbb{R}\to Y,x\mapsto[(x,\varepsilon)]_{\sim}$. Then, $i_{\varepsilon}$ is continuous and injective. 
> 2. $i_{+}:\mathbb{R}\to(X / _{\sim}) \backslash \{ o_{-} \}$ and $i_{-}:\mathbb{R}\to(X / _{\sim}) \backslash \{ o_{+} \}$ are homeomorphisms.
> 3. $X / _{\sim}$ is locally homeomorphic to $\mathbb{R}$ but not Hausdorff.

> [!proof]-
> We have:
> 1. Let $U\subseteq Y$ open. For $\varepsilon\in\{ -1,1 \}$, we define $\varphi_{\varepsilon}:\mathbb{R}\to \mathbb{R}\times \{ -1,1 \},x\mapsto(x,\varepsilon)$. We show that $\varphi_{\varepsilon}$ is continuous: For $U\subseteq \mathbb{R} \times \{ -1,1 \}$ open and non-empty, if for all $(x,a)\in U$, $a=-\varepsilon$ then $\varphi_{\varepsilon}^{-1}(U)=\varnothing$. Otherwise, there exists $(x,1)\in U$ and an open neighborhood $V$ of $x$ in $\mathbb{R}$ with $\varphi_{\varepsilon}^{-1}(U)=V$. As $p$ is continuous by definition of the quotient topology and $i_{\varepsilon}=p(\varphi_{\varepsilon})$, $i_{\varepsilon}$ is continuous. For injectivity, if $x\neq y\in \mathbb{R}$, then $(x,\varepsilon)\not\sim(y,\varepsilon)$.
> 2. Notice that by definition $Y=\{ [(x,+1)]_{\sim}:x\neq 0 \}\cup \{ o_{+},o_{-} \}$. For $0\neq x\in \mathbb{R}$, $i_{+}(x)=[(x,+1)]_{\sim}$ and $i_{+}(0)=o_{+}$. It suffices to show that $i_{+}$ is open. Let $U\subseteq \mathbb{R}$ be non-empty and let $(x,\varepsilon)\in$ $p ^{-1}(i_{+}(U))$. Then, $[(x,\varepsilon)]_{\sim}\in i_{+}(U)$. If $x=0$, $\varepsilon=1$ and $U\times \{ 1 \}\subseteq p ^{-1}(i_{+}(U))$ is an open neighborhood. Similarly, if $x\neq 0$, then $U\times \{ -1,1 \}\subseteq p ^{-1}(i_{+}(U))$ is an open neighborhood. This shows that $i_{+}$ is open. $i_{-}$ follows from symmetry,
> 3. Let $y\in Y$. If $y=o_{+}$, then, $i_{+}^{-1}$ is such a homeomorphism and if $y\neq o_{-}$, then take $i_{-}^{-1}$.
>    
>    However, consider $\left( \left[ \left( \frac{1}{n},1 \right) \right]_{\sim} \right)_{n}$. Let $U\subseteq Y$ be an open neighborhood of $o_{+}$. Then, $$i_{+}\left(  \lim_{ n \to \infty }i_{+}^{-1}\left( \left[ \left( \frac{1}{n},1 \right) \right]_{\sim} \right) \right)=i_{+}\left( \lim_{ n \to \infty } \frac{1}{n} \right)=o_{+}$$where the sequence also converges to $o_{-}$ by symmetry. Therefore, $X / _\sim$ cannot be Hausdorff.
---
