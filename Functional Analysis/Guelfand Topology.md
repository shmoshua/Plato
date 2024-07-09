#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a commutative [[Banach Algebra|Banach algebra]] and $\hat{A}$ the [[Guelfand Spectrum|Guelfand spectrum]] of $A$. The ***Guelfand topology*** is a topology on $\widehat{A}\subseteq A^{*}$ induced by the [[Weak Topology|weak*-topology]] on $A^{*}$.
---
##### Properties
> [!lemma] Theorem 1
> Let $A$ be a commutative [[Banach Algebra|Banach algebra]]. Then, we have: 
> 1. $\widehat{A}$ is locally compact Hausdorff w.r.t. Guelfand topology.
> 2. If $A$ is unital, $\widehat{A}$ is compact.
> 3. If $A$ is non-unital, $\widehat{A_{I}}$ is the [[one-point compactification]] of $\widehat{A}$.

^a2c505

> [!proof]-
> Consider the map: $$\begin{array}{cccc} {p:}&{A_{I}:=A\times \mathbb{C}}&\to&{A}\\&{(x,\lambda)} &\mapsto & {x} \end{array}{}$$Then, 
> 1. $\left\| p \right\|=1$ and 
> 2. $p^{*}:A^{*}\to(A_{I})^{*}$ is weak*-continuous and injective, by [[Weak Topology|Proposition 3]].
> 
> Therefore, $$p^{*}(B_{\leq 1}^{A^{*}}(0))=\{ \varphi\in B_{\leq 1}^{(A_{I})^{*}}(0):\varphi((0,1))=0 \}$$By [[Weak Topology|Banach Alagolu]], $B_{\leq 1}^{A^{*}}(0)$ and $B_{\leq 1}^{(A_{I})^{*}}(0)$ are weak\*-compact. Observe that: 
> $$\{ \varphi\in (A_{I})^{*}:\varphi((0,1))=0 \}$$ is weak\*-closed. As a result: $$p^{*}:B_{\leq 1}^{A^{*}}(0)\to \{ \varphi\in B_{\leq 1}^{(A_{I})^{*}}(0):\varphi((0,1))=0 \}$$is a homeomorphism. Therefore, the extension can be characterized as: $$\tilde{\varphi}:=p^{*}(\varphi)+\varphi_{\infty}$$Then, with $\gamma:A^{*}\to(A_{I})^{*},\varphi\mapsto p^{*}(\varphi)+\varphi_{\infty}$, 
> 1. $\gamma$ is injective and linear.
> 2. $\gamma$ is continuous in weak\*-topology.
>    
>  Therefore, $$\gamma:B_{\leq 1}^{A^{*}}(0)\to \{ \varphi\in B_{\leq 1}^{(A_{I})^{*}}(\varphi_{\infty}):\varphi((0,1))=1 \}$$is a homeomorphism. This implies that the image is compact. However, we have: $$\begin{CD} B_{\leq 1}^{A^{*}}(0) @>\gamma>> \{ \varphi\in B_{\leq 1}^{(A_{I})^{*}}(\varphi_{\infty}):\varphi((0,1))=1 \}\\ \cup&&\cup\\\hat{A} @>\gamma>> \widehat{A_{I}} \backslash \{ \varphi_{\infty} \}\end{CD}$$
>  Now, assume that $B$ is a commutative unital Banach algebra. Then, $$\begin{align}\hat{B}&:=\{ \varphi\in B_{\leq 1}^{B^{*}}(0):\varphi(xy)=\varphi(x)\varphi(y),\varphi(e)=1,\quad \forall x,y\in B\}\\&=\{\varphi\in B_{\leq 1}^{B^{*}}(0):\varphi(e)=1 \}\cap\bigcap_{x,y\in B}^{}\{ \varphi\in B_{\leq 1}^{B^{*}}(0):\varphi(xy)=\varphi(x)\varphi(y)\}\end{align}$$which is weak\*-closed. Therefore, $\hat{B}$ is compact. 

---
From weak*-topology, let: $$U:=N(\varphi_{I};(x_{1},\lambda_{1}),\dots,(x_{n},\lambda_{n});\varepsilon):=\{ \chi\in \widehat{A_{I}}:\left| \chi(x_{i},\lambda_{i})-\varphi_{I}(x_{i},\lambda_{i}) \right| <\varepsilon , \forall i\in [n] \}$$Then, 
1. if $\varphi_{\infty}\in U$, then $\left| \lambda_{i}-\varphi(x_{i})-\lambda_{i} \right|=\left| \varphi(x_{i}) \right|<\varepsilon$ so 