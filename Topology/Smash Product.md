#Definition #Topology 

> [!definition]
> A pointed space $(X,x_{0})$ is ***nice*** if $x_{0}\in X$ has a closed neighborhood $N$ where $x_{0}$ is a [[Retract|strong deformation retract]] in $N$. Let $(X,x_{0}),(Y,y_{0})$ be nice LCH spaces. Then, 
> 1. the ***smash product*** of $X,Y$ is defined as a pointed space $(X\land Y,*)$ $$X\land Y:=X\times Y / X\lor Y$$where $q(X\lor Y)=\{ * \}$.
- **Related definition**: For $f:(X,x_{0})\to(X',x_{0}')$ and $g:(Y,y_{0})\to(Y',y'_{0})$, we have: $$f \land g:(X\land Y,*)\to(X'\land Y',*),\quad [(x,y)]\mapsto [(f(x),g(y))]$$Further, let $f\ \tilde{\land}\ g:=(f\land g) \circ q:X \times Y\to X'\land Y'$.
---
##### Properties
> [!lemma] Proposition 1
> For $f:(X,x_{0})\to(X',x_{0}')$ and $g:(Y,y_{0})\to(Y',y'_{0})$,
> 1. $f\land g$ is well-defined.
> 2. $X\land Y\cong Y \land X$ s.t. the homeomorphism is natural to functions, i.e. the diagram commutes for all $f,g$:$$\begin{CD}X\land Y@>\psi>> Y \land X\\@Vf\land gVV@VVg\land fV\\X'\land Y'@>\psi'>> Y'\land X\end{CD}$$
> 3. $(X\land Y)\land Z\cong X \land(Y\land Z)$, s.t. the homeomorphism is natural to functions. 
> 4. If $X,Y$ are compact, $X\land Y\cong (X \backslash \{ x_{0} \})\times(Y \backslash \{ y_{0} \})\cup \{ \infty \}$, the [[one-point compactification]] and the homeomorphism is natural.

> [!proof]-
> We have that:
> 1. If $(x,y)\in X \lor Y$ then either $y=y_{0}$ or $x=x_{0}$. Hence, either $f(x)=x'_{0}$ or $g(y)=y'_{0}$. Hence, $(f(x),g(y))\in X' \lor Y'$. 
> 2. We have that: $$\psi:X\land Y\to Y\land X,\quad [(x,y)]\mapsto [(y,x)]$$Then, $\psi$ is well-defined as $(x,y)\in X \lor Y$, $(y,x)\in Y \lor X$. Further, $\psi$ is bijective. Now, it is left to show that $\psi$ is continuous as the inverse is of the same form modulo changing $X$ and $Y$. To show that it is continuous we have that: $$\psi \circ  q(x,y)=[(y,x)]$$which is continuous as $\psi \circ q$ can be factored into swapping $X$ and $Y$ and projecting. 
>    
>    Lastly, for $f,g$: $$\psi'(f\land g([(x,y)]))=\psi'([(f(x),g(y))])=[(g(y),f(x))]=g\land f([(y,x)])=g\land f(\psi([(x,y)]))$$
> 3. We have that: $$\psi:(X\land Y)\land Z\to X\land (Y\land Z),\quad [([x,y],z)]\mapsto [(x,[y,z])]$$which is well-defined as $([x,y],z)\in (X\land Y) \lor Z$, then $x=x_{0}$ or $y=y_{0}$ or $z=z_{0}$. Therefore, $(x,[y,z])\in X \lor ([Y\land Z])$. One sees that $\psi$ is bijective and continuous. Lastly, we have that for $f:(X,x_{0})\to (X',x_{0}')$, $g:(Y,y_{0})\to (Y',y_{0}')$ and $g:(Z,z_{0})\to (Z',z_{0}')$, we have that: $$\begin{align}\psi'\circ ((f \land g)\land h)([([x,y]),z])&=\psi'([([f(x),g(y)]),h(z)])\\&=[(f(x),[(g(y),h(z))])]=(f\land(g\land h))\psi([([x,y]),z])\end{align}$$
> 4. We have that $X \land Y$ is compact Hausdorff as an image of $X\times Y$. We will show that $X\land Y \backslash \{ * \}$ is homeomorphic to $(X \backslash \{ x_{0} \})\times(Y \backslash \{ y_{0} \})$ which proves the statement by [[One-Point Compactification|Theorem 2]]. Let $q:X\times Y\to X \land Y$ be the quotient map. Let $Z:=(X \backslash \{ x_{0} \})\times(Y \backslash \{ y_{0} \})$. We will show that $q|_{Z}$ is a homeomorphism. 
>    
>    1. $q|_{Z}$ is continuous and injective by definition. 
>    2. To show that $q|_{Z}$ is open, let $U\subseteq Z$ be an open set. Then, $U$ is also open in $X\times Y$ and $q^{-1}(q(U))=U$. Therefore, $q(U)$ is open in $X\land Y$.
>    3. $q(Z)=X \land Y \backslash \{ * \}$. 
>	
>	This concludes the proof for the homeomorphism. 
>	
>	To show that it is natural, let $f:(X,x_{0})\to(X',x'_{0})$ and $g:(Y,y_{0})\to(Y',y_{0}')$ maps between compact spaces. Then, $$\begin{align}\psi'(f\land g([(x,y)]))=\psi'([f(x),g(y)])=\begin{cases}(f(x),g(y))&(f(x),g(y))\notin X' \lor Y'\\ \infty&(f(x),g(y))\in X' \lor Y'\end{cases}\end{align}$$whereas: $$(f,g)(\psi([x,y]))=(f,g)\left(\begin{cases}(x,y)&(x,y)\notin X\lor Y\\ \infty&(x,y)\in X \lor Y\end{cases}\right)=\begin{cases}(f(x),g(y))&(f(x),g(y))\notin X'\lor Y'\\ \infty&(f(x),g(y))\in X' \lor Y'\end{cases}$$
---
##### Examples
> [!h] Example 1
> We have that:
> 1. $S^p\land S^q\cong S^{p+q}$

> [!proof]-
> We have:
> 1. As $S^p$ and $S^q$ are both compact, by Proposition 1.4 $$S^p\land S^q\cong (\mathbb{R}^p\times \mathbb{R}^q)\cup \{ \infty \}\cong \mathbb{R}^{p+q}\cup \{ \infty \}\cong S^{p+q}$$

---
> [!lemma] Theorem 1
> We have that:
> 1. for all $n\geq 0$, there exists a continuous map $\gamma_{n}:(I^n,\partial I^n)\to (S^n,*)$ s.t. $\gamma_{n}|_{(I^n)^\circ}$ is a homeomorphism to its image. 
> 2. for all $n\geq 0$, there exist the following:
> 	1. a generator $a_{n}\in H_{n}(I^n,\partial I^n)\cong \mathbb{Z}$.
> 	2. a generator $s_{n}\in H_{n}(S^n,*)\cong \mathbb{Z}$ with $(\gamma_{n})_{*}(a_{n})=s_{n}$.
> 	3. a generator $d_{n}\in \tilde{H}_{n}(\partial I^{n+1})\cong \mathbb{Z}$ with $\partial_{*}(a_{n+1})=d_{n}$.

> [!proof]+
> We have that:
> 1. We define the maps $\gamma$ as follows:
> 	1. $\gamma_{0}:(I^0,\varnothing)\to(S^0,*)$ 