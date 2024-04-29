#Definition #LieGroups 

> [!definition]
> A [[topological group]] $G$ is ***locally compact***, if the underlying [[topological space]] is [[Locally Compact Space|locally compact]].
---
##### Properties
> [!lemma] Lemma 1
> Let $\{ G_{\alpha} \}_{\alpha\in A}$ be a collection of Hausdorff [[Topological Group|topological groups]]. Then, 
> 1. $\prod_{\alpha\in A}^{}G_{\alpha}$ is compact if and only if $G_{\alpha}$ is compact for all $\alpha\in A$.
> 2. $\prod_{\alpha\in A}^{}G_{\alpha}$ is locally compact if and only if $G_{\alpha}$ is locally compact for all $\alpha\in A$ and $G_{\alpha}$ is compact for all except finitely many $\alpha\in A$.
---
##### Locally Compact Hausdorff Groups
> [!lemma] Lemma E1
> Let $G$ be locally compact Hausdorff, then:
> 1. $A,B\subseteq G$ is compact then $AB$ is compact.
> 2. for all neighborhood $V$ or $e$, there exists an open neighborhood $ U$
---
##### Examples
> [!h] Example 1 (Elementary Topological Groups)
> We have:
> 1. Any group $G$ w.r.t the discrete topology is locally compact Hausdorff.
> 2. $(\mathbb{R}^n,+)$ w.r.t the Euclidean topology is locally compact Hausdorff.
> 3. $\mathbb{R}^{*},\mathbb{C}^{*}$ is locally compact Hausdorff.
> 4. [[General Linear Group|$\text{GL}(n,\mathbb{R})$]] is locally compact Hausdorff by [[Locally Compact Hausdorff Space|Lemma 4]] as it is open in $\text{M}_{n,n}(\mathbb{R})$.
---
> [!h] Example 2
> Let $M$ be a [[topological manifold]] of dimension $m\geq 1$. Then, $\text{Homeo}(M)$ is a topological group but not locally compact.

> [!proof]-
> We will show that $\text{Homeo}(M)$ is not locally compact for any compact manifold $M$. Note that we can think of $M$ as a compact metric space $(M,d)$ by Urysohn’s metrization theorem. In the case when $M$ is a smooth manifold this is even easier to see by endowing it with a Riemannian metric. 
> 
> This puts us now in the favorable position of being able to identify the compact-open topology on $\text{Homeo}(X)$ with the topology of uniform convergence. We denote by $$d_{\infty}(f,g):=\sup\{ d(f(x),g(x)): x\in M \}$$
>  the metric of uniform convergence on $\text{Homeo}(M)$. Further denote by $B^\infty_{<r}(f)\subseteq\text{Homeo}(M)$ the ball of radius $r>0$ about a homeomorphism $f\in \text{Homeo}(M)$. 
>  
>  In order to show that $\text{Homeo}(M)$ is not locally compact, for every $\varepsilon>0$, we will construct $(f_{k})_{k}\subseteq B^\infty_{<\varepsilon}(\text{id})$ with no convergent subsequence.
>  
>  Let $B:=B^\infty_{<\varepsilon}(\text{id})$ and $x_{0}\in M$. Choose a chart $(\varphi,U)$ s.t.
>  1. $U\subseteq B_{<\varepsilon /2}(x_{0})$ and 
>  2. $\varphi(x_{0})=0$
>  
>  Consider the following homeomorphisms: $$\begin{array}{cccc} {\psi_{k}:}&{B_{\leq 1}(0)}\subseteq \mathbb{R}^m&\to&{B_{\leq 1}(0)\subseteq \mathbb{R}^m}\\&{x} &\mapsto & {\|x\|^kx} \end{array}{}$$which fix $0\in \mathbb{R}^m$ and the boundary $\partial B_{<1}(0)\subseteq \mathbb{R}^m$ pointwise. Then, $\psi_{k}\to \psi_{\infty}$ pointwise where: $$\psi_{\infty}(x)=\begin{cases}x&x\in \partial B_{<1}(0)\\0&\text{otherwise}\end{cases}$$
>  
>  Now, define $f_{k}:M\to M$: $$f_{k}(x):=\begin{cases}x&x\notin \varphi ^{-1}(B_{\leq1}(0))\\\varphi ^{-1}(\psi_{k}(\varphi(x)))&x\in \varphi ^{-1}(B_{\leq1}(0))\end{cases}$$Then, $f_{k}\in \text{Homeo}(M)$ as $\varphi ^{-1}\circ\psi_{k}\circ\varphi:\varphi ^{-1}(B_{\leq 1}(0))\to\varphi ^{-1}(B_{\leq 1}(0))$ is a homeomorphism and $f_{k}$ is $\text{id}$ everywhere else. Further they coincide on the boundary $\varphi ^{-1}(\partial B_{<1}(0))$.
>  
>  Further, we have that $f_{k}(B_{<\varepsilon / 2}(x_{0}))=B_{<\varepsilon / 2}(x_{0})$ and $f_{k}(x_{0})=x_{0}$. Therefore, for every $x\in B_{\varepsilon / 2}(x_{0})$:$$d(f_{k}(x),x)\leq d(f_{k}(x),f_{k}(x_{0}))+d(x_{0},x)<\varepsilon$$This means, $(f_{k})_{k}\subseteq B^\infty_{<\varepsilon}(\text{id})$. However, $f_{k}\to f_{\infty}$ pointwise, where: $$f_{\infty}(x):=\begin{cases}x&x\notin \varphi ^{-1}(B_{\leq1}(0))\\x_{0}&x\in \varphi ^{-1}(B_{\leq1}(0))\end{cases}$$which is not even continuous. Therefore, $(f_{k})_{k}$ cannot have a convergent subsequence and $\text{Homeo}(M)$ is not locally compact.

 
---
> [!h] Example 3
> Let $(X,d)$ be a [[proper metric space]]. Then, 
> 1. $\text{Iso}(X)$ is locally compact.
> 2. $\text{Iso}(X)$ is compact, if $X$ is compact.

> [!proof]-
> We have: 
> 1. 
> 1. Assume $X$ is compact. The [[compact-open topology]] on $\text{Homeo}(X)$ coincides with the topology induced by the metric of uniform convergence: $$d_{\infty}(f,g)=\sup\{ d(f(x),g(x)): x\in X \}$$ By Arzelà-Ascoli Theorem, $\text{Iso}(X)$ is compact if and only if $\text{Iso}(X)$ is equicontinuous and closed.
> 	
> 	The equicontinuity is clear as we have isometries. For closedness, let $f\in C(X,X)$ and $(f_{n})\subseteq \text{Iso}(X)$ s.t. $f_{n}\to f$. For $x,y\in X$, we have: $$\begin{align}0&\leq \left| d(f(x),f(y))-d(x,y) \right| \\&=\left| d(f(x),f(y))-d(f_{n}(x),f_{n}(y)) \right|\\&\leq \left| d(f(x),f(y))-d(f_{n}(x),f(y)) \right| +\left| d(f_{n}(x),f(y))-d(f_{n}(x),f_{n}(y)) \right| \\&\leq d(f(x),f_{n}(x))+d(f(y),f_{n}(y)) \end{align}$$which converges to $0$. Therefore, $f\in \text{Iso}(X)$ and $\text{Iso}(X)$ is compact.
---
> [!h] Example 4
> For $\text{GL}(n,\mathbb{R})$, 
> 1. $\text{A},\text{UT}(n,\mathbb{R}),\text{O}(n)$ from [[Topological Group|Example 5]] are locally compact.
> 2. $\text{O}(n)$ is compact.
> 3. $\text{O}(p,q)\subseteq \text{GL}(n,\mathbb{R})$ is compact if $p=n$ or $q=n$. 
> 4. $\text{O}(1,1)$ is non-compact.
> 5. $\text{O}(p,q)$ is non-compact for $p\geq 1,q\geq 1$. 

> [!proof]-
> We have:
> 1. They are closed in $\text{GL}(n,\mathbb{R})$ and $\text{GL}(n,\mathbb{R})$ is locally compact.
> 2. Define the map: $$\begin{array}{cccc} {T:}&{\text{M}_{n,n}(\mathbb{R})}&\to&{\text{M}_{n,n}(\mathbb{R})}\\&{A} &\mapsto & {A^\top A} \end{array}{}$$Then, $\text{O}(n)= T^{-1}(\{ I \})$ and closed in $\text{M}_{n,n}(\mathbb{R})$. 
>    
>    Further, for $A\in \text{O}(n)$, it holds that $\sum_{i=1}^{n}\left\| A_{:,i} \right\|^{2}=n$. Therefore, $\text{O}(n)$ is bounded in $\text{M}_{n,n}(\mathbb{R})$. Therefore, $\text{O}(n)$ is compact by Heine-Borel.
>  3. $\text{O}(n,0)=\text{O}(0,n)=\text{O}(n)$.
>  4. As $\text{SO}(1,1)$ is a closed subgroup of $\text{O}(1,1)$, we will show that $\text{SO}(1,1)$ is not compact. First, notice that: $$\text{SO}(1,1)=\left\{ \left. \begin{bmatrix}x&y\\y&x\end{bmatrix}  \right| x^{2}-y^{2}=1,x,y\in \mathbb{R}\right\}$$The orbit of $e_{1}$ under $\text{SO}(1,1)$ is given as: 
>	``` tikz
>	\begin{document}
>	\begin{tikzpicture}[domain=-4:4] 
>	\draw[very thin,color=gray] (-4.1,-4.1) grid (3.9,3.9); 
>	\draw[->] (-4.2,0) -- (4.2,0) node[right] {$x$}; 
>	\draw[->] (0,-4.2) -- (0,4.2) node[above] {$y$}; 
>	\draw[color=red] plot ({sqrt(1+\x*\x)},\x);
>	\draw[color=red] plot (-{sqrt(1+\x*\x)},\x);
>	\end{tikzpicture} 
>	\end{document}
>	```
>	Therefore, one sees that the orbit is not compact. However, $$\begin{array}{cccc} {f:}&{\text{SO}(1,1)}&\to&{\mathbb{R}^{2}}\\&{A} &\mapsto & {Ae_{1}} \end{array}{}$$is a continuous function. This implies $\text{SO}(1,1)$ cannot be compact. Therefore, $\text{O}(1,1)$ is not compact.
>5. For $p,q\geq 1$, there is an injection: $$\begin{array}{cccc} {f:}&{\text{O}(1,1)}&\to&{\text{O}(p,q)}\\&{\begin{bmatrix}a&b\\c&d\end{bmatrix}} &\mapsto & {\begin{bmatrix}aI_{p}&bI_{p,q}\\cI_{q,p}&dI_{q}\end{bmatrix}} \end{array}{}$$

---
> [!h] Example 5
> For $\text{GL}$
