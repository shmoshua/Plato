#Definition #RepresentationTheory 

> [!definition]
> Let $V\neq 0$ be a [[representation]] of an [[associative algebra]] $A$. Then, a vector $v\in V$ is ***cyclic*** if $Av=V$. $V$ is ***cyclic*** if it admits a cyclic vector.
---
##### Properties
> [!lemma] Proposition 1
> Let $V\neq 0$ be a representation of $A$. 
> 1. $V$ is irreducible if and only if all non-zero vectors of $V$ are cyclic.
> 2. $V$ is cyclic if and only if it is isomorphic to $A / I$ where $I$ is a [[Ideal|left ideal]] in $A$.

> [!proof]-
> We have:
> 1. Let $0\neq v\in V$ be a not cyclic. Then, $Av$ is a non-trivial subrepresentation, i.e. $V$ is not irreducible. Conversely, if $V$ is not irreducible with $W$ as a non-trivial subrepresentation. Then, there exists $w\in W$ s.t. $Aw\subseteq W$.
> 2. If $V$ is cyclic with cyclic vector $v\in V$ consider $$\begin{array}{cccc} {\varphi:}&{A}&\to&{V}\\&{a} &\mapsto & {av} \end{array}{}$$which is a homomorphism. Then, $A / \text{ker }\varphi\cong V$ by the isomorphism theorem. 
>    
>    Conversely, if $V$ is isomorphic to $A / I$, $1+I\in A / I$ is the cyclic vector.
---
##### Examples
> [!h] Example 1
> Let $A:=\mathbb{C}[X,Y] / I$ where $I$ is the ideal spanned by homogeneous polynomials of degree $\geq 2$. Let $V:=A^{*}$. Then, 
> 1. $V$ is not cyclic.
> 2. $V$ is indecomposable.

> [!proof]-
> We have:
> 1. Let $f\in V$ s.t. $Af=V$. Then, for any $g\in A^{*}$, there exists $a+bx+cy+I\in A$ s.t. $$g(x+I)=f(ax+I),\quad g(y+I)=f(ay+I),\quad g(1+I)=f(a+bx+cy+I)$$This is a contradiction as we can have $g_{1},g_{2}\in A^{*}$ s.t. $g_{1}(1+I)=g_{2}(1+I)$ but $g_{1}(x+I)\neq g_{2}(x+I)$.
> 2. However, $V$ is indecomposable. Let $d_{1},d_{x},d_{y}\in A^{*}$ be defined as: $$\begin{align}d_{1}(a+bx+cy+I)=a\\d_{x}(a+bx+cy+I)=b\\d_{y}(a+bx+cy+I)=c\end{align}$$Then, $$\begin{align}(x+I)(\xi_{1}d_{1}+\xi_{x}d_{x}+\xi_{y}d_{y})(a+bx+cy+I)&=(\xi_{1}d_{1}+\xi_{x}d_{x}+\xi_{y}d_{y})(ax+I)\\&=\xi_{x}a\\&=\xi_{x}d_{1}(a+bx+cy+I)\end{align}$$Therefore, $$\begin{align}\rho(x+I)(\xi_{1}d_{1}+\xi_{x}d_{x}+\xi_{y}d_{y})=\xi_{x}d_{1}\\\rho(y+I)(\xi_{1}d_{1}+\xi_{x}d_{x}+\xi_{y}d_{y})=\xi_{y}d_{1}\end{align}$$
> 	It follows that for any $v\in A^{*}$, there exists $a\in A$ s.t. $av=d_{1}$. Therefore, $V$ cannot be a direct sum of two non-zero subrepresentations.
---