#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be an [[graph|undirected graph]]. For a pair of vertices $a,b\in V$, the ***effective resistance*** is given as: $$R_{\text{eff}}(a,b):=\min_{Bf=e_{b}-e_{a}}f^\top Rf$$where $B$ is the [[Graph Matrices|edge-vertex incidence matrix]] and $R$ is the resistance matrix. 

---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $R_{\text{eff}}(a,b)=(e_{b}-e_{a})^\top L^+(e_{b}-e_{a})=\left\| L^{+ / 2}(e_{b}-e_{a}) \right\|^{2}_{2}$. 

> [!proof]+
> We have that:
> 1. we have that $\tilde{f}:= R^{-1}B\tilde{x}$ and $B\tilde{f}=(e_{b}-e_{a})$. Then, $\tilde{f}=\arg\min_{Bf=e_{b}-ea}$