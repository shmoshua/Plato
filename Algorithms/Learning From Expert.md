#Definition #Algorithms 

> [!definition]
> Given a finite sequence $S\in \{ 0,1 \}^N$ in the online setting, the ***learning from expert problem*** aims to find an algorithm $\mathcal{A}$ s.t. $$\mathcal{A}\in \underset{ \mathcal{A} }{ \arg\min }\left\| \mathcal{A}(S,e_{1},\dots,e_{n})-S \right\|_{1} $$where $e_{i}$ is an oracle s.t. $e_{i}:\{ 0,1 \}^{j-1}\to \{ 0,1 \}$ gives us a prediction for $S_{j}$
---
##### Properties
> [!lemma] Theorem 1 (Deterministic MWU)
> Consider the algorithm:
> ```pseudo
> \begin{algorithm} \caption{DMWU$(S,e_{1},\dots,e_{n},\varepsilon)$}
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
> Let $m^{*}$ and $m$ be the number of mistakes $\text{DMWU}$ and the best expert $e^{*}$ makes, respectively. Then, $$m\leq 2m^{*}(1+\varepsilon)+\frac{2\log n}{\varepsilon}$$

> [!proof]-
> Let $w_{i}^j$ denote the weight at the end of the $j$-th iteration. Let $m$ be the number of mistakes our algorithm $\mathcal{A}$ makes. Let $a_{j}\neq S_{j}$. Then, the weighted majority was wrong and let $W:=\sum_{i=1}^{n}w_{i}^{j-1}$. Then, $$\sum_{i=1}^{n}w^j_{i}\leq (1-\varepsilon) \frac{W}{2}+\frac{W}{2}=W\left( 1-\frac{\varepsilon}{2} \right)$$Let the best expert $e^{*}$ make $m^{*}$ mistakes. Hence, $w_{{*}}^N=(1-\varepsilon)^{m^{*}} / n$. On the other hand, the total weight of all experts would be: $$\sum_{i=1}^{n}w_{i}^N\leq \left( 1-\frac{\varepsilon}{2} \right) ^m$$Therefore, $(1-\varepsilon)^{m^{*}} \leq n\left( 1- \varepsilon / 2 \right)^m$ and we have that $$e^{m^{*}(-\varepsilon-\varepsilon^{2})}\leq (1-\varepsilon)^{m^{*}}\leq n(1-\varepsilon / 2)^m\leq n e^{-m\varepsilon /2}$$
> Then, $$m^{*}(-\varepsilon - \varepsilon^{2})\leq -\frac{m\varepsilon}{2}+\log n$$and $m\leq 2m^{*}(1+\varepsilon)+\frac{2\log n}{\varepsilon}$.
---
> [!lemma] Theorem 2
> For any deterministic algorithm $\mathcal{A}$ for the learning problem, we have that: $$m(\mathcal{A})\geq 2m^{*}$$

> [!proof]-
> Imagine we have two experts, one predicts $0$ all the time and the other $1$. Then, as $\mathcal{A}$ is deterministic, we can make $\mathcal{A}$ make a mistake every time. But by pigeonhole, there exists an expert that makes a mistake at most $\frac{m(\mathcal{A})}{2}$ times. This proves the statement.

---
> [!lemma] Theorem 3 (Randomized MWU)
> Consider the algorithm:
> ```pseudo
> \begin{algorithm} \caption{RMWU$(S,e_{1},\dots,e_{n},\varepsilon)$}
> \begin{algorithmic}
> \State $w_{i}\gets 1 / n$ for all $i\in[n]$.
> \For{$j\gets [N]$}
> \State Sample $i\in[n]$ with probability $w_{i} / \sum_{\ell=1}^{n}w_{\ell}$
> \State $a_{i}\gets e_{i}(S_{1:j-1})$
> \If{$e_{i}(S_{1:j-1})\neq S_{j}$}
> \State $w_{i}\gets w_{i}\cdot(1-\varepsilon)$
\EndIf
\EndFor
\end{algorithmic}
\end{algorithm}
> ```
> Let $m^{*}$ and $m$ be the number of mistakes $\text{RMWU}$ and the best expert $e^{*}$ makes, respectively. Then, $$\mathbb{E}[m]\leq (1+\varepsilon)m^{*}+\frac{\log n}{\varepsilon}$$

> [!proof]-
> Let $w_{i}^j$ denote the weight at the end of the $j$-th iteration. 
> 
> Let $j\in [N]$. Let $A,B\subseteq[n]$ be the set of experts that output 0 and 1 respectively for day $j$. Let $F_{j}$ be the weighted fraction of wrong experts on day $j$. Then, $$\mathbb{E}[m]=\sum_{j=1}^{N}F_{j}$$However, we have that $\sum_{i=1}^{n}w_{i}^j\leq (1-\varepsilon) F_{j}+(1-F_{j})=1-\varepsilon F_{j}$. As $(1-\varepsilon)^{m^{*}} / n$ is the weight of the best expert at the end, we have that: $$e^{m^{*}(-\varepsilon-\varepsilon^{2})}\leq(1-\varepsilon)^{m^{*}}\leq n\cdot \prod_{j=1}^{N}(1-\varepsilon F_{j})\leq ne^{-\varepsilon \mathbb{E}[m]}$$and $m^{*}(-\varepsilon-\varepsilon^{2})\leq -\varepsilon \mathbb{E}[m]+\log n$. Hence, $$\mathbb{E}[m]\leq (1+\varepsilon)m^{*}+\frac{\log n}{\varepsilon}$$


---
