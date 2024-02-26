#Series #Topology 


> [!definition] Problem 1
> Let $X$ be a set. 
> 1. Show that the cofinite topology: $$\mathcal{T}_{\text{cof}}:=\{ U\subseteq X:X \backslash U\text{ is finite or empty} \}$$is a topology on $X$.
> 2. For what $X$ does the set of all finite subsets build a topology?

We have:
1. **Showing the cofinite topology is a topology**: 
    Firstly, we have that $\varnothing\in \mathcal{T}_{\text{cof}}$ and $X\in \mathcal{T}_{\text{cof}}$ as $X\backslash X=\varnothing$. 
    
    For the union of $\{ U_{\lambda} \}\subseteq \mathcal{T}_{\text{cof}}$,  wlog we can assume that $X \backslash U_{\lambda}$ is finite, as $\varnothing$ does not "add" anything to the union. Therefore, $X \backslash \bigcup_{\lambda\in \Lambda}^{}U_{\lambda}=\bigcap_{\lambda\in \Lambda}^{}X \backslash U_{\lambda}$, which is finite, and $\bigcup_{\lambda\in \Lambda}^{}U_{\lambda}$ is open. 
    
    For $U_{1},U_{2}\in \mathcal{T}_{\text{cof}}$, if any of them is empty, then the intersection is empty and thereby open. Otherwise, $X\backslash (U_{1}\cap U_{2})=(X \backslash U_{1})\cup(X \backslash U_{2})$ which is finite as a union of two finite sets. This proves the statement.
2. **Showing $X$ is finite if and only if the finite subsets build a topology**:
	Assume $X$ is finite. Then, the set of all finite subsets equals the discrete topology on $X$. Therefore, it builds a topology. 
	
	Conversely, if $X$ is infinite, the union of all singleton sets, which are open sets by definition, is not open and therefore it is not a topology.

---

> [!definition] Problem 2
>  Let $X$ be a set and $(Y,\mathcal{T}_{Y})$ a topological space. Let $f:X\to Y$ be any function. 
>  1. Show that $\mathcal{T}:=\{ f^{-1}(V)\subseteq X:V\in \mathcal{T}_{Y} \}$ is a topology on $X$.
>  2. Show that $f:(X,\mathcal{T})\to(Y,\mathcal{T}_{Y})$ is continuous.

We have:
1. Firstly, $\varnothing =f^{-1}(\varnothing)$ and $X=f^{-1}(Y)$. Therefore, $\varnothing,X\in \mathcal{T}$.
   
   For $\{ U_{\lambda} \}\subseteq \mathcal{T}$, then there exists $\{ V_{\lambda} \}\subseteq \mathcal{T}_{Y}$ s.t. $f^{-1}(V_{\lambda})=U_{\lambda}$. Then, $$\bigcup_{\lambda\in \Lambda}^{}U_{\lambda}=\bigcup_{\lambda\in \Lambda}^{}f^{-1}(V_{\lambda})=f^{-1}\left( \bigcup_{\lambda \in \Lambda}^{}V_{\lambda} \right) $$as $\bigcup_{\lambda\in \Lambda}^{}V_{\lambda}$ is open, $\bigcup_{\lambda\in \Lambda}^{}U_{\lambda}\in \mathcal{T}$.
   
   Similarly, for $U_{1},U_{2}\in \mathcal{T}$, $U_{1}\cap U_{2}=f^{-1}(V_{1})\cap f^{-1}(V_{2})=f^{-1}(V_{1}\cap V_{2})$ which is analogously open.
2. By definition, any open map $V\subseteq Y$ is mapped to $f^{-1}(V)\in \mathcal{T}$. 
---
> [!definition] Problem 3
> Let $X,Y$ be topological spaces. Let $(U_{\lambda})\subseteq \mathcal{T}_{X}$ s.t. $X=\bigcup_{\lambda\in \Lambda}^{}U_{\lambda}$ and $f:X\to Y$ any function. 
> 1. Show $U\subseteq X$ open if and only if $U_{\lambda}\cap U$ is open for all $\lambda\in \Lambda$.
> 2. Show that if $f$ is continuous, then $f|_{U_{\lambda}}$ is continuous for all $\lambda\in \Lambda$ w.r.t. the subspace topology.
> 3. Show the converse: if $f|_{U_{\lambda}}$ is continuous for all $\lambda\in\Lambda$, then $f$ is continuous.
> 4. Construct $X,Y,f$ and $\{ U_{\lambda} \}\subseteq \mathcal{T}_{X}$ s.t. $f|_{U_{\lambda}}$ is constant for all $\lambda\in \Lambda$ but $f$ is not.
> 5. For $\lambda\in \Lambda$, let $f_{\lambda}:U_{\lambda}\to Y$ be a continuous function w.r.t. the subspace topology. If $f_{\alpha}(x)=f_{\beta}(x)$ for all $\alpha,\beta\in \Lambda$ and $x\in U_{\alpha}\cap U_{\beta}$, then show that there exists a unique continuous function $f:X\to Y$ where $f_{\lambda}$ and $f$ coincide on $U_{\lambda}$.

We have:
1. If $U$ is open, $U_{\lambda}\cap U$ is open as an intersection of open sets. Conversely, $$U=U\cap X=U\cap \bigcup_{\lambda\in \Lambda}^{}U_{\lambda}=\bigcup_{\lambda\in \Lambda}^{}(U\cap U_{\lambda})$$which is open as a union of open sets. 
2. If $f$ is continuous, for an open set $U\subseteq Y$, $(f|_{U_{\lambda}})^{-1}(U)=f^{-1}(U)\cap U_{\lambda}$ which is open in the subspace topology, for all $\lambda\in \Lambda$.
3. Assume $f|_{U_{\lambda}}$ is open for all $\lambda\in \Lambda$. Then, for open $U\subseteq Y$, $(f|_{U_{\lambda}})^{-1}(U)=f^{-1}(U)\cap U_{\lambda}$ is open for all $\lambda\in \Lambda$. Therefore, by 1, $f^{-1}(U)$ is open.
4. Let $U_{1},U_{2}$ be two disjoint open sets in some topological space $Z$. Then, we let $X=U_{1}\sqcup U_{2}$, $Y=\mathbb{R}$, $$f(x)=\begin{cases}0&x\in U_{1}\\1&x\in U_{2}\end{cases}$$
5. For $x\in X$, let $\lambda(x)\in \Lambda$ s.t. $x\in U_{\lambda}$ with ties arbitrarily broken. Then, we let: $$\begin{array}{cccc} {f:}&{X}&\to&{Y}\\&{x} &\mapsto & {f_{\lambda(x)}(x)} \end{array}{}$$This is a well-defined function as $f_{\lambda}$ coincide on the intersection.
	1. **Showing that $f$ is continuous**:
		For all $\lambda\in \Lambda$ and $x\in U_{\lambda}$, $f(x)=f_{\lambda}(x)$, i.e. $f|_{U_{\lambda}}=f_{\lambda}$. Therefore, $f|_{U_{\lambda}}$ is continuous for all $\lambda\in \Lambda$ and by 3, $f$ is continuous.
	2. **Showing $f$ is unique**:
		Assume that there exists $g:X\to Y$ s.t. $g\neq f$ and $g|_{U_{\lambda}}=f_{\lambda}$ for all $\lambda\in \Lambda$. Then, there exists $x\in X$ s.t. $g(x)\neq f(x)$. However, $g(x)=f_{\lambda(x)}(x)=f(x)$ which is a contradiction.
---
> [!definition] Problem 4
> Let $X$ be a topological space.
> 1. If $X$ is a metric space, show that for all $x,y\in X$ with $x\neq y$, there exists open sets $U,V\subseteq X$ s.t. $x\in U,y\in V$ and $U\cap V=\varnothing$. 
> 2. Show that when $X$ is an infinite set with the cofinite topology, then the separation property does not hold for $X$.

We have that:
1. Let $X$ be a metric space. Then, for $x\neq y$, $d(x,y)=\varepsilon>0$. Consider:
	1. $U=B_{<\varepsilon / 4}(x):=\{ z\in X:d(z,x)<\varepsilon / 4 \}$ which contains $x$
	2. $V=B_{<\varepsilon / 4}(y):=\{ z\in X:d(z,y)<\varepsilon / 4 \}$ which contains $y$
	Further, if $z\in U\cap V$, then, $d(x,y)\leq d(x,z)+d(z,y)<\varepsilon /2$ which is a contradiction. 
2. Let $x,y\in X$ and two open sets $U,V\subseteq X$ s.t. $x\in U$ and $y\in V$. Then, $X \backslash U,X \backslash V$ are finite and $X \backslash U\cup X \backslash V$ is finite. Therefore, $X \backslash(U\cap V)=X \backslash U \cup X \backslash V\neq X$. It follows that $U\cap V\neq \varnothing$. 
---
> [!definition] Problem 5
> Let $X=[-1,1]$ be a subspace of $\mathbb{R}$ with the subspace topology. Decide for the following sets if they are open, closed or neither in $X$.
> 1. $\{ x\in X: 1/2<\left| x \right|<1 \}$
> 2. $\{ x\in X: 1/2<\left| x \right|\leq1 \}$
> 3. $\{ x\in X: 1/2\leq\left| x \right|<1 \}$
> 4. $\{ x\in X: 1/2\leq\left| x \right|\leq1 \}$

We have:
1.  $X_{1}:=\{ x\in X: 1/2<\left| x \right|<1 \}$ is open in $\mathbb{R}$. Therefore, $X_{1}=X_{1}\cap X$ is open in $X$.
2. $X_{2}:=\{ x\in X: 1/2<\left| x \right|\leq1 \}=X \cap\{ x\in X: 1/2<\left| x \right|< 2 \}$. Therefore, $X_{2}$ is open in $X$.
3. $X_{3}:=\{ x\in X: 1/2\leq\left| x \right|<1 \}$ is not open as $x= 1/2$ does not have an open neighborhood contained in $X_{3}$. Similarly, $X \backslash X_{3}=\{ x\in X: \left| x \right|<1/2 \}\cup \{ 1,-1 \}$ is not open as there exists no open set $U$ that contains an open neighborhood of $1$ in $\mathbb{R}$ s.t. $U\cap X\subseteq X \backslash X_{3}$. Therefore, $X_{3}$ is neither open nor closed.
4. $X_{4}:=\{ x\in X: 1/2\leq\left| x \right|\leq1 \}$ is closed as $X \backslash X_{4}=\{ x\in X: \left| x \right|<1/ 2 \}$ is open in $\mathbb{R}$ and thereby in $X$. 
---
