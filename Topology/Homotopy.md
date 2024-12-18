#Definition #Topology 

> [!definition]
> Let $X,Y$ be [[Topological Space|topological spaces]] and $f_{0},f_{1}\in Y^X$ continuous maps. A ***homotopy*** $h$ from $f_{0}$ to $f_{1}$ is a continuous map: $h:X\times[0,1]\to Y$ s.t. 
> 1. $h(x,0)=f_{0}(x)$ for all $x\in X$.
> 2. $h(x,1)=f_{1}(x)$ for all $x\in X$.
> 
> $f_{0}$ and $f_{1}$ are called ***homotopic***, if such homotopy exists.

^420cea

- **Related definition**: ***Homotopy type*** is an equivalence relation defined on topological spaces s.t. $X\sim Y$ if and only if there exists continuous $f:X\to Y$ and $g:Y\to X$ s.t. $f\circ g$ is homotopic to $\text{id}_{Y}$ and $g\circ f$ is homotopic to $\text{id}_{X}$. $f$ is called ***homotopy equivalence***. ^9863c7
- **Related definition**: A homotopy $h$ from $f_{0}$ to $f_{1}$ is ***relative to*** $A\subseteq X$ if $h(a,t_{1})=h(a,t_{2})$ for all $t_{1},t_{2}\in [0,1]$ and $a\in A$. We write that $f_{0}\sim f_{1}(\mathrm{Re})$
---
##### Properties
> [!lemma] Proposition 1
> For topological spaces $X,Y,Z$, 
> 1. $f\sim g \iff f$ and $g$ are homotopic forms an equivalence relation on $C(X,Y)$. We denote with $[X,Y]$ the set of equivalence classes. 
> 2. Homotopy is compatible with composition: let $f_{1},f_{2}\in C(X,Y)$ and $g_{1},g_{2}\in C(Y,Z)$ s.t. $f_{1}\sim f_{2}$ and $g_{1}\sim g_{2}$. Then, $g_1\circ f_{1} \sim g_{2}\circ f_{2}$.

^b0fd45

> [!proof]-
> We have:
> 1. For any $f\in C(X,Y)$, $h(x,t)=f(x)$ is a homotopy from $f$ to $f$. If $f\sim g$ with homotopy $h$, $h(x,t)=h(x,1-t)$ gives a homotopy from $g$ to $f$. Finally, let $f_{0}\sim f_{1}$ and $f_{1}\sim f_{2}$ with homotopy $h_{1}$ and $h_{2}$ respectively. Then, $$h(x,t)=\begin{cases}h_{0}(x,2t)&0\leq t\leq \frac{1}{2}\\h_{1}(x,2t-1)& \frac{1}{2}\leq t\leq 1\end{cases}$$and $f_{0}\sim f_{2}$.
> 2. Let $h$ and $h'$ be the respective homotopies. Then, define: $$h''(x,t):=h'(h(x,t),t)$$which is continuous and: $h''(x,0)=h'(h(x,0),0)=g_{1}(f_{1}(x))$ and $h''(x,1)=h'(h(x,1),1)=g_{2}(f_{2}(x))$

^bd53f0

---
> [!lemma] Proposition 2
> We have that:
> 1. Homotopy type is an equivalence relation.
> 2. for a homotopic equivalence $f:X\to Y$, the homotopic inverse $g:Y\to X$ is unique up to homotopy.

^69c44b

> [!proof]-
> We have:
> 1. For topological space $X$, $\text{id}_{X}:X\to X$ is a homotopy equivalence. For $X$ with the same homotopy type as $Y$ with homotopy equivalence $f$, there exists $g$ by definition for which $g$ is a homotopy equivalence and $Y$ has the same homotopy type as $X$. Lastly, let $f:X\to Y$ and $f':Y\to Z$ be homotopic equivalences with $g,g'$ respectively. Then, consider $f'\circ f:X\to Z$ and $g\circ g':Z\to X$. We have that: $$\begin{array}{cccc} {h_{Z}:}&{Z\times[0,1]}&\to&{Z}\\&{(z,t)} &\mapsto & {f'(h_{f\circ g}(g'(z),t))} \end{array}{}$$is a homotopy from $f'\circ f\circ g\circ g'$ to $f'\circ g'$, where $h_{f\circ g}$ is the homotopy from $f\circ g$ to $\text{id}_{Y}$. As homotopies form an equivalence relation, $f'\circ f\circ g\circ g'$ is homotopic to $\text{id}_{Z}$. By symmetry, $X$ has the same homotopy type as $Z$.
> 2. Let $g,h:Y\to X$ s.t. $f\circ g \sim \text{id}_{Y}$, $g\circ f\sim \text{id}_{X}$, $f\circ h\sim \text{id}_{Y}$ and $h\circ f\sim \text{id}_{X}$. Then, $$g=g\circ \text{id}_{Y}\sim g\circ f\circ h\sim \text{id}_{X}\circ h=h$$This proves the statement.

^cba2c6

---
> [!lemma] Lemma 3
> If $X$ has the same homotopy type as a one-point space $\{ x_{0} \}$, then 
> 1. for any space $Y$, any continuous map $Y\to X$ is homotopic to a constant map and
> 2. for any space $Y$, any continuous map $X\to Y$ is homotopic to a constant map.

> [!proof]-
> Let $X$ have the same homotopy type as $\{ x_{0} \}$, then $X$ is contractible by Example 2 and there exists a constant map $f:X\to X$ s.t. $f\sim \text{id}_{X}$. Then, for any continuous $\varphi:Y\to X$, $\varphi=\text{id}_{X}\circ\varphi \sim f\circ\varphi$ which is a constant map. Similarly, for any continuous $\varphi:X\to Y$, $\varphi=\varphi \circ\text{id}_{X}\sim\varphi \circ f$, which is a constant map.
---
##### Examples
> [!h] Example 1
> Any two functions $f_{0},f_{1}:\mathbb{R}^n\to \mathbb{R}^m$ are homotopic with: $$\begin{array}{cccc} {h:}&{\mathbb{R}^n\times \mathbb{I}}&\to&{\mathbb{R}^m}\\&{(x,t)} &\mapsto & {(1-t)f_{0}(x)+tf_{1}(x)} \end{array}{}$$

^89e2c1

---
> [!h] Example 2
> Let $X$ be a topological space. TFAE:
> 1. $X$ has the same homotopy type as a one-point space $\{ x_{0} \}$.
> 2. $X$ is contractible.

^623c55

> [!proof]-
> Let $X$ have the same homotopy type as $\{ x_{0} \}$ and $f:X\to \{ x_{0} \}$ be the homotopy equivalence with homotopy inverse $g$ s.t. $f \circ g\sim \text{id}_{\{ x_{0} \}}$ and $g\circ f\sim \text{id}_{X}$. Then, $g\circ f:X\to X$ is a constant function homotopic to $\text{id}_{X}$ and $X$ is contractible. 
> 
> Conversely, assume $X$ is contractible and let $f:X\to X$ be the constant function homotopic to $\text{id}_{X}$ with $\text{Im }f=\{ x \}$. Then, we can define a constant functions $f':X\to \{ x_{0} \}$ and $g':\{ x_{0} \}\to X, x_{0}\mapsto x$ s.t. $g'\circ f'=f$. Finally, $f'\circ g'(x_{0})=x_{0}$ and we have that $f'\circ g'\sim \text{id}_{\{ x_{0} \}}$ from reflexivity.

^fb1fb4

---
> [!h] Example 3 (Rn - 0)
> We have that:
> 1. $\mathbb{R}^n \backslash \{ 0 \}$ is homotopy equivalent to $S^{n-1}$. 

^fc91a4

> [!proof]-
> Let us define two continuous functions. Take $i:S^{n-1}\hookrightarrow \mathbb{R}^n \backslash \{ 0 \}$ the inclusion and: $$r:\mathbb{R}^n \backslash \{ 0 \}\to S^{n-1},\quad x\mapsto \frac{x}{\|x\|}$$ Then, $r\circ i=\text{id}_{S^{n-1}}$ and it is left to show that $i\circ r\sim \text{id}_{\mathbb{R}^n \backslash \{ 0 \}}$. Let: $$h:\mathbb{R}^n \backslash \{ 0 \}\times[0,1]\to \mathbb{R}^n  \backslash \{ 0 \},\quad (x,t)\mapsto  tx+(1-t) \frac{x}{\|x\|}$$where we claim that $h(x,t)\neq 0$ for all $x,t$. Assume $h(x,t)=0$. Then, $$0=h(x,t)=\left( t+\frac{(1-t)}{\|x\|} \right)x $$Hence, $t+\frac{1-t}{\|x\|}=0$ and $\left( 1-\frac{1}{\|x\|} \right)t=-\frac{1}{\|x\|}$ which is a contradiction. Hence, we have that $h$ is continuous and this proves the statement.

^f58dcb

---
