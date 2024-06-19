#Definition #Topology 

> [!definition]
> Let $X,Y,Z$ be [[Topological Space|topological spaces]]. For continuous maps $f:Y\to X$ and $g:Z\to X$, a map $\tilde{g}:Z\to Y$ is a ***lift of $g$ to $Y$*** if
> 1. $f\circ \tilde{g}=g$.
- **Related definition**: If $g$ has a lift, we say it has a ***lifting***.
---
##### Properties
> [!lemma] Theorem 1 (Homotopy Lifting Property)
> Let $f:Y\to X$ be a [[covering space]]. Let $h:Z\times[0,1]\to X$ be a [[homotopy]]. 
> 1. for a lift $\tilde{h}_{0}$ of $h_{0}:Z\to X,z \mapsto h(z,0)$, there exists a unique lift $\tilde{h}$ of $h$ s.t. $\tilde{h}(z,0)=\tilde{h}_{0}(z)$ for all $z\in Z$. 

> [!proof]+
> We have:
> 1. Let $Z$ be a single point set. Then, $h$ can be considered as a continuous map $h:[0,1]\to X$. We will show the uniqueness of the lift in this case. 
>    
>    Let $\tilde{h},\tilde{h}':[0,1]\to Y$ be lifts s.t. $\tilde{h}(0)=\tilde{h}_{0}=\tilde{h}'(0)$. Let further: $$A:=\{ t\in[0,1]:\tilde{h}(t)=\tilde{h}'(t) \}\subseteq[0,1]$$Then, $A$ is non-empty as $0\in A$ and $A$ is closed by continuity. However, we also show that $A$ is open. Let $t\in A$. Let $V$ be an open interval containing $t$ s.t. $h(V)\subseteq U$ where $f$ is trivializable above $U$. In other words, we have:
>    
>    ```tikz
>    \usepackage{tikz-cd} 
>    \begin{document}
>    \begin{tikzcd} 
>    & {f^{-1}(U)} & {U\times D} \\ 
>    V & U 
>    \arrow["\varphi", from=1-2, to=1-3] \arrow["f"', from=1-2, to=2-2] \arrow["{\text{pr}_1}", from=1-3, to=2-2] \arrow["{\tilde{h}}", from=2-1, to=1-2] \arrow["h"', from=2-1, to=2-2] 
>    \end{tikzcd}
>    \end{document}
>    ```
---
