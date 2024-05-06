#Definition #Analysis 

> [!definition]
> Let $X$ be a [[topological space]] and $(Y,d)$ a [[metric space]]. A family $F\subseteq \mathcal{F}(X,Y)$ is ***equicontinuous at $x\in X$***, if for every $\varepsilon>0$, $x$ has a neighborhood $U\subseteq X$ s.t. $$d(f(x),f(y))<\varepsilon,\quad \forall y\in U,f\in F$$
---
##### Properties
---
##### Related Theorems
![[Compact-Open Topology#^40ff33]]
![[Compact-Open Topology#^e1d408|p]]

---
> [!lemma] Hihi


---
##### Examples
> [!h] Example 1
> Let $X=[0,1]$ and $Y=\mathbb{C}$. Then, 
> 1. $C^1([0,1])$ is equicontinuous.

> [!proof]+
> By mean value theorem, $$\left| f(x)-f(y) \right| \leq\sup \left| f' \right| \cdot \left| x-y \right| $$So for any $x\in X$ and $\varepsilon>0$, a