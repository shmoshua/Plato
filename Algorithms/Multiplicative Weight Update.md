#Definition #Algorithms 

> [!definition]
> Given a finite sequence $S\in \{ 0,1 \}^N$ in the online setting, the ***multiplicative weight update problem*** aims to find an algorithm $\mathcal{A}$ s.t. $$\mathcal{A}\in \underset{ \mathcal{A} }{ \arg\min }\left\| \mathcal{A}(S,e_{1},\dots,e_{n})-S \right\|_{1} $$where $e_{i}$ is an oracle s.t. $e_{i}:\{ 0,1 \}^{j-1}\to \{ 0,1 \}$ gives us a prediction for $S_{j}$
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
> [!lemma] Theorem 2 (Randomized MWU)
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

$$\mathbb{E}\left[ \sum_{p\in P,p\notin C(R)}^{} w_{p}\right]\leq \frac{3}{4}\sum_{ p\in P}^{}w_{p}$$

```pseudo
\begin{algorithm}\caption{Randomized}\begin{algorithmic} 
\State $w_p\gets 1 / |P|$ for all $p\in P$
\While{$C(P)$ not found}
\State Construct $R\sube P$ given in Lemma 1.
\State Compute $C:=C(R)$.
\For{$p\in P$}

\EndFor
\EndWhile
\end{algorithmic}
\end{algorithm}
```

Let $T$ be the number of iterations. We have that: $$\mathbb{E}[T]=\sum_{i=1}^{\infty}\mathbb{P}(T\geq t)$$

We have that: $$\mathbb{P}(T\geq t)=\mathbb{P}()$$

For each iteration, let $w_{p}^t$ be the weights in $t$. Let $F_{j}$ be the weighted fraction of points outside of $C(R_{j})$. 

We have that: $$\mathbb{E}[F_{j}]\leq \frac{3}{r+1}\left( \sum_{p\in P}^{}w_{p}^{j-1} \right)^2\leq \frac{3}{r+1}e^{-2\varepsilon F_{j}}$$

At time step $j$, let $F_{j}$ be weighted fraction then, $\mathbb{E}[F_{j}]\leq \frac{3}{r+1}e^{-2\varepsilon F_{j}}$. Further, 
1. If $C(R_{j})=C$, then we are done.
2. If $C(R_{j})\neq C$, then there exists $p\in \{ p_{1},p_{2},p_{3} \}$ s.t. $q \notin C(R_{j})$. Hence, $w_{q}^j=(1-\varepsilon)w_{q}$. 

**Claim**: there exists $q$ s.t. $w_{p1}^{T}=(1-\varepsilon)^{T} / n$. Assume otherwise. 
 $$w_{p_{1}}^{T}w_{p_{2}}^{T}w_{p_{3}}^{T}\leq(1-\varepsilon)^{T} / n^3$$

Let $K_{j}$ be the number of points not in $C(R_{j})$. Then, $$\prod_{p\in P}w_{p}^j=(1-\varepsilon)^{K_{j}}\prod_{p\in P}w_{p}^j\leq e^{-K_{j}}$$and $\prod_{p\in P}w_{p}^T=(1-\varepsilon)^{\sum_{j\in [T] }^{}K_{j}}$

1. At each step $w_{p}^j\geq (1-\varepsilon)^j$: $$K_{j}(1-\varepsilon)^j\leq\sum_{p\in P}^{}w_{p}^j\mathbb{P}(p\notin C(R))=\mathbb{E}\left[ \sum_{p\in P:p\notin C(R)}^{} w_{p}^j\right]\leq \frac{3}{r+1}\sum_{p\in P}^{}w_{p}^j$$