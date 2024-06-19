
#Definition #Topology 

> [!definition]
> A [[topological space]] $X$ is ***semi-locally simply connected*** if every $x\in X$ admits a neighborhood $U$ s.t. any loop in $U$ is [[path|path-homotopic]] to $\varepsilon_{x}$ in $X$.
- **Remark**: This is equivalent as saying $i_{*}:\pi_{1}(U,x)\to \pi_{1}(X,x)$ is trivial.
- **Remark**: This is weaker than requiring $U$ to be simply connected! The contraction does not have to happen in $U$!
---
##### Examples
> [!h] Example 1
> We have:
> 1. Any locally simply connected space is semi-locally simply connected.
> 2. Any [[topological manifold]] is semi-locally simply connected.
---
> [!h] Example 2
> For a [[simply connected space]] $Y$ and a [[covering space]] $p:Y\to X$, $X$ is semi-locally simply connected.

> [!proof]-
> Let $x\in X$. Let $U$ be a neighborhood of $x$ s.t. $p$ is trivializable over $U$, i.e. 
> ```tikz
> \usepackage{tikz-cd}
> \begin{document}\begin{tikzcd} {p^{-1}(U)} & {U\times D} \\ U \arrow["\varphi", from=1-1, to=1-2] \arrow["p"', from=1-1, to=2-1] \arrow["{p_1}", from=1-2, to=2-1] \end{tikzcd}\end{document}
> ```
> 
> Pick $d_{0}\in D$. Then, $p:\varphi ^{-1}(U\times \{ d_{0} \})\to U$ is a homeomorphism. Therefore, any loop in $U$ gives a loop in $\varphi ^{-1}(U\times \{ d_{0} \})\subseteq Y$. As $Y$ is simply connected, let $\tilde{h}$ be the path homotopy from the loop to $\varepsilon_{\varphi ^{-1}(x,d_{0})}$. Then, $p\circ\tilde{h}$ is a path homotopy in $X$ from $\gamma$ to $\varepsilon_{x}$.
---
