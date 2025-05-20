#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be an [[graph|undirected graph]]. For a pair of vertices $a,b\in V$, the ***effective resistance*** is given as: $$R_{\text{eff}}(a,b):=\min_{Bf=e_{b}-e_{a}}f^\top Rf$$where $B$ is the [[Graph Matrices|edge-vertex incidence matrix]] and $R$ is the resistance matrix. 

---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $R_{\text{eff}}(a,b)=(e_{b}-e_{a})^\top L^+(e_{b}-e_{a})=\left\| L^{+ / 2}(e_{b}-e_{a}) \right\|^{2}_{2}$. 
> 2. $R_{\text{eff}}$ is a distance on $V$.

> [!proof]-
> We have that:
> 3. we have that $\tilde{f}:= R^{-1}B\tilde{x}$ and $B\tilde{f}=(e_{b}-e_{a})$. Then, $\tilde{f}=\arg\min_{Bf=e_{b}-e_{a}}f^\top Rf$. Therefore, $$R_{\text{eff}}(a,b)=\tilde{f}^\top R\tilde{f}=\tilde{x} ^\top L\tilde{x}$$However, as $L\tilde{x}=BR^{-1}B \tilde{x}=B\tilde{f}=e_{b}-e_{a}$ and $\tilde{x}=L^+(e_{b}-e_{a})$. Hence,$$R_{\text{eff}}(a,b)=(e_{b}-e_{a})^\top L^+ L L^+ (e_{b}-e_{a})=(e_{b}-e_{a})^\top L^+  (e_{b}-e_{a})$$