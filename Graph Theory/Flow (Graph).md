#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a [[Graph|directed graph]]. For a ***source*** $s\in V$ and a ***sink*** $t\in V$, a ***$s$-$t$-flow*** is a map $f: E\to \mathbb{R}$ s.t.
> 1. **conservation**: $\sum_{w \in \text{out}(v)}^{}f(v,w)=\sum_{w\in \text{in}(v)}^{}f(w,v)$ for all $v\in V \backslash \{ s,t \}$

- **Related definition**: Given a capacity $c:E \to \mathbb{R}_{\geq 0}$, a flow $f$ is ***feasible*** if $0\leq f\leq c$.
- **Related definition**: The ***flow value*** $\left| f \right|$ is given by $\left| f \right|:=\sum_{w\in \text{out}(s)}^{}f(s,w) - \sum_{w\in \text{in}(t)}^{}f(w,t)$.
- **Related definition**: A flow $f$ is a:
	1. ***$(s,t)$-path flow*** if $f=\alpha \cdot \chi_{p}$ for some $\alpha\in \mathbb{R}$ where $p$ is a $(s,t)$-path.
	2. ***cycle flow*** if $f=\alpha \cdot \chi_{c}$ for some $\alpha \in \mathbb{R}$ where $c$ is a cycle.
---
##### Properties

> [!lemma] Proposition 1 (Path-Cycle Decomposition)
> Let $f$ be a feasible $(s,t)$-flow. Then,
> 1. there exists $k\leq \left| \text{supp}(f) \right|$ and $f_{1},\dots,f_{k}$ where $f_{i}$ is either a feasible $(s,t)$-path flow or a feasible cycle flow s.t. $f=\sum_{i=1}^{k}f_{i}$.

> [!proof]-
> We prove it by induction on $m:=\left| \text{supp}(f) \right|$. 
> 
> 1. If $m=0$, then $f=0$ and there is nothing to do. 
> 1. If $m\geq 1$, then we have the three cases:
> 	1. there exists an $(s,t)$-path $p$ s.t. $p\subseteq \text{supp}(f)$. Then, let $\alpha:=\min_{e\in p}f(e)>0$. Then, $g:= f-\alpha \cdot \chi_{p}$ is a non-negative flow and $\left| \text{supp}(g) \right|<\left| \text{supp}(f) \right|$. Hence, by induction hypothesis, we have our statement.
> 	2. there exists a cycle $c$ s.t. $c\subseteq \text{supp}(f)$. Then, analogously to case 1, it holds.
> 	3. there exists no path or cycle contained in $\text{supp}(f)$. This implies there exists a node $v\neq s,t$ s.t. it has an incoming edge in $\text{supp}(f)$ but no outgoing edge. This is however a contradiction.
---

> [!lemma] Proposition 2
> Let $f$ be a flow. 
> 1. If there is no $(s,t)$-path in $\text{supp}(f)$, then for $S:=\{ v\in V: \exists (s,v)\text{-path in supp}(f) \}$, $(S,V \backslash S)$ is a [[Cut (Graph)|cut]] with $c_{f}(S)=0.$

> [!proof]-
> We have:
> 1. Assume that $c_{f}(S)>0$. Then, there exists $e\in E\cap (S\times V \backslash S)$ with $f(e)>0$. Let $e=(u,v)$. As $u$ is reachable in $\text{supp}(f)$ and $e\in \text{supp}(f)$, $v$ is reachable in $\text{supp}(f)$ which is a contradiction.

---
> [!lemma] Theorem (Lower Bounds)
> Let $G=(V,E)$ be a directed graph and $\ell,u:E\to \mathbb{R}_{\geq 0}$ be the lower bound and upper bound functions. Then, we define a flow network $G'$ where:
> 1. $V(G'):=V \cup \{ s',t' \}$
> 2. $E(G'):=E \cup \{ s' \to v \}_{v\in V}\cup \{ v\to t' \}_{v\in V}\cup \{ t\to s \}$
> 
> Then, TFAE:
> 1. $G$ has a feasible $(s,t)$-flow.
> 2. $G'$ has a saturating $(s',t')$-flow.

> [!proof]+
> We have:
> 1. (1=>2): Let $f: E\to \mathbb{R}$ be a feasible $(s,t)$-flow in $G$. Then, we can extend this into the following $f':E'\to \mathbb{R}$ where: $$\begin{align}f'()\end{align}$$