#Definition #Topology 

> [!definition]
> Let $X$ be a [[Topological Space|topological space]]. A subspace $Y\subseteq X$ is called a ***retract*** of $X$, if there exists a continuous map $r:X\to Y$, called a ***retraction***, s.t.
> 1. $r(y)=y$ for all $y\in Y$, i.e. $r|_{Y}=\text{id}_{Y}$.

^0da441

- **Related definition**: A [[homotopy]] $h:X\times[0,1]\to X$ between $\text{id}_{X}$ and a retraction $r$ is called a ***deformation retraction*** and $Y$ a ***deformation retract***. ^5cd052
- **Related definition**: A deformation retraction $h$ is ***strong*** if for all $t\in[0,1]$. $h(\cdot,t)|_{Y}=\text{id}_{Y}$. Then, $Y$ is called a ***strong deformation retract***. In other words, $\text{id}_{X}\sim_{\text{rel }A}r$. ^735e3a

---
##### Properties
> [!lemma] Proposition 1
> Let $A\subseteq X$ be a deformation retract. Then, 
> 1. $A$ and $X$ are homotopy equivalent.

^d770ca

> [!proof]-
> We have:
> 1. Consider $i:A\hookrightarrow X$ and the retraction $r$. Then, $r\circ i:A\to A=\text{id}_{A}$ and we have that: $$i\circ  r=r \sim \text{id}_{X}$$

^b65047

---
> [!lemma] Lemma 2
> If $Y$ is a retract of $X$, the group morphism $\pi_{1}(Y,y_{0})\to \pi_{1}(X,y_{0})$ induced by $Y\to X$ is injective.

> [!proof]-
> By [[Fundamental Group|Functoriality]], $i_{*}:\pi_{1}(Y,y_{0})\to \pi_{1}(X,y_{0})$ is a group homomorphism. It is then injective by definition.
---
##### Examples
> [!h] Example 1
> We have that:
> 1. $\{ 0 \}$ is a strong deformation retract of $\mathbb{R}^n$.
> 1. $S^{n-1}$ is a strong deformation retract of $\mathbb{R}^n \backslash\{ 0 \}$
> 2. $S^{1}$ is not a retract of $\mathbb{R}^2$ by Lemma 1, as $\pi_{1}(S^1,1)\cong\mathbb{Z}$ and $\pi_{1}(\mathbb{R}^{2},1)=\{ \varepsilon_{1} \}$.

^5d4435

> [!proof]-
> Let us define: $$\begin{array}{cccc} {r:}&{\mathbb{R}^n\backslash\{ 0 \}}&\to&{S_{n-1}}\\&{x} &\mapsto & {x / \|x\|} \end{array}{}$$Then, for all $x\in S_{n-1}$, $\|r(x)\|=1$ and $r(x)\in S_{n-1}$. The continuity follows from that of the norm. 

^0fd510

---
> [!Example 2]
> We have that:
> 1. there exists no retraction $r:B^n\to S^{n-1}$.

> [!proof]-
> Assume there exists such $r$. Let $H$ be a [[homology theory]] with coefficients group $G\neq 0$. Then, by definition, we have that $r\circ i=\text{id}$ where $i$ is the inclusion. Hence, 
>```tikz 
>\usepackage{tikz-cd} \begin{document} \begin{tikzcd} {G=\tilde{H}_{n-1}(S^{n-1})} & {0=\tilde{H}_{n-1}(B^n)} \\ & {G=\tilde{H}_{n-1}(S^{n-1})} \arrow["{i_*}", from=1-1, to=1-2] \arrow["{\textrm{id}}"', from=1-1, to=2-2] \arrow["{r_*}", from=1-2, to=2-2] \end{tikzcd}\end{document}
>```
> 
> implies that $G=0$ which is a contradiction.

---
