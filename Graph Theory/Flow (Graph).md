#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a [[Graph|directed graph]]. For a ***capacity function*** $c:E\to \mathbb{R}_{\geq 0}$, a ***flow*** is a map $f: E\to \mathbb{R}_{\geq 0}$ s.t. with ***source*** $s\in V(G)$ and ***sink*** $t\in V(G)$:
> 1. **conservation**: $\sum_{w \in \text{out}(v)}^{}f(v,w)=\sum_{w\in \text{in}(v)}^{}f(w,v)$ for all $v\in V(G) \backslash \{ s,t \}$
> 2. **capacity**: $f(e)\leq g(e)$ for all $e\in E$.