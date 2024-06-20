#Definition #Topology 

> [!definition]
> A function $f:X\to Y$ between two [[Topological Space|topological spaces]] is a ***local homeomorphism*** if every point $x\in X$ admits an open neighborhood $U$ s.t. 
> 1. $f(U)$ is open in $Y$.
> 2. $f:U\to f(U)$ is a [[homeomorphism]].
---
##### Examples
> [!h] Example 1 (Covering Space)
> Any [[covering space]] $f:Y\to X$ is a local homeomorphism.

> [!proof]+
> Let $y\in Y$. Then, by the definition of a covering space, there exists an open neighborhood $V$ of $f(y)$ and a discrete $D\neq \varnothing$ and a homeomorphism $\varphi$ s.t. 
> ```tikz
> \usepackage{tikz-cd}
> \begin{document}\begin{tikzcd} {f^{-1}(V)} & {V\times D} \\ V \arrow["\varphi", from=1-1, to=1-2] \arrow["f", from=1-1, to=2-1] \arrow["{p_1}", from=1-2, to=2-1] \end{tikzcd} \end{document}
> ```
> Then, $y$ is contained in an open $U$ isomorphic to $V\times \{ d \}$ for some $d\in D$ and $f|_{U}$ gives the desired homeomorphism.