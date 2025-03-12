#Definition #Algorithms #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a [[graph]]. 
> 1. a subset $M\subseteq E$ is a ***matching*** if $e\cap f=\varnothing$ for all $e,f\in M$.

^ba7938

- **Related definition**: A matching $M$ is: ^32ed75
	1. ***maximal*** if there is no other matching $M'\supseteq M$ with $\left| M' \right|> \left| M \right|$.
	2. ***maximum*** if there is no other matching $M'$ with $\left| M' \right|> \left| M \right|$.
	3. ***perfect*** if $\left| M \right|=\left| V(G) \right| / 2$.
- **Related definition**: For a graph $G$, $\nu(G)$ denotes the size of maximum matching. ^cf73c8
- **Remark**: The maximum matching problem can be written in ILP as follows: $$\begin{array}{rll}\max&\sum_{e\in E}^{}x_{e}\\\text{subject to}&\sum_{e\ni v}^{}x_{e}\leq 1 & \forall v\in V\\&x_{e}\in \{ 0,1 \}&\forall e\in E\end{array}$$
---
##### Properties
> [!lemma] Proposition 1 
> Let $G=(V,E)$ be a graph. Then,
> 1. $\nu(G)\leq \tau(G)\leq 2\nu(G)$ where $\tau(G)$ is the size of the minimum [[vertex cover]].

> [!proof]-
> See [[Vertex Cover]].
---
![[Vertex Cover#^c36b60]]

---
> [!lemma] Theorem 3 (Hall, 1929)
> Let $H:=(A\sqcup B,E)$ be bipartite. TFAE:
> 1. there exists a matching $M$ covering $A$. 
> 2. for all $S\subseteq A$, $\left| S \right|\leq \left| N(S) \right|$ where $N(S):= \bigcup_{v\in S}^{}N_{v}$.

> [!proof]-
> We have that:
> 1. (1=>2): Obvious as $M$ covers $A$.
> 2. (2=>1): We show this via induction on $\left| A \right|$.
> 	1. Let $\left| A \right|=1$. If 2 holds, then for $A=\{ v \}$, we have $d(v)\geq 1$. Hence, there exists a matching $M$ covering $A$ with $\left| M \right|=1$. Conversely, if there exists a matching covering $A$, we have that $\left| N(A) \right|\geq 1$.
> 	2. Let $\left| A \right|\geq 2$. Assume that $\left| S \right|\leq \left| N(S) \right|$ for all $S\subseteq A$.
> 		1. If $\left| N(S) \right|\geq \left| S \right|+1$ for every non-empty $S\subsetneq A$, then pick any $u$ in $A$ and as $\left| N_{u} \right|\geq 1$, we can also pick $v\in N_{u}$. Then, define $e:=uv$ and $H':= H \backslash e=(A'\sqcup B',E')$. We then have for all $S\subseteq A'$, $$\left| N_{H'}(S) \right| \geq \left| N_{H}(S) \right| -1\geq \left| S \right| +1-1=\left| S \right| $$Hence, there exists a matching $M'$ in $H'$ covering $A'$. With $e$, this creates a matching covering $A$.
> 		2. Otherwise, there exists a non-empty $S\subsetneq A$ s.t. $\left| N(S) \right|= \left| S \right|$. Let $R:= A \backslash S$ and $T:= B \backslash N(S)$. Then, by definition $e(S,T)=0$. We claim that $H_{1}:=H[S\sqcup N(S)]$ and $H_{2}:=H[R\sqcup T]$ satisfy 2. 
> 		   
> 		   For $H_{1}$, for any $S'\subseteq S$, $\left| N_{H_{1}}(S') \right|=\left| N_{H}(S') \right|\geq \left| S' \right|$. For $H_{2}$, for any $S'\subseteq R$, if $\left| N_{H_{2}}(S') \right|< \left| S' \right|$, then: $$\left| N_{H}(S\cup S') \right|=\left| N_{H}(S) \right| +\left| N_{H_{2}}(S') \right| +e(S,T)<\left| N_{H}(S') \right| +\left| S' \right| =\left| S \right| +\left| S' \right|  $$which is a contradiction as $\left| S\cup S' \right|=\left| S \right|+\left| S' \right|$.
> 		   
> 		   Hence, by induction we have disjoint matchings that cover $S$ and $R$ and this together covers $A$.
> 
> This proves the theorem.
---
> [!lemma] Theorem (Bipartite Maximum Matching)
> Let $G=(V,E)$ be a bipartite graph. Then, 

---
##### Matching Algorithms
> [!lemma] Theorem 1 (MWU)
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

> [!proof]-
> We have that:
> 1. Let $x$ be a feasible solution to the LP relaxation of maximum matching problem. Therefore, $\text{OPT}_{LP}\leq \text{OPT}_{\text{Oracle}LP}$ for any $w$. Hence, we have that: $$\sum_{e\in E}^{}\overline{x}_{e}=\frac{1}{T}\sum_{t\in [T]}^{}\underbrace{ \sum_{e\in E}^{}x^{(t)}_{e} }_{ \geq \text{OPT}_{LP} }\geq \text{OPT}_{LP}$$
> 2. We have the following claims. Let $W^{(t)}:=\sum_{v\in V}^{}w_{v}^{(t)}$. Then,
> 	1. **Claim 1**: $W^{(T+1)}\leq n\cdot\exp(\eta T)$
> 	   
> 	   We have that for all $t$: $$\begin{align}W^{(t+1)}&=\sum_{v\in V}^{}w_{v}^{(t+1)}=\sum_{v\in V}^{}\left( 1+ \frac{\varepsilon}{2n}\sum_{e\ni v}^{}x_{e}^{(t)} \right)w_{v}^{(t)}\\&=W^{(t)}+ \frac{\varepsilon}{2n} \sum_{v\in V}^{}w_{v}^{(t)}\sum_{e\ni v}^{}x_{e}^{(t)}\leq (1+ \frac{\varepsilon}{2n})W^{(t)}\end{align}$$Hence, $W^{(T+1)}\leq(1+ \frac{\varepsilon}{2n})^Tn\leq n\exp \left( \frac{\varepsilon}{2n} T \right)$.
> 	
> 	Assume that there exists $v\in V$ s.t. $\sum_{e\ni v}^{}\overline{x}_{e}>1+\varepsilon$. Then, $\sum_{t\in [T]}^{}\sum_{e\ni v}^{}x^{(t)}_{e}>T(1+\varepsilon)$. Further, we have: $\sum_{e\ni v}^{}x_{e}^{(t)}\leq n$. 
> 	$$\begin{align}w^{(T+1)}_{v}=\prod_{t=1}^{T}\left( 1+ \frac{\varepsilon}{2n} \sum_{e\ni v}^{}x_{e}^{(t)} \right)&\geq\prod_{t=1}^{T}\exp \left( \eta \sum_{e\ni v}^{}x_{e}^{(t)}-\eta^{2}\left( \sum_{e\ni v}^{}x_{e}^{(t)} \right)^{2}  \right)\\&\geq\exp \left( \eta \sum_{t\in[T]}^{}\sum_{e\ni v}^{}x_{e}^{(t)}-\eta^{2} \sum_{t\in[T]}^{}\left( \sum_{e\ni v}^{}x_{e}^{(t)} \right)^{2}  \right)\\&\geq\exp \left( \eta \sum_{t\in[T]}^{}\sum_{e\ni v}^{}x_{e}^{(t)}-\eta^{2} \sum_{t\in[T]}^{}\left( \sum_{e\ni v}^{}x_{e}^{(t)} \right)^{2}  \right) \end{align}$$
---
> [!lemma] Theorem 2 (Streaming Perfect Matching)
> Any randomized single-pass streaming algorithm deciding whether a bipartite graph $G=(U\sqcup V ,E)$ has a perfect matching requires $\Omega(n^{2})$ space.

> [!proof]-
> We show that for any randomized algorithm using at most $cn^{2}$ bits, 
> 
> Let $k\in \mathbb{Z}_{\geq 0}$ and let $G=(U\sqcup V,E)$ be a bipartite graph where $U:=U_{1}\sqcup U_{2}$ and $V:=V_{1}\sqcup V_{2}$. We have that $\left| U_{1} \right|=\left| V_{1} \right|=k$ and $\left| U_{2} \right|=\left| V_{2} \right|=k-1$. Let $e_{1},\dots,e_{k^{2}}$ be a fixed order of edges between $U_{1}$ and $V_{1}$. 
> 
> We sample each edge $e_{i}$ uniformly at random, independently. This gives us 

---
##### Examples

> [!h] Example 1
> We have that:
> 1. $\nu(K_{n})= \left\lfloor \frac{n}{2}\right\rfloor$
> 2. $\nu(K_{r,s})=\min \{ r,s \}$.

^ef41f6

---
