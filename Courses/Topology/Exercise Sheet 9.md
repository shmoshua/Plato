#Series #Topology 

> [!def] Problem 1
> For $z\in \mathbb{C}$ and $r\geq 0$, we denote: $$C(z,r)=\{ w\in \mathbb{C}:\left| w-z \right| =r \}$$Let $X=[0,2]\subseteq \mathbb{R}$ and $Y=C(i,1)\cup C(-i,1)$. 
> 1. Show that the map $\varphi:X\to Y$ s.t. $$\varphi(t):=\begin{cases}i+\exp\left( 2i\pi\left( t-\frac{1}{4} \right) \right)&0\leq t\leq 1\\-i+\exp\left( 2i\pi\left( t-\frac{3}{4} \right) \right)&1\leq t\leq 2\end{cases}$$ is well-defined, and that it is continuous. 
> 2. Define an equivalence relation on $X$ with equivalence classes $\{ 0,1,2 \}$ and $\{ t \}$ for $t\in X \backslash \{ 0,1,2 \}$. Let $X':=X / \sim$ and $p:X\to X'$ the projection. Show that there is a continuous map $\tilde{\varphi}:X'\to Y$ s.t. $\tilde{\varphi}\circ p=\varphi$, and that $\tilde{\varphi}$ is continuous when $X'$ has the quotient topology.
> 3. Show that $\tilde{\varphi}$ is a homeomorphism.

We have:
1. For any $0\leq t\leq 1$, $\left| i-\varphi(t) \right|=1$ and $\varphi(t)\in C(i,1)$. Similarly, for $1\leq t\leq 2$, $\left| -i-\varphi(t) \right|=1$ and $\varphi(t)\in C(-i,1)$. Further, for $t=1$, $$i+\exp\left( \frac{3}{2}\pi i \right)=0=-i+\exp\left( \frac{1}{2}\pi i \right)$$Therefore, $\varphi$ is well-defined. The continuity follows from the continuity of $\exp$. 
2. Let $\tilde{\varphi}:X'\to Y$ be defined as: $$\tilde{\varphi}(S)=\begin{cases}0&S=\{ 0,1,2 \}\\i+\exp\left( 2i\pi\left( t-\frac{1}{4} \right) \right)&S=\{ t \},0< t< 1\\-i+\exp\left( 2i\pi\left( t-\frac{3}{4} \right) \right)&S=\{ t \},1< t< 2\end{cases}$$Then, $\tilde{\varphi}\circ p = \varphi$ and $\tilde{\varphi}$ is continuous as $\varphi$ is.
3. One easily sees using analysis that $\tilde{\varphi}$ is bijective. As $X=[0,2]$ is compact and $Y$ is Hausdorff, $\tilde{\varphi}$ is a homeomorphism.
---
> [!def] Problem 2
> Let $X$ and $Y$ be topological spaces with equivalence relations $\sim_{X}$ and $\sim_{Y}$ on $X$ and $Y$ respectively. Let $Z=X\times Y$ with the product topology. On $Z$, let $\sim$ be the equivalence relation defined by $$(x_{1},y_{1})\sim(x_{2},y_{2})\iff x_{1}\sim_{X}x_{2}\land y_{1}\sim_{Y}y_{2}$$
> Let $X':=X /{\sim_{X}}$, $Y':=Y /\sim_{Y}$, $Z:= Z /\sim$  denote the respective quotients. Each is given the quotient topology. Let finally $p_{X}$, $p_{Y}$ and $p$ denote the projections. 
> 1. Show that there is a bijection $\phi:Z'\to X'\times Y'$ s.t. the class of $(x,y)$ is mapped to $(p_{X}(x),p_{Y}(y))$, and that $\phi$ is continuous when $X'\times Y'$ has the product topology. 
> 2. Suppose that $p_{X}$ and $p_{Y}$ are open maps. Show that $\phi(p(W))$ is open in $X'\times Y'$ for all $W\subseteq Z$ open. 
> 3. Deduce that $\phi$ is an homeomorphism in that case.

We have: 
1. We claim that $\phi$ is well-defined. Let $(x_{1},y_{1})\sim(x_{2},y_{2})$. Then, $x_{1}\sim x_{2}$ and $p_{X}(x_{1})=p_{X}(x_{2})$. Therefore, it holds that $(x_{1},y_{1})\sim(x_{2},y_{2})$ if and only if $(p_{X}(x_{1}),p_{Y}(y_{1}))=(p_{X}(x_{2}),p_{Y}(y_{2}))$ by symmetry and this shows the well-definedness and injectivity. For $(S,T)\in X'\times Y'$, there exists $x\in X,y\in Y$ s.t. $p_{X}(x)=S$ and $p_{Y}(y)=T$ by surjectivity of projection. Therefore, $\phi(p(x,y))=(p_{X}(x),p_{Y}(y))$. This shows that $\phi$ is bijective. 
   
   To show that $\phi$ is continuous, for a product space $V\times W$, let $\pi_{V}$ denote the projection onto $V$. Then, we notice that $\pi_{X'}\circ\phi \circ p=p_{X}\circ \pi_{X}$, which is continuous. By symmetry, it holds that $\phi$ is continuous.
2. Let $(x,y)\in W$. Then, there exists an open neighborhood $U_{X}\ni x$ and $U_{Y}\ni y$ s.t. $U_{X}\times U_{Y}\subseteq W$. Then, $p_{X}(U_{X})\ni p_{X}(x)$ and $p_{Y}(U_{Y})\ni p_{Y}(y)$ are open neighborhoods s.t. $p_{X}(U_{X})\times p_{Y}(U_{Y})$ is an open neighborhood of $\phi(p(x,y))$ contained in $\phi(p(W))$. This shows that $\phi(p(W))$ is open.
3. $\phi$ is a continuous bijection. For the inverse $\phi ^{-1}:X'\times Y'\to Z'$ and an open $U\subseteq Z'$, Then, $p ^{-1}(U)\subseteq Z$ is open and $\phi(U')=\phi(p(p ^{-1}(U)))$ which is open by 2. Therefore, the inverse is continuous.
---
> [!def] Problem 3
> Let $X$ be a topological space and $\sim$ an equivalence relation on $X$. Let $X':= X / \sim$ and $p:X\to X'$ the projection. Let $\Gamma:=\{ (x,y)\in X\times X:x \sim y \}$ be the graph of the equivalence relation. Define the relation $\equiv$ on $X\times X$ by $(x,y)\equiv(x',y')$ if and only if $x\sim x'$ and $y\sim y'$. 
> 1. Show that $\Gamma=q^{-1}(q(\Delta))$ where $$\Delta=\{ (x,x)\in X\times X: x\in X \}$$is the diagonal in $X\times X$ and $q:X\times X\to X\times X / \equiv$ is the projection.
> 2. If the map $p$ is open and $\Gamma$ is closed in $X\times X$, show that the diagonal $$\Delta':=\{ (x,x)\in X'\times X': x\in X' \}$$ is closed in $X'\times X'$ for the product topology. 
> 3. Deduce that the space $X'$ is then Hausdorff.

We have:
1. for $(x,y)\in \Gamma$, as $x\sim y$, we have that $(x,y)\equiv(x,x)$ and $q(x,y)=q(x,x)\in q(\Delta)$. Therefore, $\Gamma \subseteq q^{-1}(q(\Delta))$. Conversely, for $(x,y)\in q^{-1}(q(\Delta))$, $q(x,y)\in q(\Delta)$ and there exists $z\in X$ such that $x \sim z\sim y$. By transitivity, $x\sim y$ and $(x,y)\in \Gamma$.
2. From the previous exercise, as $p$ is open, we have that the map $$\begin{array}{cccc} {\phi:}&{(X\times X) / \equiv}&\to&{X'\times X'}\\&{q(x,y)} &\mapsto & {(p(x),p(y))} \end{array}{}$$is a homeomorphism. As $\Gamma=q^{-1}(q(\Delta))$ is closed, $q(\Delta)$ is closed and therefore $\phi(q(\Delta))=\Delta'$ is closed. 
3. $X'$ is Hausdorff if and only if the diagonal $\Delta'$ is closed.
---
> [!def] Problem 4
> Let $X=Y=\mathbb{R}$ with the euclidean topology, and let $\sim_{X}$ be the equality relation, $\sim_{Y}$ the relation where the equivalence class of $0$ is $\mathbb{Z}$ while the equivalence class of any $x\notin \mathbb{Z}$ is $\{ x \}$.
> 1. Show that $p_{X}$ is open. 
> 2. Show that if $A\subseteq Y$ is any subset, then $$p ^{-1}_{Y}(p_{Y}(A))=\begin{cases}A&A\cap \mathbb{Z}=\varnothing\\ \mathbb{Z}\cup A&\text{otherwise}\end{cases}$$ 
> 3. Deduce that $p_{Y}$ is not an open map. Show however that $p_{Y}(C)$ is closed if $C$ is closed.
> 4. Show that a fundamental system of neighborhoods of $(p_{X}(0),p_{Y}(0))\in X'\times Y'$ is given by the sets of the form $$p_{X}((-\delta,\delta))\times p_{Y}\left( \bigcup_{n\in \mathbb{Z}}^{}(n-\varepsilon_{n},n+\varepsilon_{n}) \right)$$where $\delta>0$ and $\varepsilon_{n}>0$, for $n\in \mathbb{Z}$, are arbitrary positive real numbers. 
> 5. Show that a fundamental system of neighborhoods of $p(0,0)$ in $Z'$ is given by the sets of the form $$p\left( \bigcup_{n\in \mathbb{Z}}^{}(-\delta_{n},\delta_{n})\times(n-\varepsilon_{n},n+\varepsilon_{n}) \right) $$where $\delta_{n}>0$ and $\varepsilon_{n}>0$, for $n\in \mathbb{Z}$, are arbitrary positive real numbers. 
> 6. Deduce $\phi:Z'\to X'\times Y'$ is not a homeomorphism. 
> 7. Can you get some intuitive feeling for the “shape” of $Y'$? for that of $Z'$?

We have:
1. One easily sees that $x\sim y$ if and only if $x=y$. Therefore, $p_{X}=\text{id}$ and $p_{X}$ is open.
2. Let $A\cap \mathbb{Z}=\varnothing$. Then, $p_{Y}(A)=\bigcup_{x\in A}^{}\{ x \}$. Indeed, for $x\in p ^{-1}_{Y}(p_{Y}(A))$, there exists $y\in A$ s.t. $x\sim_{Y} y$. As $A\cap \mathbb{Z}=\varnothing$, we have that $x\in A$ and $p ^{-1}_{Y}(p_{Y}(A))=A$. Similarly, if $A\cap \mathbb{Z}\neq \varnothing$, then for $x\in p _{Y}^{-1}(p_{Y}(A))$, $x \sim_{Y} y$ for some $y\in A$ and this means either $x\in \mathbb{Z}$ or $x\in A$. Conversely, if $x\in \mathbb{Z} \cup A$, then $p_{Y}(x)\in\mathbb{Z} \cup p_{Y}(A)=p_{Y}(A)$. This proves the statement.
3. We have that $\left( -\frac{1}{2}, \frac{1}{2} \right)\subseteq \mathbb{R}$ is open but $p_{Y}\left(  - \frac{1}{2}, \frac{1}{2} \right)$ is not open as $\mathbb{Z} \cup (-\frac{1}{2}, \frac{1}{2})$ is not open in $\mathbb{R}$. However, for any closed $C$, $p_{Y}(C)$ is closed as $\mathbb{Z}\cup C$ is closed as a finite union of closed subsets. 
4. Let $V\subseteq X'\times Y'$ be a neighborhood of $(p_{X}(0),p_{Y}(0))$. Then, there exist open neighborhoods $U_{X},U_{Y}$ of $p_{X}(0)$ and $p_{Y}(0)$ respectively, s.t. $U_{X}\times U_{Y}\subseteq V$. Then, $p ^{-1}_{X}(U_{X})\subseteq X$ are $p_{Y}^{-1}(U_{Y})\subseteq Y$ are open neighborhood of $0$. Indeed, there exists $(-\delta,\delta)\subseteq p_{X}^{-1}(U_{X})$ and as $0\in p _{Y}^{-1}(U_{Y})$, $\mathbb{Z}\subseteq p _{Y}^{-1}(U_{Y})$ and for every $n\in \mathbb{Z}$, there exists $\varepsilon_{n}>0$ s.t. $\bigcup_{n\in \mathbb{Z}}^{}(n-\varepsilon_{n},n+\varepsilon_{n})\subseteq p_{Y}^{-1}(U_{Y})$. This shows that this is a fundamental system.
5. Let $V\subseteq Z'$ be an open neighborhood of $p(0,0)$. Then, $p ^{-1}(V)\subseteq X\times Y$ is an open neighborhood of $(0,0)$ and there exists $U_{X}\subseteq X$