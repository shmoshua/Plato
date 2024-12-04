> [!definition]
> Let $P=\{ p_{1},\dots,p_{n} \}\subseteq \mathbb{R}^2$. The ***minimum enclosing circle problem*** is finding: $$(x^{*},r^{*}):=\underset{ (x,r): P\subseteq B_{\leq r}(x) }{ \arg\min }r$$
---
##### Properties
> [!lemma] Theorem 1
> Consider the following algorithm:
> ```pseudo
> \begin{algorithm}\caption{MEC($P$)}
> \begin{algorithmic}
> \For{$S\in{P \choose 3}$}
> \State Find a circle that goes through $S$.
> \State Check if it is an enclosing circle.
> \EndFor
> \Return the minimum circle from all found enclosing circles.
\end{algorithmic}
\end{algorithm}
> ```
> solves the minimum enclosing circle problem in $O(n^4)$.
---
##### Problem 2
Let $p_{1},p_{2},p_{3}$ be s.t. $C(P)=C(\{ p_{1},p_{2},p_{3} \})$. 
```pseudo
\begin{algorithm}\caption{MWU-MinimumEnclosingCircle($P$)}\begin{algorithmic} 
\State $w_p\gets 1$ for all $p\in P$
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