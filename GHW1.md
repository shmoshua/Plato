### 1. Well-Spaced Subsets
1. (5min) Assume there is a well-spaced subset $S\subseteq V$ s.t. $\left| S \right|=k+1$ wlog. Note that for any $v\in S$, $N(v)\subseteq V \backslash S$ and $N(v)\cap N(w)=\varnothing$ for all $v,w\in S$. However, there are $3k-1$ vertices and $3k+3$ neighbors. Hence, there exists at least one vertex that is common by pigeonhole, contradiction.
2. Greedy algorithm. We denote $B_{2}(v)$ as the radius $2$-ball of $v$. We choose $S$ as follows. Let $B$ denote the set of "blocked" vertices. 
	1. In the beginning, we have $S,B=\varnothing$. Add $s_{1}:=\arg\min_{v\in V(G)}\left| B_{2}(v) \right|$ to $S$ and set $B=B_{2}(s_{1})$. 
	2. At each step, choose $s_{i}:=\arg\min_{v\in D_{1}(B)\backslash B}$
---
### 2. Disjoint Reward Maximization
1. (5min) We have the ILP: $$\begin{array}{rl}\text{max}&\sum_{S\in \mathcal{F}}^{}r_{S}x_{S}\\\text{subject to}&\sum_{S:i\in S}^{}x_{S}=1&\forall i\in \mathcal{X}\\&x_{S}\in \{ 0,1 \}&\forall S\in \mathcal{F}\end{array}$$We can relax this into the LP $$\begin{array}{rl}\text{max}&\sum_{S\in \mathcal{F}}^{}r_{S}x_{S}\\\text{subject to}&\sum_{S:i\in S}^{}x_{S}\leq 1&\forall i\in \mathcal{X}\\&0\leq x_{S}\leq 1&\forall S\in \mathcal{F}\end{array}$$
2. (15min) Let $x^{*}_{S}$ be the optimum for the LP. Then, $\sum_{S\in \mathcal{F}}r_{S}x^{*}_{S}\geq \text{OPT}$. Now, let $y_{S}\sim \text{Ber}(x^{*}_{S}\cdot p)$ for all $S\in \mathcal{F}$. Then, we define $\mathcal{G}:=\{ S\in \mathcal{F}:y_{S}=1 \}$. Now, from $\mathcal{G}$, we delete any subsets that are not disjoint. Let this new family be called $\tilde{\mathcal{G}}$.
   
   Now, let $S\in \mathcal{F}$ and $i\in S$. Then, $$\mathbb{E}[\left| \{ T\neq S\in \mathcal{F}:i\in T \} \right| ]=\sum_{T}^{}$$