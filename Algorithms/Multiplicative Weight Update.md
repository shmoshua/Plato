#Definition #Algorithms 

> [!definition]
> Given a finite sequence $S\in \{ 0,1 \}^N$ in the online setting, the ***multiplicative weight update problem*** aims to find an algorithm $\mathcal{A}$ s.t. $$\mathcal{A}\in \underset{ \mathcal{A} }{ \arg\min }\left\| \mathcal{A}(S,e_{1},\dots,e_{n})-S \right\|_{1} $$where $e_{i}$ is an oracle s.t. $e_{i}:\{ 0,1 \}^{j-1}\to \{ 0,1 \}$ gives us a prediction for $S_{j}$
---
##### Properties
> [!lemma] Theorem 1 (MWU)
> Consider the algorithm:
> ```pseudo
> \begin{algorithm} \caption{MWU$(S,e_{1},\dots,e_{n},\varepsilon)$}
> \begin{algorithmic}
> \State $w_{i}\gets 1 / n$ for all $i\in[n]$.
> \For{$j\gets [N]$}
> \State $a_{i}\gets $weighted majority of $e_{1}(S_{1:j-1}),\dots,e_{n}(S_{1:j-1})$ w.r.t. $w_{1},\dots,w_{n}$.
> \If{$e_{i}(S_{1:j-1})\neq S_{j}$}
> \State $w_{i}\gets w_{i}\cdot(1-\varepsilon)$
\EndIf
\EndFor
\end{algorithmic}
\end{algorithm}
> ```

> [!proof]+
> Let $w_{i}^j$ denote the weight at the end of the $j$-th iteration. Let $a_{j}\neq S_{j}$. Then, the weighted majority was wrong and let $W:=\sum_{i=1}^{n}w_{i}^{j-1}$. Then, $$\sum_{i=1}^{n}w^j_{i}\leq (1-\varepsilon) \frac{W}{2}+\frac{W}{2}=W\left( 1-\frac{\varepsilon}{2} \right)$$