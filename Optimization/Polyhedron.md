#Definition #Optimization 

> [!definition]
> Let $A\in \mathbb{R}^{m,n},b\in \mathbb{R}^n$. 
> 1. A ***polyhedron*** is given by $P:=\{ x \in \mathbb{R}^n : Ax\leq b\}$.

- **Related definition**: A ***face*** $F$ of a polyhedron $P$ is given by: $$F:=\{ x\in P:A_{I}x = B_{I} \}$$for some $I\subseteq [m]$.
- **Related definition**: A face $F$ is ***minimal*** if there does not exist another face $F'$ s.t. $\varnothing \subsetneq F' \subsetneq F$
- **Related definition**: A polyhedron is 
	1. ***rational*** if $A\in \mathbb{Q}^{m,n}, b\in \mathbb{Q}^n$.
	2. ***integral*** if every minimal face of $P$ contains integer points.
	3. a ***polytope*** if it is bounded.
---
##### Properties
> [!lemma] Lemma 1
> Let $P$ be a polyhedron.
> 1. $P$ is [[Convex Set|convex]].
> 2. if $P$ is a polytope, $P=\text{conv}(v_{1},..,v_{k})$ for some $v_{1},\dots,v_{k}$ where $v_{1},\dots,v_{k}$ are the vertices.

> [!proof]-
> We have that:
> 1. Let $x,y\in P$. Then $Ax,Ay\leq b$ and for any $\lambda\in[0,1]$, $$A(\lambda x+(1-\lambda)y)=\lambda Ax+(1-\lambda)Ay\leq b$$

---
> [!lemma] Lemma 1
> Let $P$ be a polytope. 
> 1. its minimal faces are exactly the vertices.
> 2. if $P$ if integral, then all vertices are integral.

---
> [!lemma] Lemma 2
> Let $P$ be a polyhedron with at least one vertex. TFAE:
> 1. $P$ is integral.
> 2. $\max_{x\in P}c^\top x \in \mathbb{Z}$ for all $c\in \mathbb{Z}^n$ for which it is feasible/bounded.

> [!proof]-
> We have that:
> - (1=>2): Let $c\in \mathbb{Z}^n$. As the optimal value is attained at a minimal face and as there exists an integer point $x^{*}\in\mathbb{Z}^n$ by the integrality of $P$, we have that $c^\top x^{*}\in \mathbb{Z}$.
> - (2=>1): Let $x^{*}$ be a fractional vertex of $P$, i.e. $\exists j$ s.t. $x^{*}_{j}\notin \mathbb{Z}$. As $P$ has finitely many vertices, choose $c\in \mathbb{Z}^n$ s.t. $c^\top x^{*}$ is maximized over $P$. We can also choose $a\in \mathbb{Z}_{+}$ s.t. $x^*$ is optimal over ${P}$ for an objective vector $\overline{c}:= \frac{1}{a}e_{j}+c$.
>   
>   Then, $a\overline{c}\in \mathbb{Z}^n$ and $a\overline{c} ^\top x^{*}\in \mathbb{Z}$. However, $$a\overline{c}^\top x^{*} - ac^\top x^{*} = x_{j}^{*}\notin \mathbb{Z}$$which is a contradiction.

---
