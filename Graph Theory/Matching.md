#Definition #Algorithms #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a [[graph]]. $M\subseteq E$ is a ***matching*** if:
> 1. $e\cap f=\varnothing$ for all $e,f\in M$.
- **Related definition**: A matching $M$ is:
	1. ***maximal*** if there is no other matching $M'\supseteq M$ with $\left| M' \right|> \left| M \right|$.
	2. ***maximum*** if there is no other matching $M'$ with $\left| M' \right|> \left| M \right|$.
- **Remark**: The maximum matching problem can be written in ILP as follows: $$\begin{array}{rll}\max&\sum_{e\in E}^{}x_{e}\\\text{subject to}&\sum_{e\ni v}^{}x_{e}\leq 1 & \forall v\in V\\&x_{e}\in \{ 0,1 \}&\forall e\in E\end{array}$$
---
##### Properties
> [!lemma] Theorem (Bipartite Maximum Matching)
> Let $G=(V,E)$ be a bipartite graph. Then, 
> 