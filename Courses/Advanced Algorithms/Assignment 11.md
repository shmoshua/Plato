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

Now, notice that from $p_{1},p_{2},p_{3}$ at least one point lies out of $C(R)$ at every iteration. Hence, $$(1+\varepsilon)^a+(1+\varepsilon)^b+(1+\varepsilon)^c\leq w_{p_{1}}^T+w_{p_{2}}^T+w_{p_{3}}^T$$where $a+b+c=T$. Therefore, there exists $p\in P$ s.t. $(1+\varepsilon)^{T / 3}\leq w_{p}^T$. Hence, $$e^{T\varepsilon/6}\leq w_{p}^T\leq \sum_{p\in P}^{}w_{p}^T=n\prod_{j\in [T]}^{}(1+\varepsilon F_{j})\leq ne^{\varepsilon \sum_{j\in[T]}^{}F_{j}}$$and $T\leq \sum_{j\in[T]}^{}F_{j}+\frac{6\log n}{\varepsilon}$. Now, $$\begin{align}\mathbb{E}\left[ \sum_{j\in [T]}^{}F_{j} \right]&=\sum_{j=1}^{\infty}\mathbb{E}[F_{j}\cdot \mathbb{1}_{T\geq j}]\end{align}$$
We have that: $$\begin{align}\mathbb{E}[F_{j}\cdot \mathbb{1}_{T\geq j}]&=\mathbb{E}[\mathbb{E}[F_{j}\cdot \mathbb{1}_{T\geq j}|\mathbb{1}_{T\geq j}]]\\&=\mathbb{E}[F_{j}|T\geq j]\mathbb{P}(T\geq j)\\&\leq \frac{3}{r+1}\left( \sum_{p\in P}^{}w_{p}^{j-1} \right) ^{2}\mathbb{P}(T\geq j)\\&\leq \frac{3n^{2}}{r+1}\prod_{\ell=1}^{j-1}(1+\varepsilon F_{\ell})^{2}\mathbb{P}(T\geq j)\end{align}$$Therefore, $$\begin{align}\mathbb{E}\left[ \sum_{j\in [T]}^{}F_{j} \right]&=\sum_{j=1}^{\infty}\mathbb{E}[F_{j}\cdot \mathbb{1}_{T\geq j}]\leq \sum_{j=1}^{\infty}\frac{3n^2}{r+1}\prod_{\ell=1}^{j-1}(1+\varepsilon F_{\ell})^{2}\mathbb{P}(T\geq j)\end{align}$$

We claim that $\mathbb{E}\left[ \sum_{j\in [T]}^{}F_{j} \right]\leq c\log n$. Otherwise, there exists an instance with $\sum_{j\in [T]}^{}F_{j}\geq c\log n$

We have: $$\mathbb{E}[F_{j}]\leq\frac{3}{r+1}\left( \sum_{p\in P}^{}w_{p}^{j-1} \right)^{2}=\frac{3n^{2}}{r+1}\prod_{\ell=1}^{j-1}(1+\varepsilon F_{\ell})^{2}$$

$$\prod_{i=1}^{j-1}(1+\varepsilon F_{\ell})\leq \frac{1}{n}$$

$(x-1)\mathbb{E}[T]\geq -6\log n$

---

Let $T$ be the number of iterations. Let $w_{p}^j$ be $w_{p}$ at the end of the $j$-th iteration. Then, for all $j\geq 1$: $$\sum_{p\in P}^{}w_{p}^j=\sum_{p\in P: p\notin C(R_{j})}^{}w_{p}^{j-1}+(1-\varepsilon)\sum_{p\in P: p\in C(R_{j})}^{}w_{p}^{j-1}=(F_{j}+(1-\varepsilon)(1-F_{j}))\sum_{p\in P}^{}w_{p}^{j-1}$$where $F_{j}:=(\sum_{p\in P: p\notin C(R_{j})}^{}w_{p}^{j-1}) / (\sum_{p\in P}^{}w_{p}^{j-1})$. Therefore, $\sum_{p\in P}^{}w_{p}^T=\prod_{j\in [T]}^{}(1-\varepsilon( 1-F_{j}))n$.

Therefore, there exists $p\in P$ s.t. $(1-\varepsilon)^{2T / 3}\leq w_{p}^T$. Hence, $$e^{-}\leq w_{p}^T\leq \sum_{p\in P}^{}w_{p}^T=n\prod_{j\in [T]}^{}(1+\varepsilon F_{j})\leq ne^{\varepsilon \sum_{j\in[T]}^{}F_{j}}$$and $T\leq \sum_{j\in[T]}^{}F_{j}+\frac{6\log n}{\varepsilon}$. Now, $$\begin{align}\mathbb{E}\left[ \sum_{j\in [T]}^{}F_{j} \right]&=\sum_{j=1}^{\infty}\mathbb{E}[F_{j}\cdot \mathbb{1}_{T\geq j}]\end{align}$$
We have that: $$\begin{align}\mathbb{E}[F_{j}\cdot \mathbb{1}_{T\geq j}]&=\mathbb{E}[\mathbb{E}[F_{j}\cdot \mathbb{1}_{T\geq j}|\mathbb{1}_{T\geq j}]]\\&=\mathbb{E}[F_{j}|T\geq j]\mathbb{P}(T\geq j)\\&\leq \frac{3}{r+1}\left( \sum_{p\in P}^{}w_{p}^{j-1} \right) ^{2}\mathbb{P}(T\geq j)\\&\leq \frac{3n^{2}}{r+1}\prod_{\ell=1}^{j-1}(1+\varepsilon F_{\ell})^{2}\mathbb{P}(T\geq j)\end{align}$$Therefore, $$\begin{align}\mathbb{E}\left[ \sum_{j\in [T]}^{}F_{j} \right]&=\sum_{j=1}^{\infty}\mathbb{E}[F_{j}\cdot \mathbb{1}_{T\geq j}]\leq \sum_{j=1}^{\infty}\frac{3n^2}{r+1}\prod_{\ell=1}^{j-1}(1+\varepsilon F_{\ell})^{2}\mathbb{P}(T\geq j)\end{align}$$