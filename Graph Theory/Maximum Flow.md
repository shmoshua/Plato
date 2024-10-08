#Definition #GraphTheory #Algorithms 

> [!definition]
> Let $G=(V,E)$ be a [[Graph|directed graph]]. For a ***capacity function*** $c:E\to \mathbb{R}_{\geq 0}$ and a ***source*** $s\in V$ and a ***sink*** $t\in V$, 
> 1. the ***maximum flow problem*** aims to find: $$f^{*}\in \underset{ f\text{ feasible flow} }{ \arg\max }\text{ val}(f) $$where $\text{val}(f):=\sum_{w\in \text{out}(s)}^{}f(s,w) - \sum_{w\in \text{in}(t)}^{}f(w,t)$ defines the [[Flow (Graph)|flow value]].
- **Remark**: The max-flow problem is a convex optimization problem but not a strongly convex optimization, as solutions are not unique.
---
##### Properties
> [!lemma] Proposition 1
> There always exists a max flow $f^{*}$ that has a [[Flow (Graph)|path-cycle decomposition]] made up of only path flows. 

> [!proof]-
> Let $f$ be a max flow. Then, let $f_{1},\dots,f_{k}$ be the path-cycle decomposition of $f$ where wlog $f_{1},\dots,f_{\ell}$ are path flows and $f_{\ell+1},\dots,f_{k}$ are cycles. Then, define $f^{*}:=\sum_{i=1}^{\ell}f_{i}$. 
> 1. **Claim 1: $\text{val}( f^{*} )=\text{val} (f )$**
>    We have that: $$\begin{align}\text{val} (f ) &=\sum_{i=1}^{k}\left( \sum_{w\in \text{out}(s)}^{}f_{i}(s,w) - \sum_{w\in \text{in}(t)}^{}f_{i}(w,t) \right) \\&=\sum_{i=1}^{\ell}\left( \sum_{w\in \text{out}(s)}^{}f_{i}(s,w) - \sum_{w\in \text{in}(t)}^{}f_{i}(w,t) \right)=\text{val}( f^{*} )\end{align}$$
> 2. **Claim 2: $f^{*}$ is feasible**
>    We have that $f^{*}\leq f\leq c$.
---
