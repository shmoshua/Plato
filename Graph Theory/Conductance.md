#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be an unweighted connected [[graph]]. 
> 1. for $S\subseteq V$, the ***conductance*** $\phi(S)$ of $S$ is given by: $$\phi(S):=\frac{e(S, V \backslash S)}{\min \{ \text{vol}(S),\text{vol}(V \backslash S) \}}$$where $\text{vol}(A):=\sum_{v\in A}^{}d(v)$. 
> 2. the ***conductance*** of $G$ is given by: $$\phi(G):=\min _{S\subseteq V}\phi(S)$$

- **Remark**: $\phi(S)=\phi(V \backslash S)$ for all $S\subseteq V$. 
- **Remark**: Finding the conductance of a graph is NP-hard.
---
