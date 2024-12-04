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
