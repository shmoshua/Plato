#Series #DiscreteOptimization

##### Problem 1.1: Carathéodory’s Theorem
1. Firstly, one notices that it is a polyhedron. Further, as $Q$ is contained in the unit ball w.r.t. $\|\cdot\|_{\infty}$, it is clearly a polytope. Hence, it suffices to show that it is non-empty.
   
   Let $P:=\{ x\in \mathbb{R}^n: Ax \leq b  \}$ and we define $A_{=}$ as the constraints where $A_{=}x = b_{=}$. We proceed via induction over $n - \text{rnk}(A_{=})$. If $\text{rnk}(A_{=})=n$, then $x\in V$ and $e_{x}\in Q$. Now, suppose $\text{rnk}(A_{=})<n$, then there exists $0\ne z\in \text{ker }A_{=}$. Further, as $P$ is bounded, there exists $\alpha<0,\beta>0$ s.t. $x+az\in P$ if and only if $\alpha\leq a \leq \beta$. Then, $$x=\frac{\beta}{\beta-\alpha}(x+\alpha z)+\frac{-\alpha}{\beta-\alpha}(x+\beta z)$$and $x$ is a convex combination of two points in $P$. It suffices to show that $x+\alpha z,x+\beta z$ are convex combinations of the vertices. By definition, there is a row $a_{i}^\top$in $A$ s.t. $a_{i}^\top x < b_{i}$ but $a_{i}^\top(x+\alpha z)=b_{i}$. Hence, by induction we have that $x+\alpha z$ is a convex combination and similarly is $x+\beta z$. This concludes the proof.
1. As $Q$ is a non-empty polytope, it has a vertex $\lambda ^{*}$. We can represent $Q$ in standard form LP, i.e. $Q:=\{ \lambda\in \mathbb{R}^{|V|}_{+}:C\lambda=d  \}$ where $C\in \mathbb{R}^{n+1,|V|}$ and $d\in \mathbb{R}^{n+1}$. Note that if $|V|\leq n+1$ the statement holds trivially. Suppose otherwise. As $\lambda ^{*}$ is a vertex of $Q$, there exists $B\in {|V| \choose n+1}$ s.t. $\text{supp}(\lambda^*)\subseteq B$ and $\lambda ^{*}=C_{B}^{-1} d$. Therefore, $$x=\sum_{v\in V}^{}\lambda ^{*}_{v}v=\sum_{v\in B}^{}\lambda ^{*}_{v}v$$where $\sum_{v\in B}^{}\lambda ^{*}_{v}=\sum_{v\in V}^{}\lambda ^{*}_{v}=1$. This shows the statement.
---
##### Problem 1.2: Rank Deficiency in Unbounded Polyhedra
$A$ not having a full column rank is equivalent to there being a non-zero $v\in \mathbb{R}^n$ s.t. $Av = 0$. Let $P$ contain a line. Then, there exists $0\ne v\in \mathbb{R}^n$ and $x\in \mathbb{R}^{n}$ s.t. $x+\mathbb{R} v\subseteq P$. Then, we have that: $$Ax+\lambda A v\leq b,\quad \forall \lambda\in \mathbb{R}$$and this implies that $Av = 0$. 

Conversely, let $0\ne v\in \text{ker } A$. Then, let $x\in P$, which exists as $P$ is non-empty. Then for any $\lambda\in \mathbb{R}$, $$A(x+\lambda v)=Ax\leq b$$This shows that $P$ contains a line.

---
##### Problem 1.3: Strong Duality and Farkas Lemma
1. Let $P:=\{  x\in \mathbb{R}^n: Ax\leq 0 \}$ and $Q:=\{ y\in \mathbb{R}^m_{+}: A^\top y = c \}$. Note that $0\in P$ and $P$ is hence non-empty. 
   
   Assume that there exists $y\in \mathbb{R}^m_{+}$ s.t. $A^\top y = c$, i.e. $Q$ is non-empty. Then, the dual polyhedron is non-empty and by setting $b = 0$, we have that: $\max\{ c^\top x : Ax\leq 0,x\in \mathbb{R}^n \} = 0$ by the strong LP duality. 
   
   Now, assume that there doesn't exist such a $y$, i.e. $Q$ is empty. 
   
   By the strong LP duality, 
   
   we have that by setting $b=0$: $$\max\{ c^\top x : Ax\leq 0,x\in \mathbb{R}^n \}=0$$


A -> nB
B -> nA
nB = nA

A -> nB
nA -> B