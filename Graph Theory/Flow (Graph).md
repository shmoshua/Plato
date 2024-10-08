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
