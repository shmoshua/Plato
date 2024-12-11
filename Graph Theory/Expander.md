#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be an [[Graph|undirected graph]]. For any $0<\phi\leq 1$, 
> 1. A [[Cut (Graph)|cut]] $(S, V\backslash S)$ is ***$\phi$-sparse*** if $\left| E(S, V \backslash S) \right|<\phi\min \left\{  \sum_{v\in S}^{}d(v), \sum_{v\in V \backslash S}^{}d(v)  \right\}$.
> 2. $G$ is a ***$\phi$-expander*** if $G$ contains no $\phi$-sparse cut.