#Series #Topology 

> [!def] Problem 1
> Let $X$ be a topological space.
> 1. If $X$ is Hausdorff, show that $\{ x \}$ is closed in $X$ for all $x\in X$.
> 
> We define a set $\tilde{X}:=X\cup \{ \infty \}$, where $\infty$ is any mathematical object not in $X$. We define a topology on $\tilde{X}$ so that $U$ is open if and only if either $U=\varnothing$, or $U=V\cup \{ \infty \}$ for some open set $V\subseteq X$.
> 1. Check that this defines a topology, and that the inclusion map $X\hookrightarrow \tilde{X}$ is continuous.
> 2. Show that the closure of $\{ \infty \}$ is equal to $\tilde{X}$, i.e., that the single point $\infty$ is dense in $\tilde{X}$.

We have that: 
1. Let $y\in \overline{\{ x \}}$. Then, for every neighborhood $U$ of $y$, $x\in U$. This implies that $x=y$ as $X$ is Hausdorff. Therefore, $\{ x \}$ is closed.
2. It is trivial to see that $\varnothing,\tilde{X}$ are open. Let $\{ U_{i} \}_{i\in I}$ now be open sets in $\tilde{X}$. Wlog we may assume that none of these are empty sets. Therefore, $\bigcup_{i\in I}^{}U_{i}=\bigcup_{i\in I}^{}V_{i}\cup \{ \infty \}=\left( \bigcup_{i\in I}^{}V_{i} \right)\cup \{ \infty \}$ which is open. Similarly, for $U_{1},U_{2}$ open, if one of them is $\varnothing$, the intersection is open. If both are non-empty, then $U_{1}\cap U_{2}=(V_{1}\cap V_{2})\cup \{ \infty \}$ which is open.
   
   Now, for any open $U\subseteq \tilde{X}$, the preimage of the inclusion is empty if $U$ is empty or $V$ if $U=V\cup \{ \infty \}$This shows that the inclusion is continuous.
3. Let $y\in X$ and $U$ an open neighborhood of $y$ in $\tilde{X}$. Then, by definition, $\infty\in U$. Therefore, $y\in \overline{\{ \infty \}}$. As $y$ was arbitrary, this proves the statement.
---
> [!def] Problem 2
> Let $X$ be a compact Hausdorff space. Let $(C_{n})_{n}$ be a sequence of closed subsets of $X$ with empty interior for all $n$. Denote $C:=\bigcup_{n\geq 1}^{}C_{n}$. Let $U$ be a non-empty open subset of $X$.
> 1. Let $x\in X$ and $A\subseteq X$ be a closed subspace with $x\notin A$. Show that there exists a neighborhood $U$ of $x$ s.t. $\overline{U}\cap A=\varnothing$.
> 1. Let $U_{0}=U$. Show that one can construct by induction a sequence of open set $(U_{n})_{n\geq 1}$ such that, for all $n\geq 1$, the properties $$\begin{cases}\overline{U}_{n}\cap C_{n}=\varnothing\\\overline{U}_{n}\subseteq U_{n-1}\end{cases}$$ are satisfied.
> 2. Show that: $$\bigcap_{n\geq 1}^{}\overline{U_{n}}\neq \varnothing$$and deduce that $U\cap(X \backslash C)\neq\varnothing$.
> 3. Deduce that the interior of $C$ is empty.
> 4. Show that if $(V_{n})$ is a sequence of dense open sets in $X$, the intersection $$\bigcap_{n\geq 1}^{}V_{n}$$ is still dense in $X$.
> 5. Give an example of a sequence $(V_{n})_{n}$ of dense open sets in the compact space $[0,1]$ such that the intersection of the $V_{n}$’s is not open.

We have: 
1. Let $y\in A$. Then, $x\neq y$ and as $X$ is Hausdorff, there exists disjoint open neighborhoods $U_{y},V_{y}$ of $x$ and $y$ respectively. As $A$ is a closed subspace, $A$ is compact and $\{ V_{y} \}_{y\in A}$ is an open cover of $A$. Therefore, there exists a finite set $J\subseteq A$ s.t. $\bigcup_{y\in J}^{}V_{y}\supseteq A$. Let $U:=\bigcap_{y\in J}^{}U_{y}$ which is an open neighborhood of $x$. Then, we have that $U\cap \bigcup_{y\in J}^{}V_{j}=\varnothing$ and as both sets are open, $\overline{U}\cap A \subseteq \overline{U}\cap \bigcup_{y\in J}^{}V_{j}=\varnothing$. 
2. For each $n$, we define $U_{n}$ as follows: As $C_{n}$ has an empty interior, there exists $x_{n}\in U_{n-1} \backslash C_{n}$. Then, $x_{n}\notin C_{n}\cup \partial U_{n-1}$ which is a closed set. Therefore, there exists a neighborhood $U_{n}$ of $x$ s.t. $\overline{U_{n}}\cap (C_{n}\cup \partial U_{n-1})=\varnothing$. As $x\in U_{n-1}$, $U_{n}$ meets the required conditions.
3. Assume that $\bigcap_{n\geq 1}^{}\overline{U}_{n}=\varnothing$. Then, $(X \backslash \overline{U}_{n})_{n}$ is an open cover of $X$ and there exists a finite $J$ s.t. $\bigcup_{n\in J}^{}(X \backslash \overline{U}_{n})=X$. In other words, $\bigcap_{n\in J}^{}\overline{U}_{n}=\varnothing$, which is a contradiction as $(U_{n})_{n}$ is a decreasing sequence of non-empty open sets. Furthermore, $$U\cap(X \backslash C)=U\cap \bigcap_{n\geq 1}^{}(X \backslash C_{n})\supseteq\bigcap_{n\geq 1}^{}\overline{U}_{n}\neq \varnothing$$
4. We have that for any non-empty open set $U$, $U\not\subseteq C$. Therefore, $C^\circ=\varnothing$. 
5. Let $C_{n}:=X \backslash V_{n}$. Then, $C_{n}$ is closed and $C_{n}^\circ=(X \backslash V_{n})^{\circ}=X\backslash X=\varnothing$. Therefore, the interior of $C:=\bigcup_{n\geq 1}^{}C_{n}$ is empty and: $$\overline{\bigcap_{n\geq 1}^{}V_{n}}=\overline{X\backslash C}=X \backslash C^\circ =X$$
6. Let $C_n:=\{ x\in[0,1]:nx\in \mathbb{Z} \}$ for $n\geq 1$. Then, $C_{n}$ is closed as a finite union of singleton sets ($X$ is Hausdorff) and by setting $V_{n}:= [0,1] \backslash C_{n}$, we have our desired sequence as $\bigcup_{n\geq 1}^{}C_{n}=[0,1]\cap \mathbb{Q}$, which is not closed in $\mathbb{R}$. 
---
> [!def] Problem 3
> Let $X=\mathbb{R}\times \{ -1,1 \}$ with the product topology (where $\{ -1,1 \}$ has the discrete topology). We define an equivalence relation on $X$ so that $(x,1)\sim(x,-1)$ if $x\neq 0$, and there are no further equivalences except equality. (In particular, the equivalence classes $o_{+}$ and $o_{-}$ of the points $(0,1)$ and $(0,-1)$ have only one element, and give different points in $Y$.) 
> 
> Let $Y=X / \sim$ be the space of equivalence classes. Let $p:X\to Y$ be the quotient map; define a topology $\mathcal{T}$ on $Y$ so that $U\subseteq Y$ is open if and only if $p ^{-1}(U)\subseteq X$ is open.
> 1. Show that this defines a topology on $Y$. 
> 2. For $\varepsilon\in\{ -1,1 \}$, define a map $i_{\varepsilon}:\mathbb{R}\to Y,x\mapsto[(x,\varepsilon)]_{\sim}$. Show that $i_{\varepsilon}$ is continuous and injective. 
> 3. Show that $i_{+}$ has image $Y \backslash \{ o_{-} \}$ and gives a homeomorphism $\mathbb{R}\to Y \backslash \{ o_{-} \}$. Similarly, $i_{-}$ defines a homeomorphism $\mathbb{R}\to Y \backslash \{ o_{+} \}$. 
> 4. Show that $Y$ is a topological manifold of dimension 1 (i.e., for every $y\in Y$, there exists an open neighborhood of $y$ which is homeomorphic to an open subset of $\mathbb{R}$). 
> 5. Show that every $y\in Y$ has a countable fundamental system of neighborhoods. 
> 6. Show that $Y$ is not Hausdorff. In particular, find a sequence $(y_{n})_{n}\subseteq Y$ which converges to both $o_{+}$ and $o_{-}$.

We have:
1. $\varnothing,Y$ are trivially open. For $U_{1},U_{2}\subseteq Y$ open, $p ^{-1}(U_{1}\cap U_{2})=p ^{-1}(U_{1})\cap p ^{-1}(U_{2})$ which is open in $X$. Lastly, for open sets $(U_{i})_{i\in I}$ in $Y$, $p ^{-1}\left( \bigcup_{i\in I}^{}U_{i} \right)=\bigcup_{i\in I}^{}p ^{-1}(U_{i})$ which is open. 
2. Let $U\subseteq Y$ open. For $\varepsilon\in\{ -1,1 \}$, we define $\varphi_{\varepsilon}:\mathbb{R}\to \mathbb{R}\times \{ -1,1 \},x\mapsto(x,\varepsilon)$. We show that $\varphi_{\varepsilon}$ is continuous: For $U\subseteq \mathbb{R} \times \{ -1,1 \}$ open and non-empty, if for all $(x,a)\in U$, $a=-\varepsilon$ then $\varphi_{\varepsilon}^{-1}(U)=\varnothing$. Otherwise, there exists $(x,1)\in U$ and an open neighborhood $V$ of $x$ in $\mathbb{R}$ with $\varphi_{\varepsilon}^{-1}(U)=V$. As $p$ is continuous by definition of the quotient topology and $i_{\varepsilon}=p(\varphi_{\varepsilon})$, $i_{\varepsilon}$ is continuous. For injectivity, if $x\neq y\in \mathbb{R}$, then $(x,\varepsilon)\not\sim(y,\varepsilon)$.
3. Notice that by definition $Y=\{ [(x,+1)]_{\sim}:x\neq 0 \}\cup \{ o_{+},o_{-} \}$. For $0\neq x\in \mathbb{R}$, $i_{+}(x)=[(x,+1)]_{\sim}$ and $i_{+}(0)=o_{+}$. It suffices to show that $i_{+}$ is open. Let $U\subseteq \mathbb{R}$ be non-empty and let $(x,\varepsilon)\in$ $p ^{-1}(i_{+}(U))$. Then, $[(x,\varepsilon)]_{\sim}\in i_{+}(U)$. If $x=0$, $\varepsilon=1$ and $U\times \{ 1 \}\subseteq p ^{-1}(i_{+}(U))$ is an open neighborhood. Similarly, if $x\neq 0$, then $U\times \{ -1,1 \}\subseteq p ^{-1}(i_{+}(U))$ is an open neighborhood. This shows that $i_{+}$ is open. $i_{-}$ follows from symmetry,
4. Let $y\in Y$. If $y=o_{+}$, then, $i_{+}^{-1}$ is such a homeomorphism and if $y\neq o_{-}$, then take $i_{-}^{-1}$.
5. This follows from the fact that $Y$ is a topological manifold and $\mathbb{R}$ is a metric space.
6. Consider $\left( \left[ \left( \frac{1}{n},1 \right) \right]_{\sim} \right)_{n}$. Let $U\subseteq Y$ be an open neighborhood of $o_{+}$. Then, $$i_{+}\left(  \lim_{ n \to \infty }i_{+}^{-1}\left( \left[ \left( \frac{1}{n},1 \right) \right]_{\sim} \right) \right)=i_{+}\left( \lim_{ n \to \infty } \frac{1}{n} \right)=o_{+}$$where the sequence also converges to $o_{-}$ by symmetry. 
---
> [!def] Problem 4
> Let $X$ be a compact topological space. We denote by $C(X)$ the set of continuous functions $f:X\to \mathbb{C}$, where $\mathbb{C}$ has the euclidean topology. 
> 1. Show that $C(X)$ is a commutative ring, with addition given by $(f+g)(x)=f(x)+g(x)$, multiplication by $(fg)(x)=f(x)g(x)$ and neutral element for multiplication the constant function $1$.
> 
> Let $I\subseteq C(X)$ be an ideal. 
> 1. Show that the function $x\mapsto \left| f(x) \right|^{2}$ is in $I$ for all $f\in I$.
> 2. Show that $m_{x_{0}}:=\{ f\in C(X):f(x_{0})=0 \}$ is an ideal whenever $x_{0}\in X$.
> 3. Show that if there exists a function $f\in I$ such that $f(x)\neq 0$ for all $x\in X$, then $I=C(X)$.
> 4. Suppose there is no $x_{0}$ such that $I\subseteq m_{x_{0}}$. Deduce that for every $x\in X$, there exists an open neighborhood $U_{x}$ of $x$ and a function $f_{x}\in I$ such that $f_{x}(y)\neq 0$ for all $y\in U_{x}$.
> 5. Deduce that if there is no $x_{0}$ such that $I\subseteq m_{x_{0}}$, then $I=C(X)$.
> 6. Show that $I$ is a maximal ideal if and only if $I=m_{x_{0}}$ for some $x_{0}\in X$.

We have:
1. Continuous functions are closed under pointwise addition and multiplication. The multiplicative associativity, identity and distributivity all follows from that of $\mathbb{C}$.
2. For $f\in I$, we have that $\overline{f}\in C(X)$. Therefore, $\left| f \right|^{2}=f\overline{f}\in I$. 
3. For $f\in m_{x_{0}}$ and $g\in C(X)$, $(fg)(x)=f(x)g(x)=0$. Therefore, $fg\in m_{x_{0}}$.
4. If there exists such a function $f$, then $f$ is a unit as $\frac{1}{f}\in C(X)$ is well-defined everywhere on $X$. This shows that $I=C(X)$.
5. Assume that there exists $x\in X$ s.t. for all open neighborhoods $U_{x}$ and functions $f_{x}\in I$ that $f_{x}|_{U_{x}}\equiv 0$. Then clearly, $I\subseteq m_{x}$. 
6. As $X$ is compact and $(U_{x})_{x}$ is a covering of $X$, there exists finite $J\subseteq X$ s.t. $\bigcup_{x\in J}^{}U_{x}=X$. Notice that $\left| f_{x} \right|^{2}\in I$ for all $x\in J$. Therefore, $\sum_{x\in J}^{}\left| f_{x} \right| ^{2}\in I$ is a function that does not take 0 as value. Therefore, $I=C(X)$.
7. Let $I=m_{x_{0}}$ for some $x_{0}\in X$ and $I\subsetneq J$. Then, there exists $f\in J \backslash I$, i.e. $f(x_{0})\neq 0$. Therefore, there is no $y\in X$ s.t. $J\subseteq m_{y}$ and $J=C(X)$. Conversely assume that $I\neq m_{x_{0}}$ for all $x_{0}\in X$. If $I\subsetneq m_{x_{0}}$ for some $x_{0}\in X$ then $I$ is not maximal. Otherwise there is no $x_{0}$ s.t. $I\subseteq m_{x_{0}}$, which means $I=C(X)$.
---
