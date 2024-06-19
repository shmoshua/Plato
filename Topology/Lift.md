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
> 1. **Claim 1: The lift is unique when $Z$ is single-point**
>    Let $Z$ be a single point set. Then, $h$ can be considered as a continuous map $h:[0,1]\to X$. We will show the uniqueness of the lift in this case. 
>    
>    Let $\tilde{h},\tilde{h}':[0,1]\to Y$ be lifts s.t. $\tilde{h}(0)=\tilde{h}_{0}=\tilde{h}'(0)$. Let further: $$A:=\{ t\in[0,1]:\tilde{h}(t)=\tilde{h}'(t) \}\subseteq[0,1]$$Then, $A$ is non-empty as $0\in A$ and $A$ is closed by continuity. However, we also show that $A$ is open. Let $t\in A$. Let $V$ be an open interval containing $t$ s.t. $h(V)\subseteq U$ where $f$ is trivializable above $U$. In other words, we have:
>    
>    ```tikz
>    \usepackage{tikz-cd} 
>    \begin{document}
>    \begin{tikzcd} 
> 	   & {f^{-1}(U)} & {U\times D} \\ 
> 	   V & U 
> 	   \arrow["\varphi", from=1-2, to=1-3]
> 	   \arrow["f", from=1-2, to=2-2]
> 	   \arrow["{\tilde{h}}", from=2-1, to=1-2] 
> 	   \arrow["h"', from=2-1, to=2-2] 
> 	   \arrow["p_1", from=1-3, to=2-2]
>    \end{tikzcd}
>    \end{document}
>    ```
>    Therefore, such $U$ exists for $h(t)$ as $f$ is a covering space. Then, by continuity of $h$, such $V$ exists. Since $f\circ\tilde{h}=h$ and $f\circ\tilde{h}'=h$, we have that $\tilde{h}(V)\subseteq f^{-1}(U)$ and $\tilde{h}'(V)\subseteq f^{-1}(U)$. 
>    
>    Then, for $s\in V$, $\tilde{h}(s)=\varphi ^{-1}(h(s),\delta(s))$ and $\tilde{h}'(s)=\varphi ^{-1}(h(s),\delta'(s))$ for some continuous $\delta,\delta':V\to D$. Since $V$ is connected, $\delta,\delta'$ are constant. However, as $\tilde{h}(t)=\tilde{h}'(t)$, we have that $\delta(t)=\delta'(t)$. This shows that $\tilde{h}=\tilde{h}'$ on $V$. Therefore, $V\subseteq A$ and $A$ is open. 
>    
>    This shows that $A=[0,1]$ and $\tilde{h}=\tilde{h}'$.
> 2. **Claim 2: The lift is unique for any $Z$.**
>    Let $\tilde{h},\tilde{h}'$ be two lifts. Let $z_{0}\in Z$. Then, $t\mapsto \tilde{h}(z_{0},t)$ and $t\mapsto \tilde{h}'(z_{0},t)$ are lifts of $t\mapsto h(z_{0},t)$ coinciding at $0$. Therefore, they are equal by claim 1. As $z_{0}$ is arbitrary, $\tilde{h}=\tilde{h}'$.
> 3. **Claim 3: Existence**:
>    Firstly we observe that $\tilde{h}$ exists locally, i.e. given $(z_{0},t_{0})\in Z\times[0,1]$, there is an open interval $J$ containing $t_{0}$ and an open neighborhood $U\ni z_{0}$ s.t. 
>    1. $h(U\times J)\subseteq W$ where $f$ is trivializable over $W$ and
>    2. given $\tilde{h}_{t_{0}}:U\to f^{-1}(W), z\mapsto \tilde{h}(z,t_{0})$ there exists a lift $\tilde{h}$ of $h|_{U\times J}$ s.t. for all $z\in U$, $\tilde{h}(z,t_{0})=\tilde{h}_{t_{0}}(z)$
>       
>    Let $\varphi,D$ be s.t. $W$ is an open neighborhood of $h(z_{0},t_{0})$ with: 
>    
>    ```tikz
>    \usepackage{tikz-cd} 
>    \begin{document}
>    \begin{tikzcd} 
> 	   & {f^{-1}(W)} & {W\times D} \\ 
> 	   {U\times J} & W
> 	   \arrow["\varphi", from=1-2, to=1-3]
> 	   \arrow["f", from=1-2, to=2-2]
> 	   \arrow["h"', from=2-1, to=2-2] 
> 	   \arrow["p_1", from=1-3, to=2-2]
>    \end{tikzcd}
>    \end{document}
>    ```
>    then such $U\times J$ exists as $h$ is continuous. Then, for $t_{0}$, we can write: $$\varphi(\tilde{h}(z,t_{0}))=(h(z,t_{0}),\delta(z))$$
---
