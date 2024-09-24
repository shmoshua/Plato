#Definition #Analysis 

> [!definition]
> Let $X$ be a [[Topological Space]] and $(Y,d)$ a [[Metric Space]]. A family $F\subseteq \mathcal{F}(X,Y)$ is ***equicontinuous at $x\in X$***, if for every $\varepsilon>0$, $x$ has a neighborhood $U\subseteq X$ s.t. $$d(f(x),f(y))<\varepsilon,\quad \forall y\in U,f\in F$$
---
##### Properties
> [!lemma] Proposition 1
> Let $X$ be a [[Topological Space]] and $(Y,d)$ be a [[Metric Space]]. If $\mathcal{F}\subseteq C(X,Y)$ is [[Compact Space|totally bounded]], then $\mathcal{F}$ is continuous.

> [!proof]-
> For $x\in X$ and $\varepsilon>0$. As $\mathcal{F}$ is totally bounded, let $\{ f_{1},..,f_{n} \}\subseteq \mathcal{F}$ be the $\varepsilon /3$ net. Then, $$U:=\bigcap_{k=1}^{n}f_{k}^{-1}(B_{< \varepsilon / 3}(f_{k}(x_{0})))$$is an open neighborhood of $x_{0}$. Therefore, for any $f\in\mathcal{F}$, there exists $k$ s.t. $$d(f(x),f(y))<d(f(x),f_{k}(x))+d(f_{k}(x),f_{k}(y))+d(f_{k}(y),f(y))<\varepsilon$$for all $y\in U$.
---
##### Related Theorems
![[Compact-Open Topology#^40ff33]]
![[Compact-Open Topology#^e1d408|p]]

---
##### Examples
> [!h] Example 1
> Let $X=[0,1]$ and $Y=\mathbb{C}$. Then, 
> 1. $C^1([0,1])$ is equicontinuous.

> [!proof]+
> By mean value theorem, $$\left| f(x)-f(y) \right| \leq\sup \left| f' \right| \cdot \left| x-y \right| $$So for any $x\in X$ and $\varepsilon>0$, a