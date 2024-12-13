#Definition #Algorithms 

> [!definition]
> Let $0<c< 1$ and $s:[n]\to[c,1]$. 
> 1. The ***bin covering problem*** aims to find the maximal number $k$ of bins where each bin contains at least size 1:$$\text{OPT}(I)\in\underset{ \begin{array}{c}\mathcal{B}=\{ B_{1},\dots,B_{k} \},B_{i}\subseteq[n]\\s(B_{i})\geq 1,B_{i}\cap B_{j}=\varnothing\end{array}}{ \arg\max }\left| \mathcal{B}\right| $$

^e1a1e7

---
##### Properties
> [!lemma] Proposition 1
> With the assumptions that:
> 1. There are only $k$ possible sizes.
> ```pseudo
>    \begin{algorithm} \caption{ExactBinCovering($I,c,k$)} 
>    \begin{algorithmic}
>    \State Enumerate all possible bin configuration.
>    \Return the best bin configuration.
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    solves bin covering in $O(n^R)$ time where $R$ is a constant.

^62d5f8

> [!proof]-
> Going through all possible bin configuration with the given $n$ items is upper bounded by going through all possible configurations of bins, choosing from arbitrarily many items of $k$ fixed sizes.  Let $M:=\left\lceil \frac{1}{c}\right\rceil$. Then, each bin has at most $M$ items. By the second assumption, we have at most $R:={M+k \choose M}$ configurations in a bin. By choosing $n$ bins from these $R$ bins, we have at most $${n+R \choose n}={n+R\choose R}\leq(n+R)^R=O(n^R) $$

^5e1d26

---
> [!lemma] Proposition 2
> ```pseudo
>    \begin{algorithm} \caption{PTAS-BinCovering($I,\varepsilon$)} 
>    \begin{algorithmic}
>    \State $\varepsilon\gets \min\left\{  \varepsilon, 1/\left\lceil \frac{1}{c}\right\rceil  \right\}$
>    \State $k\gets \left\lceil 1/\varepsilon^{2}\right\rceil$
>    \State $Q\gets \left\lfloor \varepsilon \left\lfloor n\varepsilon\right\rfloor\right\rfloor$
>    \State Sort the items by size in decreasing order.
>    \State Partition $n$ items into $k$ non-overlapping groups $G_{1},\dots,G_{k}$, each with $Q$ items in order.
>    \For{$i\in [k]$}
>    \State $i_{\text{min}}\gets \min_{u\in G_{i}}s(u)$
>    \For{$u\in G_{i}$}
>    \State $s(u)\gets i_{\min}$\EndFor
>    \EndFor
>    \State Denote the modified instance as $J$.
>    \Return \Call{ExactBinCovering}{$J,c,k$}
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    is a [[PTAS]] for bin covering.

^cb3b26

> [!proof]-
> By the assumption, we have that $\varepsilon\leq \frac{1}{\left\lceil 1 / c\right\rceil}$ and $\left\lfloor \varepsilon n\right\rfloor\leq \left\lfloor \frac{n}{\left\lceil 1 / c\right\rceil}\right\rfloor\leq \left| \text{OPT}(I) \right|$. Then, $Q= \left\lfloor \varepsilon \left\lfloor n\varepsilon\right\rfloor\right\rfloor\leq \varepsilon \cdot \left| \text{OPT}(I) \right|$.
> 1. **Claim 1: $\left| \text{OPT}(I) \right|-Q\leq \left| \text{OPT}(J) \right|\leq \left| \text{OPT}(I) \right|$**
>    The second inequality is trivial, as rounding down only decreases the number of bins. 
>    
>    For the first inequality, let $G_{1},\dots,G_{k}$ be the groups in $I$ before the rounding and $H_{1},\dots,H_{k}$ be the groups in $J$ after the rounding. We now design a covering for $J$. Take the optimal covering for $I$. Remove $H_{k}$ from the covering and move $H_{i}$ down to $H_{i+1}$ for each item in the optimal covering. Then, this is still a valid covering in $J$ and we lose at most $\left| H_{k} \right|:=Q$ bins. Hence, $$\left| \text{OPT}(I) \right| -Q\leq \left| \text{OPT}(J) \right| $$
>    
>  
>  Then, $$\left| \text{PTAS-BinPacking}(I) \right| =\left| \text{OPT}(J) \right|\geq \left| \text{OPT}(I) \right|-Q\geq(1-\varepsilon)\left| \text{OPT}(I) \right| $$

^697fb8

---