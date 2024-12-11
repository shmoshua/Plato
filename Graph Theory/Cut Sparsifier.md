#Definition #Algorithms 

> [!definition]
> Let $G=(V,E)$ be an [[Graph|undirected graph]] on $n$ vertices with weights $w:E \to \mathbb{R_{\geq 0}}$. For $\varepsilon>0$, a ***cut sparsifier*** is a subgraph $H=(V,E')$ s.t. $E'\subseteq E$ with weights $w':E'\to \mathbb{R_{\geq 0}}$ s.t.
> 1.  $\left| E' \right|=\tilde{O}(n / \varepsilon^{2})$ and
> 2. $\left| w'(E_{H}(S, V \backslash S))-w(E_{G}(S, V \backslash S)) \right|\leq \varepsilon w(E_{G}(S, V \backslash S))$ for all $S\subseteq V$.
---
##### Properties
> [!lemma] Theorem 1 (Complete Graphs)
> Consider the following algorithm: 
> ```pseudo
> \begin{algorithm}\caption{CutSparsifierCompleteGraphs($n,\varepsilon$)}
> \begin{algorithmic} 
> \State $G\gets K_{n}$
> \State $p\gets 30\frac{\log n}{\varepsilon^{2}n}$
> \State $H\gets (V,\varnothing)$
> \For{$e=\{ u,v \}\in E(G)$}
> \State Add $e$ to $H$ with weight $w'(e)=1 / p$ with probability $p$ independently.\EndFor
> \Return $H$
\end{algorithmic}
\end{algorithm}
> ```
> Given $w=1$, 
> 1. $\text{CutSparsifierCompleteGraphs}$ returns a cut sparsifier for $K_{n}$ w.h.p.

> [!proof]-
> Let $S\subseteq V$ of size $k\leq n / 2$. Let $X_{e}$ be the indicator variable that $e\in H$. Let $X_{S}:=\sum_{e\in E_{G}(S,V \backslash S)}^{}X_{e}$. Then, $\mathbb{E}[X_{S}]=\left|  E_{G}(S,V \backslash S) \right|\cdot p$ and further $$w'(E_{H}(S,V \backslash S))=\sum_{e\in E_{G}(S, V \backslash S)}^{} \frac{1}{p}X_{e}=\frac{1}{p}X_{S}$$Therefore, $$\begin{align}\mathbb{P}\left( \left| \frac{1}{p}X_{S}-\frac{1}{p}\mathbb{E}[X_{S}] \right| \geq \frac{\varepsilon}{p} \mathbb{E}[X_{S}] \right)&=\mathbb{P}(\left| X_{S}-\mathbb{E}[X_{S}] \right| \geq \varepsilon \mathbb{E}[X_{S}])\\&\leq 2\exp \left( -\frac{\varepsilon^{2}p\left| E_{G}(S,V \backslash S) \right| }{3} \right) \end{align}$$As $G=K_{n}$, we have that $\left| E_{G}(S,V \backslash S) \right|\geq \frac{kn}{2}$. Therefore, $$\mathbb{P}(\left| w'(E_{H}(S, V \backslash S))-w(E_{G}(S, V \backslash S)) \right|> \varepsilon w(E_{G}(S, V \backslash S)))\leq 2\exp \left( -5k\log n \right)\leq 2n^{-5k}$$Bringing it all together, $$\begin{align}&\mathbb{P}\left( \exists k\leq \frac{n}{2},S\in {V \choose k} : \left| w'(E_{H}(S, V \backslash S))-w(E_{G}(S, V \backslash S)) \right|> \varepsilon w(E_{G}(S, V \backslash S)) \right)\\&\leq \sum_{k=1}^{n/2}{n \choose k}2n^{-5k}\leq \sum_{k=1}^{n/2}2n^{-4k}\leq 2n^{-4}\end{align}$$
> Further, let $X=\sum_{e\in{n \choose 2}}^{}X_{e}$. Then, $$\mathbb{P}\left( X\geq \frac{n\log^2n}{\varepsilon^{2}} \right)\leq \frac{\mathbb{E}[X]}{n\log^{2}n / \varepsilon^{2}}\leq \frac{15}{\log n}$$Therefore, w.h.p we have that $\left| E' \right|= O(n \log^{2} n / \varepsilon^{2})=\tilde{O}(n / \varepsilon^{2})$ and we have a cut sparsifier.
---
> [!lemma] Theorem 2 (Expanders)
> Consider the following algorithm: 
> ```pseudo
> \begin{algorithm}\caption{CutSparsifierExpanders($G,\phi,\varepsilon$)}
> \begin{algorithmic} 
> \State $\delta\gets \min_{v\in V}d(v)$
> \State $p\gets 15\frac{\log n}{\varepsilon^{2}\phi\delta}$
> \State $H\gets (V,\varnothing)$
> \For{$e=\{ u,v \}\in E(G)$}
> \State Add $e$ to $H$ with weight $w'(e)=1 / p$ with probability $p$ independently.\EndFor
> \Return $H$
\end{algorithmic}
\end{algorithm}
> ```
> We need that $\frac{15\log n}{\varepsilon^{2} \delta}\leq \phi$.



> [!proof]-
> Let $S\subseteq V$ of size $k\leq n / 2$. Since $G$ is a $\phi$-expander, we have that $\left| E(S, V \backslash S) \right|\geq \phi  k\delta$.
> 
> Let $X_{e}$ be the indicator variable that $e\in H$. Let $X_{S}:=\sum_{e\in E_{G}(S,V \backslash S)}^{}X_{e}$. Then, $\mathbb{E}[X_{S}]=\left|  E_{G}(S,V \backslash S) \right|\cdot p$ and further $$w'(E_{H}(S,V \backslash S))=\sum_{e\in E_{G}(S, V \backslash S)}^{} \frac{1}{p}X_{e}=\frac{1}{p}X_{S}$$Therefore, $$\begin{align}\mathbb{P}\left( \left| \frac{1}{p}X_{S}-\frac{1}{p}\mathbb{E}[X_{S}] \right| \geq \frac{\varepsilon}{p} \mathbb{E}[X_{S}] \right)&=\mathbb{P}(\left| X_{S}-\mathbb{E}[X_{S}] \right| \geq \varepsilon \mathbb{E}[X_{S}])\\&\leq 2\exp \left( -\frac{\varepsilon^{2}p\left| E_{G}(S,V \backslash S) \right| }{3} \right) \end{align}$$Therefore, $$\mathbb{P}(\left| w'(E_{H}(S, V \backslash S))-w(E_{G}(S, V \backslash S)) \right|> \varepsilon w(E_{G}(S, V \backslash S)))\leq 2\exp \left( -5\log n k\right)\leq 2n^{-5k}$$Bringing it all together, $$\begin{align}&\mathbb{P}\left( \exists k\leq \frac{n}{2},S\in {V \choose k} : \left| w'(E_{H}(S, V \backslash S))-w(E_{G}(S, V \backslash S)) \right|> \varepsilon w(E_{G}(S, V \backslash S)) \right)\\&\leq \sum_{k=1}^{n/2}{n \choose k}2n^{-5k}\leq \sum_{k=1}^{n/2}2n^{-4k}\leq 2n^{-4}\end{align}$$
> Further, let $X=\sum_{e\in E}^{}X_{e}$. Then, we have $\mathbb{E}[X]\leq \frac{15m\log n}{\varepsilon^{2}\phi\delta}$ and by Markov:$$\mathbb{P}\left( X\geq \frac{15 m\log^2n}{\varepsilon^{2}\delta} \right)\leq \frac{1}{\phi \log n}\leq \frac{\varepsilon^{2}\delta}{15\log^{2} n}$$Therefore, w.h.p we have that $\left| E' \right|= O(n \log^{2} n / \varepsilon^{2})=\tilde{O}(n / \varepsilon^{2})$ and we have a cut sparsifier.
---