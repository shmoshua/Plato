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
> Let $G=(V,E)$ and $\{ w_{v} \}_{v\in V}\subseteq \mathbb{R}_{\geq 0}$. The ***oracle LP*** on $\{ w_{v} \}_{v\in V}$ is defined as:$$\begin{array}{rll}\max&\sum_{e\in E}^{}x_{e}\\\text{subject to}&\sum_{v\in V}^{}w_{v}\sum_{e\ni v}^{}x_{e}\leq \sum_{v\in V}^{}w_{v} & \\&0\leq x_{e}\leq 1&\forall e\in E\end{array}$$Now, consider the following algorithm: 
> ```pseudo
> \begin{algorithm} \caption{MWUMatching($G,\varepsilon$)}
> \begin{algorithmic} 
> \State $w^{(1)}\gets 1$
> \For{$t=1,\dots,T:=8n\ln n / \varepsilon^{2}$}
> \State $x^{(t)}\gets$ \Call{OracleLP}{$w^{(t)}$}
> \State $w^{(t+1)}_{v}\gets \left( 1+ \frac{\varepsilon}{2n}\sum_{e\ni v}^{}x^{(t)}_{e} \right)w^{(t)}_{v}$
\EndFor
> \Return $\overline{x}:=\frac{1}{T}\sum_{t\in [T]}^{}x^{(t)}$
> \end{algorithmic}
> \end{algorithm}
> ```
> Then, for the output $\overline{x}$, 
> 1. $\sum_{e\in E}^{}\overline{x}_{e}\geq \text{OPT}_{LP}$
> 2. $\sum_{e\ni v}^{}\overline{x}_{e}\leq 1+\varepsilon$ for all $v\in V$

> [!proof]+
> We have that:
> 1. Let $x$ be a feasible solution to the LP relaxation of maximum matching problem. Therefore, $\text{OPT}_{LP}\leq \text{OPT}_{\text{Oracle}LP}$ for any $w$. Hence, we have that: $$\sum_{e\in E}^{}\overline{x}_{e}=\frac{1}{T}\sum_{t\in [T]}^{}\underbrace{ \sum_{e\in E}^{}x^{(t)}_{e} }_{ \geq \text{OPT}_{LP} }\geq \text{OPT}_{LP}$$
> 2. We have the following claims. Let $W^{(t)}:=\sum_{v\in V}^{}w_{v}^{(t)}$. Then,
> 	1. **Claim 1**: $W^{(T+1)}\leq n\cdot\exp(\eta T)$
> 	   
> 	   We have that for all $t$: $$\begin{align}W^{(t+1)}&=\sum_{v\in V}^{}w_{v}^{(t+1)}=\sum_{v\in V}^{}\left( 1+ \frac{\varepsilon}{2n}\sum_{e\ni v}^{}x_{e}^{(t)} \right)w_{v}^{(t)}\\&=W^{(t)}+ \frac{\varepsilon}{2n} \sum_{v\in V}^{}w_{v}^{(t)}\sum_{e\ni v}^{}x_{e}^{(t)}\leq (1+ \frac{\varepsilon}{2n})W^{(t)}\end{align}$$Hence, $W^{(T+1)}\leq(1+ \frac{\varepsilon}{2n})^Tn\leq n\exp \left( \frac{\varepsilon}{2n} T \right)$.
> 	
> 	Assume that there exists $v\in V$ s.t. $\sum_{e\ni v}^{}\overline{x}_{e}>1+\varepsilon$. Then, $\sum_{t\in [T]}^{}\sum_{e\ni v}^{}x^{(t)}_{e}>T(1+\varepsilon)$. Further, we have: $\sum_{e\ni v}^{}x_{e}^{(t)}\leq n$. 
> 	$$\begin{align}w^{(T+1)}_{v}=\prod_{t=1}^{T}\left( 1+ \frac{\varepsilon}{2n} \sum_{e\ni v}^{}x_{e}^{(t)} \right)&\geq\prod_{t=1}^{T}\exp \left( \eta \sum_{e\ni v}^{}x_{e}^{(t)}-\eta^{2}\left( \sum_{e\ni v}^{}x_{e}^{(t)} \right)^{2}  \right)\\&\geq\exp \left( \eta \sum_{t\in[T]}^{}\sum_{e\ni v}^{}x_{e}^{(t)}-\eta^{2} \sum_{t\in[T]}^{}\left( \sum_{e\ni v}^{}x_{e}^{(t)} \right)^{2}  \right)\\&\geq\exp \left( \eta \sum_{t\in[T]}^{}\sum_{e\ni v}^{}x_{e}^{(t)}-\eta^{2} \sum_{t\in[T]}^{}\left( \sum_{e\ni v}^{}x_{e}^{(t)} \right)^{2}  \right) \end{align}$$