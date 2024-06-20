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

> [!proof]-
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
>    then such $U\times J$ exists as $h$ is continuous. Then, for $t_{0}$, we can write: $$\varphi(\tilde{h}_{t_{0}}(z,t_{0}))=(h(z,t_{0}),\delta(z))$$with $\delta:U\to D$ continuous and $\tilde{h}(z,t):=\varphi ^{-1}(h(z,t),\delta(z))$. By the same argument as in Claim 1, $\tilde{h}$ is unique.
>    
>    Now, for a given $z_{0}\in Z$, by compactness we can find a finite subset $S\subseteq [0,1]$ and $J_{s}$ for each $s\in S$, s.t. $[0,1]=\bigcup_{s\in S}^{}J_{s}$ and $U_{s}$ a neighborhood of $z_{0}$ s.t. $h(U_{s}\times J_{s})$ is a trivializable neighborhood of $h(z_{0},s)$. Let $U:=\bigcap_{s\in S}^{}U_{s}$. Further, we arrange $S$ in increasing order $s_{0}<s_{1}<\dots<s_{m}$ s.t. $J_{s_{i}}\cap J_{s_{i+1}}\neq \varnothing$ and $0\in J_{s_{0}}$ and $1\in J_{s_{m}}$. 
>    
>    By taking the local lift at each $z=z_{0}$ and $t_{0}\in J_{s_{i}}$, we can define $\tilde{h}(z,t_{0})$ for any $z\in Z$ and $t_{0}\in [0,1]$ and it is well-defined as the lift is unique given by above, as all the local neighborhoods are overlapping.
- **Corollary**: for any path $\gamma:[0,1]\to X$ from $x_{0}$ and any $y_{0}\in Y$ s.t. $f(y_{0})=x_{0}$, there exists a unique lift $\tilde{\gamma}:[0,1]\to Y$ s.t. $\tilde{\gamma}(0)=y_{0}$.
---
> [!lemma] Theorem 2
> Let $f:Y\to X$ be a [[covering space]] and $g:Z\to X$ a contiuous map. Let $z_{0}\in Z$ and $x_{0}=g(z_{0})$. Further, let $y_{0}\in Y$ s.t. $f(y_{0})=x_{0}$.
> 1. if $g$ admits a lift $\tilde{g}:Z\to Y$ with $\tilde{g}(z_{0})=y_{0}$, then: $$g_{*}(\pi_{1}(Z,z_{0}))\subseteq f_{*}(\pi_{1}(Y,y_{0}))\subseteq \pi_{1}(X,x_{0})$$
> 2. if $Z$ is [[Path-Connected Space|path-connected]] and locally path-connected s.t. $$g_{*}(\pi_{1}(Z,z_{0}))\subseteq f_{*}(\pi_{1}(Y,y_{0}))\subseteq \pi_{1}(X,x_{0})$$then $g$ admits a lift $\tilde{g}$ with $\tilde{g}(z_{0})=y_{0}$.

> [!proof]+
> We have:
> 1. We have that $g=f\circ \tilde{g}$. Therefore, $$g_{*}(\pi_{1}(Z,z_{0}))=f_{*}(\tilde{g}_{*}(\pi_{1}(Z,z_{0})))\subseteq f_{*}(\pi_{1}(Y,y_{0}))\subseteq \pi_{1}(X,x_{0})$$all by [[Fundamental Group|functoriality of $\pi_{1}$.]]
> 2. We will show this in multiple steps:
> 	1. For any $z\in Z$ and any path $\gamma:[0,1]\to Z$ from $z_{0}$ to $z$, there exists a unique lift $\eta:[0,1]\to Y$ of $g\circ\gamma$ s.t. $\eta(0)=y_{0}$ by Corollary of homotopy lifting theorem.
> 	  
>     2. Let $\gamma'$ be another path in $Z$ from $z_{0}$ to $z$, and $\eta'$ the corresponding lift of $g\circ\gamma'$ to $Y$ such that $\eta'(0)=y_{0}$. Then, notice that $\gamma \overline{\gamma'}$ is a loop at $z_{0}$. Hence, by $g_{*}(\pi_{1}(Z,z_{0}))\subseteq f_{*}(\pi_{1}(Y,y_{0}))$, there is a loop $\alpha:[0,1]\to Y$ at $y_{0}$ s.t. $g\circ\gamma\overline{\gamma'}$ and $f\circ\alpha$ are path-homotopic. Let $h$ be one such path-homotopy. Then, $h:[0,1]\times[0,1]\to X$ s.t. 
>        $$h(s,0)=(g\circ \gamma)*(\overline{g\circ \gamma'})(s),\quad h(s,1)=(f\circ \alpha)(s)$$Then, notice that $f(\alpha(s))=h(s,1)$. Therefore, by homotopy lifting property, we have a unique lift $\tilde{h}:[0,1]\times[0,1]\to Y$ s.t. $$\tilde{h}(s,1)=\alpha(s)$$Now, consider $t\mapsto \tilde{h}(0,t)$. We have $\tilde{h}(0,1)=y_{0}$, however, $\varepsilon_{y_{0}}$ is also a lift of $t\mapsto h(0,t)$ as: $$f(y_{0})=x_{0}=h(0,t),\quad \forall t\in[0,1]$$Therefore, by uniqueness, $\tilde{h}(0,t)=y_{0}$ for all $t\in [0,1]$. Similarly, $\tilde{h}(1,t)=y_{0}$ for all $t\in [0,1]$. Hence, $\tilde{h}_{0}$ is a loop at $y_{0}$. 
>      3. Notice that $\eta(0)=y_{0}$. However, $t\mapsto \tilde{h}(0,t/2)$ for $t\in [0,1]$ is also a lift of $g\circ\gamma$ with $\tilde{h}(0,0)=y_{0}$. Therefore, by uniqueness, $\tilde{h}(0, t)=\eta(2t)$ for $t\in[0,1 /2]$. Similarly, $\eta'(0)=y_{0}$ and $t\mapsto \tilde{h}(0,1-t /2)$ is a lift of $g\circ\gamma'$ with $\tilde{h}(0,1)=y_{0}$. Therefore, by uniqueness, $$\tilde{h}(0,t)=\begin{cases}\eta(2t)&0\leq t\leq \frac{1}{2\\}\\ \eta'(2-2t)& \frac{1}{2}\leq t\leq 1\end{cases}$$As $\tilde{h}_{0}$ is continuous, we also get that $\eta(1)=\eta'(1)$. Therefore, for any path $\gamma$ from $z_{0}$ to $z$, we can choose $\tilde{g}(z)=\eta(1)$, which is well-defined.
>      4. Now, let $z\in Z$ and $U\subseteq X$ a neighborhood of $g(z)$ s.t. $f$ is trivializable over $U$. Then, let $\tilde{g}(z)\in Y$ and we have $f(\tilde{g}(z))=g(z)$. Therefore, there exists $d\in D$ s.t. $\varphi(\tilde{g}(z))=(g(z),d)$ where $\varphi :f^{-1}(U)\to U\times D$ is the given homeomorphism. Setting $\tilde{U}:=\varphi ^{-1}(U\times \{ d \})$ gives $f:\tilde{U}\to U$ as a homeomorphism.
>      5. As $Z$ is path-connected, there exists a path-connected neighborhood $V$ of $z$ s.t. $g(V)\subseteq U$. Then, for $w\in V$, let $\gamma_{0}$ be a path from $z_{0}$ to $z$ and $\gamma_{w}$ a path from $z$ to $w$. We aim to find a lift of $\gamma_{0}\gamma_{w}$. We have that: $$f(f^{-1}(g))$$
>         
>         Show that there exists a path connected neighborhood $V$ of $z$ such that $g(V)\subseteq U$.  show then that for $w\in V$ , we have $\tilde{g}(w)=f_{g(V)}^{-1}(g(w))$, and deduce that $\tilde{g}$ is continuous. (Hint: write a path γ from z0 to w ∈ V as γ0 ∗ γw where γ0 is a fixed path from z0 to z and γw is a path from z to w, and find an explicit lift of γw using fg(V ) .)
>         
>         Show that there exists a neighborhood U˜ of ˜g(z) such that the restriction fU˜ of f to U˜ is a homeomorphism fU˜ : U˜ → U.
>        
>        
>        