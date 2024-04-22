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

> [!proof]+
> Let $f\in V$ s.t. $Af=V$. Then, for any $g\in A^{*}$, there exists $a+bx+cy+I\in A$ s.t. $$g(x+I)=f(ax+I)$$