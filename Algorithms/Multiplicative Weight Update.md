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
> Let $m^{*}$ and $m$ be the number of mistakes $\text{MWU}$ and the best expert $e^{*}$ makes, respectively. Then, $$m\leq 2m^{*}(1+\varepsilon)+\frac{2\log n}{\varepsilon}$$

> [!proof]+
> Let $w_{i}^j$ denote the weight at the end of the $j$-th iteration. Let $m$ be the number of mistakes our algorithm $\mathcal{A}$ makes. Let $a_{j}\neq S_{j}$. Then, the weighted majority was wrong and let $W:=\sum_{i=1}^{n}w_{i}^{j-1}$. Then, $$\sum_{i=1}^{n}w^j_{i}\leq (1-\varepsilon) \frac{W}{2}+\frac{W}{2}=W\left( 1-\frac{\varepsilon}{2} \right)$$Let the best expert $e^{*}$ make $m^{*}$ mistakes. Hence, $w_{{*}}^N=(1-\varepsilon)^{m^{*}} / n$. On the other hand, the total weight of all experts would be: $$\sum_{i=1}^{n}w_{i}^N\leq \left( 1-\frac{\varepsilon}{2} \right) ^m$$Therefore, $(1-\varepsilon)^{m^{*}} \leq n\left( 1- \varepsilon / 2 \right)^m$ and we have that $$e^{m^{*}(-\varepsilon-\varepsilon^{2})}\leq (1-\varepsilon)^{m^{*}}\leq n(1-\varepsilon / 2)^m\leq n e^{-}$$
> $$m^{*}\log(1-\varepsilon)\leq m\log (1-\varepsilon /2) + \log n$$Then, as $-x-x^{2}\leq \log (1-x)\leq -x$ for $x<1 / 2$, $$m^{*}(-\varepsilon - \varepsilon^{2})\leq -\frac{m\varepsilon}{2}+\log n$$and $m\leq 2m^{*}(1+\varepsilon)+\frac{2\log n}{\varepsilon}$.
---
