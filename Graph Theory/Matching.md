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

---
> [!lemma] Theorem 2 (MWU)
> Let $G=(V,E)$ and $\{ w_{v} \}_{v\in V}\subseteq [0,1]$. The ***oracle LP*** on $\{ w_{v} \}_{v\in V}$ is defined as:$$\begin{array}{rll}\max&\sum_{e\in E}^{}x_{e}\\\text{subject to}&\sum_{v\in V}^{}w_{v}\sum_{e\ni v}^{}x_{e}\leq \sum_{v\in V}^{}w_{v} & \\&0\leq x_{e}\leq 1&\forall e\in E\end{array}$$Now, consider the following algorithm: 
> ```pseudo
> \begin{algorithm} \caption{MWUMatching($G,\varepsilon$)}
> \begin{algorithmic} 
> \State $w\gets 1$
> \For{$t=1,\dots,T:=$}
> \State $x\gets$ \Call{OracleLP}{$w$}
> \State $w_{v}\gets (1+\varepsilon \sum_{e\ni v}^{}x_{e}$
\EndFor
> 
\end{algorithmic}
\end{algorithm}
```