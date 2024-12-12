#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be an [[Graph|undirected graph]]. For any $0<\phi\leq 1$, 
> 1. A [[Cut (Graph)|cut]] $(S, V\backslash S)$ is ***$\phi$-sparse*** if $\left| E(S, V \backslash S) \right|<\phi\min \left\{  \text{vol}_{G}(S), \text{vol}_{G}(V \backslash S)  \right\}$.
> 3. $G$ is a ***$\phi$-expander*** if $G$ contains no $\phi$-sparse cut.
- **Related definition**: For $S\subseteq V$, the ***volume*** is defined as $\text{vol}_{G}(S):=\sum_{v\in S}^{}d_{G}(v)$. 
- **Related definition**: For a graph $G=(V,E)$, a partition $V_{1},\dots,V_{\ell}$ of $V$ is a ***$(\phi,M)$-expander decomposition*** if:
	1. $G[V_{i}]$ is a $\phi$-expander for all $i\in[\ell]$.
	2. $\sum_{i=1}^{\ell}e(V_{i}, V \backslash V_{i})\leq M$.
---
##### Properties

> [!lemma] Lemma 1 (Basic Lemma)
> For any $G=(V,E)$ and $S\subseteq V$:
> 1. $e(S, V )\leq \text{vol}_{G}(S)\leq 2e(S, V)$ 
> 2. $\text{vol}(S)+\text{vol}(V \backslash S)=2m$.
> 3. if $G$ is a connected $\phi$-expander, $\text{diam}(G)=4\log m / \phi$

> [!proof]-
> We have that:
> 1. The left inequality is trivial as every cut edge contributes to the volume. For the upper inequality, we have that: $$\sum_{v\in S}^{}d_{G}(v)$$
> 2. From the handshake lemma.
> 3. For any $v\in V$, let $r_{v}\geq 1$ s.t. $$\text{vol}(B_{\leq r_{v}-1}(v))\leq \frac{\text{vol}(V)}{2},\quad \text{vol}(B_{\leq r_{v}}(v))> \frac{\text{vol}(V)}{2}$$Since $G$ is connected. $r_{v}$ is well-defined for every $v$. Now, let $s,t\in V$. Then, 
> 	1. **Claim 1**: $B_{\leq r_{s}}(s)\cap B_{\leq r_{t}}(t)\neq\varnothing$.
> 	   Assume otherwise. Then, $\text{vol}(B_{\leq r_{s}}(s))+\text{vol}(B_{\leq r_{t}}(t))\leq \text{vol}(V)$ which is a contradiction to the definition of $r_{s}$ and $r_{t}$.
> 	2. **Claim 2**: For every $v\in V$, $r_{v}\leq 2\log m / \phi$. 
> 	   Let $r<r_{v}$. Then, by definition, $\text{vol}(B_{\leq r}(v))\leq \text{vol}(V) /2$. Now as $G$ is a $\phi$-expander, we have: $$e(B_{\leq r}(v), V \backslash B_{\leq r}(v))\geq \phi \min \{ \text{vol}(B_{\leq r}(v)) ,\text{vol}(V \backslash B_{\leq r}(v)) \} = \phi \text{vol}(B_{\leq r}(v))  $$Further, we have that: $$\text{vol}(B_{\leq r+1}(v))\geq \text{vol}(B_{\leq r}(v))+e(B_{\leq r}(v), V \backslash B_{\leq r}(v))\geq(1+\phi)  \text{vol}(B_{\leq r}(v))$$Hence, we have that $\text{vol}(B_{\leq r}(v))\geq (1+\phi)^r\geq e^{r\phi/2}$. If $r> 2 \log m /\phi$, then: $$\text{vol}(B_{\leq r}(v))> m=\text{vol}(V) / 2$$Therefore, $r_{v}\leq 2 \frac{\log m}{\phi}$.
> 	   
> 	Hence, for any $s,t\in V$, we have that: $$\text{dist}(s,t)\leq r_{s}+r_{t}\leq \frac{4\log m}{\phi}$$
---
> [!lemma] Proposition 2 (Minimum Cut)
> Let $G=(V,E)$ be a simple $(2 / \delta(G))$-expander. Then,
> 1. All minimum cuts of $G$ are singleton.

> [!proof]-
> Let $C\subseteq V$ be a vertex set inducing a minimum cut, i.e. $e(C, V \backslash C)=\lambda(G)$. Then, we have that: $$\frac{2}{\delta(G)}\leq\phi(G)\leq \phi(C)=\frac{\lambda(G)}{\min\{ \text{vol}(C),\text{vol}(V \backslash C) \}}$$
> Now, wlog assume that $\left| C \right|\leq \left| V \backslash C \right|$. Then,
> $$\delta(G)\geq \lambda(G)\geq \frac{2}{\delta(G)}\min\{ \text{vol}(C),\text{vol}(V \backslash C) \}\geq \frac{2}{\delta(G)}\delta(G)\left| C \right| =2\left| C \right| $$We can now assume that $\left| C \right|\geq 2$. Then, for any $v\in C$, $$e(v, V \backslash C)\geq \delta(G)-(\left| C \right| -1)>\delta(G) / 2$$However, we have: $$e(C, V \backslash C)> \left| C \right| \delta(G) /2 \geq \delta(G)\geq \lambda(G)$$which is a contradiction.
---
> [!lemma] Theorem 3 (Expander Decomposition)
> Consider the following algorithm:
> ```pseudo
> \begin{algorithm} \caption{ExpanderDecomposition($G,\phi$)}
> \begin{algorithmic} 
> \If{$G$ is a $\phi$-expander}
> \Return $G$
\EndIf
> \State $(S,V \backslash S)\gets \phi$-sparse cut in $G$.
> 
\Return \Call{ExpanderDecomposition}{$G[S],\phi$}$\sqcup$ \Call{ExpanderDecomposition}{$G[V \backslash S],\phi$}
\end{algorithmic}
\end{algorithm}
> ```
> Then, for every $0<\phi<1$, the algorithm returns a $(\phi,M)$-expander decomposition where $M=2\phi m\log(2m)=O(\phi m\log m)$.

> [!proof]-
> Let $V_{1},\dots,V_{\ell}$ be the output of the algorithm. By construction, $G[V_{i}]$ is a $\phi$-expander for all $i\in[\ell]$.
> 
> 
> 
> Let $(S,V_{i} \backslash S)$ be a $\phi$-sparse cut in $G$ where wlog $\text{vol}(S)\leq \text{vol}( V \backslash S)$. Then, we have that $e(S, V \backslash S)<\phi \text{vol}(S)$. Then, we charge each vertex $u\in S$ with $\phi \cdot d(u)$ charge. Then, we have that: $$e(S, V \backslash S)<\phi \text{vol}(S)=\sum_{v\in S}^{}\text{charge}(v)$$
> 
> As $\text{vol}(V)=2m$ and the volume at least halves at every step, each vertex receives charges in at most $\log (2m)$ iterations. Hence, we have that $\text{charge}(v)\leq \phi \cdot d(v)\cdot \log(2m)$. Hence, we have that: $$\sum_{i\in[\ell]}^{}e(V_{i}, V \backslash V_{i})\leq \sum_{v\in V}^{}\text{charge}(v)\leq 2m\phi \log(2m)$$
- **Remark**: Given that finding a sparse cut is $\mathcal{NP}$-hard, 

---
> [!lemma] Theorem 4
> Consider the following algorithm:
> ```pseudo
> \begin{algorithm} \caption{Expander($G=(V,E)$)}
> \begin{algorithmic} 
> \State $\phi\gets \left\lfloor \frac{1}{8 \log 4m}\right\rfloor$
> \State $G'\gets$ $G$ but $\Delta:= m / n$ self-loops added to each $v\in V$.
> \State $V_{1},\dots,V_{k}\gets$ \Call{ExpanderDecomposition}{$G',\phi$}
> \Return $G[V_{1}],\dots,G[V_{k}]$
\end{algorithmic}
\end{algorithm}
> ```
> The algorithm returns a $\{ G_{i}:=(V_{i},E_{i}) \}_{i\in[k]}$ where:
> 1. $G_{i}$ is a $\tilde{\Omega}(1)$-expander for all $i\in[k]$.
> 2. $E=\bigsqcup_{i\in[k]} E_{i}$.
> 3. $\delta(G_{i})=\tilde{\Omega}(e(G_{i}) / v(G_{i}))$ for all $i\in[k]$.
> 4. $\left| \{ i\in[k]:v\in V_{i} \} \right|=O(\log n)$ for all $v\in V$.



> [!proof]+
> Let $V_{1},\dots,V_{k}$ be the output from $\text{ExpanderDecomposition}(G',\phi)$. Then, we have: $$d_{G_{i}}(v)\geq e_{G}(v, V_{i}\backslash \{ v \})=e_{G'}(v, V_{i}\backslash \{ v \})\geq \phi \deg_{G'[V_{i}]}(v)\geq \phi \Delta$$Further, for every $G_{i}$, we have that $S\subseteq V_{i}$, $$e_{G_{i}}(S, V_{i}\backslash S)=e_{G'[V_{i}]}(S, V_{i}\backslash S)\geq \phi \min\{ \deg_{G'[V_{i}]}(S),\deg_{G'[V_{i}]}(V_{i} \backslash S) \}$$
---
##### Examples
> [!h] Example 1 (Path and Cycles)
> We have that
> 1. $P_{n}$ is a $\text{O}\left( \frac{1}{n} \right)$-expander.
> 2. $C_{n}$ is a $\text{O}\left( \frac{1}{n} \right)$-expander.
---
> [!h] Example 2 (Star)
> If $G=K_{1,t}$, a star on $t+1$ vertices. Then, for any cut, there exists a side that only contains leaves. Let this side be $S$. Then, $$\frac{e(S, V \backslash S)}{\min \{ \text{vol}(S),\text{vol}(V \backslash S) \}} =\frac{\left| S \right| }{\min \{  \left| S \right| ,2t-\left| S \right|  \}}\geq \frac{\left| S \right| }{\left| S \right| }=1$$Hence, $G$ is a $1$-expander.
---
> [!h] Example 1
> $K_{n}$ is a $\frac{1}{2}$-expander.

> [!proof]-
> Let $S\subseteq V$ with $\left| S \right|=k\leq n / 2$. Assume $(S,V\backslash S)$ is a $\frac{1}{2}$-sparse cut. Then, $$\frac{kn}{2}\leq|S||V \backslash S|=\left| E(S,V \backslash S) \right| < \frac{1}{2}(n-1)k$$which is a contradiction.
---
