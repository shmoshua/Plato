#Series #DiscreteOptimization

##### Problem 1.1: Carathéodory’s Theorem
1. Firstly, one notices that it is a polyhedron. Further, as $Q$ is contained in the unit ball w.r.t. $\|\cdot\|_{\infty}$, it is clearly a polytope. Hence, it suffices to show that it is non-empty.
   
   Let $P:=\{ x\in \mathbb{R}^n: Ax \leq b  \}$ and we define $A_{=}$ as the constraints where $A_{=}x = b_{=}$. We proceed via induction over $n - \text{rnk}(A_{=})$. If $\text{rnk}(A_{=})=n$, then $x\in V$ and $e_{x}\in Q$. Now, suppose $\text{rnk}(A_{=})<n$, 
1. From $x\in P$, we have that $Ax\leq b$
2. Firstly, one can easily see that 

