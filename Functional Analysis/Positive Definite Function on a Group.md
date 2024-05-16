#Definition #FunctionalAnalysis 

> [!definition]
> Let $G$ be a group and $\mathcal{H}$ a [[Hilbert Space|$\mathbb{C}$-Hilbert space]]. A ***positive-definite function*** on $G$ is a function $\Phi:G\to \mathcal{B}(\mathcal{H})$ s.t. for every $g_{1},\dots,g_{n}\in G$ and $x_{1},\dots,x_{n}\in \mathcal{H}$, $$\sum_{i,j=1}^{n}\braket{ \Phi(g_{j}^{-1}g_{i})x_{i} , x_{j} } \geq 0$$
- **Remark**: If $\mathcal{H}=\mathbb{C}$, using that $\mathcal{B}(\mathbb{C})\cong \mathbb{C}$, a function $\Phi:G\to \mathbb{C}$ is ***positive definite*** if for every $g_{1},\dots,g_{n}\in G$ and $c_{1},..,c_{n}\in \mathbb{C}$ s.t. $$\sum_{i,j=1}^{n}\Phi(g_{j}^{-1}g_{i})c_{i}\overline{c_{j}}\geq 0$$
---
##### Properties

> [!lemma] Lemma 1
> Let $\Phi:G\to \mathbb{C}$ be positive definite. Then,
> 1. $\Phi(x ^{-1})=\overline{\Phi(x)}$ for all $x\in G$.
> 2. $\left| \Phi(x) \right|\leq \Phi(e)$ for all $x\in G$.
> 3. $\left| \Phi(x)-\Phi(y) \right|^{2}\leq 2\Phi(e)\text{Re}(\Phi(e)-\Phi(x  ^{-1}y))$ for every $x,y\in G$.

> [!proof]+
> We have:
> 1. Let $x\in G$ and $c\in \mathbb{C}$. Then, $$0\leq \Phi(e)+\Phi(x)$$
---
##### Examples
> [!h] Example 1 (Unitary Representation)
> Let $\pi:G\to \text{U}(\mathcal{H})$ be a [[unitary representation]]. Then, 
> 1. for any $v\in \mathcal{H}$, $\Phi:G\to \mathbb{C},g\mapsto \braket{ \pi(g)v , v }$ is positive definite.

> [!proof]-
> $$\sum_{i,j=1}^{n}\braket{ \pi(g_{j}^{-1}g_{i})v ,v  }c_{i}\overline{c_{j}}=\sum_{i,j=1}^{n}\braket{ c_{i}\pi(g_{i})v ,c_{j}\pi(g_{j})v  }=\left\| \sum_{i=1}^{n}c_{i}\pi(g_{i})v \right\| ^{2}\geq 0$$
---
