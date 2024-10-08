#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a [[Graph|directed graph]]. For a ***capacity function*** $c:E\to \mathbb{R}_{\geq 0}$ and a ***source*** $s\in V$ and a ***sink*** $t\in V$, a ***$s$-$t$-flow*** is a map $f: E\to \mathbb{R}_{\geq 0}$ s.t.
> 1. **conservation**: $\sum_{w \in \text{out}(v)}^{}f(v,w)=\sum_{w\in \text{in}(v)}^{}f(w,v)$ for all $v\in V \backslash \{ s,t \}$
> 2. **capacity**: $f(e)\leq g(e)$ for all $e\in E$.

- **Related definition**: The ***flow value*** $\left| f \right|$ is given by $\left| f \right|:=\sum_{w\in \text{out}(s)}^{}f(s,w) - \sum_{w\in \text{in}(t)}^{}f(w,t)$.
- **Related definition**: A flow $f$ is a:
	1. ***$(s,t)$-path flow*** if $f=\alpha \cdot \chi_{p}$ for some $\alpha\geq 0$ where $p$ is a $(s,t)$-path.
	2. ***cycle flow*** if $f=\alpha \cdot \chi_{c}$ for some $\alpha\geq 0$ where $c$ is a cycle.
---
##### Properties

> [!lemma] Proposition 1 (Path-Cycle Decomposition)
> Let $f$ be a $(s,t)$-flow. Then,
> 1. there exists $k\leq \left| \text{supp}(f) \right|$ and $f_{1},\dots,f_{k}$ where $f_{i}$ is either $(s,t)$-path flow or cycle flow s.t. $f=\sum_{i=1}^{k}f_{i}$.

> [!proof]-
> We prove it by induction on $m:=\left| \text{supp}(f) \right|$. 
> 
> 1. If $m=0$, then $f=0$ and there is nothing to do. 
> 1. If $m\geq 1$, then we have the three cases:
> 	1. there exists an $(s,t)$-path $p$ s.t. $p\subseteq \text{supp}(f)$. Then, let $\alpha:=\min_{e\in p}f(e)>0$. Then, $g:= f-\alpha \cdot \chi_{p}$ is a non-negative flow and $\left| \text{supp}(g) \right|<\left| \text{supp}(f) \right|$. Hence, by induction hypothesis, we have our statement.
> 	2. there exists a cycle $c$ s.t. $c\subseteq \text{supp}(f)$. Then, analogously to case 1, it holds.
> 	3. there exists no path or cycle contained in $\text{supp}(f)$. This implies there exists a node $v\neq s,t$ s.t. it has an incoming edge in $\text{supp}(f)$ but no outgoing edge. This is however a contradiction.
---
