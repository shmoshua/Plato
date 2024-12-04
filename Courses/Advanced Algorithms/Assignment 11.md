#Series #Algorithms 

##### Problem 2
Let $p_{1},p_{2},p_{3}$ be s.t. $C(P)=C(\{ p_{1},p_{2},p_{3} \})$. 
```pseudo
\begin{algorithm}\caption{MWU-MinimumEnclosingCircle($P$)}\begin{algorithmic} 
\State $w_p\gets 1$ for all $p\in P$
\While{true}
\State Construct $R\sube P$ given in Lemma 1.
\If{$P\in C(R)$}
\Return $C(R)$
\EndIf
\State $w_p\gets (1+\varepsilon) w_p$ for all $p\notin C(R)$
\EndWhile
\end{algorithmic}
\end{algorithm}
```

Let $T$ be the number of iterations. Let $w_{p}^j$ be $w_{p}$ at the end of the $j$-th iteration. Then, for all $j\geq 1$: $$\sum_{p\in P}^{}w_{p}^j=(1+\varepsilon)\sum_{p\in P: p\notin C(R_{j})}^{}w_{p}^{j-1}+\sum_{p\in P: p\in C(R_{j})}^{}w_{p}^{j-1}=((1+\varepsilon)F_{j}+(1-F_{j}))\sum_{p\in P}^{}w_{p}^{j-1}$$where $F_{j}:=(\sum_{p\in P: p\notin C(R_{j})}^{}w_{p}^{j-1}) / (\sum_{p\in P}^{}w_{p}^{j-1})$. Therefore, $\sum_{p\in P}^{}w_{p}^T=\prod_{j\in [T]}^{}(1+\varepsilon F_{j})n$.

Now, notice that from $p_{1},p_{2},p_{3}$ at least one point lies out of $C(R)$ at every iteration. Hence, $$(1+\varepsilon)^a+(1+\varepsilon)^b+(1+\varepsilon)^c\leq w_{p_{1}}^T+w_{p_{2}}^T+w_{p_{3}}^T$$where $a+b+c=T$. Therefore, there exists $p\in P$ s.t. $(1+\varepsilon)^{T / 3}\leq w_{p}^T$. Hence, $$e^{T\varepsilon/6}\leq w_{p}^T\leq \sum_{p\in P}^{}w_{p}^T=n\prod_{j\in [T]}^{}(1+\varepsilon F_{j})\leq ne^{\varepsilon \sum_{j\in[T]}^{}F_{j}}$$and $T\leq \sum_{j\in[T]}^{}F_{j}+\frac{6\log n}{\varepsilon}$. Now, $$\begin{align}\mathbb{E}\left[ \sum_{j\in [T]}^{}F_{j} \right]&=\sum_{j=1}^{\infty}\mathbb{E}[F_{j}\cdot \mathbb{1}_{T>j}]\end{align}$$
We have that: $$\begin{align}\mathbb{E}[F_{j}\cdot \mathbb{1}_{T>j}]&=\mathbb{E}[\mathbb{E}[F_{j}\cdot \mathbb{1}_{T>j}|\mathbb{1}_{T>j}]]\\&=\mathbb{E}[F_{j}|T>j]\mathbb{P}(T>j)\\&\leq \int_{0}^{1}  F_{j}\, d\mathbb{P} \end{align}$$

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