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
> Let $\phi=\tilde{\Omega}(1)$, i.e. there exists $c$ s.t. $\phi=\Omega\left( \frac{1}{\log^c n} \right)$. Then, with high probability:
> 1. $\left| E' \right|=\tilde{O}(\frac{m}{\varepsilon^{2} \delta})$
> 2. $\left| w'(E_{H}(S, V \backslash S))-e_{G}(S, V \backslash S) \right|\leq \varepsilon w(E_{G}(S, V \backslash S))$ for all $S\subseteq V$.



> [!proof]-
> Let $S\subseteq V$ of size $k\leq n / 2$. Since $G$ is a $\phi$-expander, we have that $e_{G}(S, V \backslash S)\geq \phi  k\delta$.
> 
> Let $X_{e}$ be the indicator variable that $e\in H$. Let $X_{S}:=\sum_{e\in E_{G}(S,V \backslash S)}^{}X_{e}$. Then, $\mathbb{E}[X_{S}]=e(S,V \backslash S) \cdot p$ and further $$w'(E_{H}(S,V \backslash S))=\sum_{e\in E_{G}(S, V \backslash S)}^{} \frac{1}{p}X_{e}=\frac{1}{p}X_{S}$$Therefore, $$\begin{align}\mathbb{P}\left( \left| \frac{1}{p}X_{S}-\frac{1}{p}\mathbb{E}[X_{S}] \right| \geq \frac{\varepsilon}{p} \mathbb{E}[X_{S}] \right)&=\mathbb{P}(\left| X_{S}-\mathbb{E}[X_{S}] \right| \geq \varepsilon \mathbb{E}[X_{S}])\\&\leq 2\exp \left( -\frac{\varepsilon^{2}p\cdot  e_{G}(S,V \backslash S)  }{3} \right) \leq 2n^{-5 k}\end{align}$$Bringing it all together, $$\begin{align}&\mathbb{P}\left( \exists k\leq \frac{n}{2},S\in {V \choose k} : \left| w'(E_{H}(S, V \backslash S))-w(E_{G}(S, V \backslash S)) \right|> \varepsilon w(E_{G}(S, V \backslash S)) \right)\\&\leq \sum_{k=1}^{n/2}{n \choose k}2n^{-5 k}\leq \sum_{k=1}^{n/2}2n^{-4k}\leq n^{-3}\end{align}$$which shows the second condition. 
> 
> Further, let $X=\sum_{e\in E}^{}X_{e}$. Then, we have $\mathbb{E}[X]\leq \frac{15m\log n}{\varepsilon^{2}\phi\delta}\leq \frac{15m\log n}{\varepsilon^{2}\delta}\cdot \frac{\log^cn}{t}$ for some $c\geq 0$ and $t\geq 0$ and by Markov:$$\mathbb{P}\left( X\geq \frac{15 m\log^{c+2}n}{\varepsilon^{2}\delta} \right)\leq \frac{1}{ \log n}$$Therefore, w.h.p we have that $\left| E' \right|=\tilde{O}(\frac{m}{\varepsilon^{2}\delta})$ and we have a cut sparsifier.
---
> [!lemma] Theorem 3 (General Graphs)
> Consider the following algorithm: 
> ```pseudo
> \begin{algorithm}\caption{CutSparsifier($G,\varepsilon$)}
> \begin{algorithmic} 
> \State $\phi\gets \left\lfloor \frac{1}{8\log 4m}\right\rfloor$
> \State $G_{1},\dots,G_{k}\gets$ \Call{Expander}{$G$}
> \For{$i\in[k]$}
> \State $H_{i}\gets$ \Call{CutSparsifierExpanders}{$G,\phi,\varepsilon$}
\EndFor
> \Return $H:=\bigcup_{i\in[k]}^{} H_{i}$
> \end{algorithmic}
> \end{algorithm}
> ```
> Then, $H$ is a cut sparsifier w.h.p.

> [!proof]+
> Let $H=(V,E')$. Then, $$\mathbb{E}[\left| E' \right| ]\leq\sum_{i\in[k]}^{}\frac{15e(G_{i})\log v(G_{i})v(G)}{\varepsilon^{2}\phi^{2} e(G)}=\tilde{O}\left( \sum_{i\in[k]}^{} \right)$$$$\frac{e(G)}{v(G)}\geq \frac{e(G_{i})}{v(G_{i})}$$