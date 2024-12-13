#Definition #Algorithms 

> [!definition]
> Let $0<c< 1$ and $s:[n]\to[c,1]$. 
> 1. The ***bin covering problem*** aims to find the maximal number $k$ of bins where each bin contains at least size 1:$$\text{OPT}(I)\in\underset{ \begin{array}{c}\mathcal{B}=\{ B_{1},\dots,B_{k} \},B_{i}\subseteq[n]\\s(B_{i})\geq 1,B_{i}\cap B_{j}=\varnothing\end{array}}{ \arg\max }\left| \mathcal{B}\right| $$
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
>    \State $k\gets \left\lceil 1/\varepsilon^{2}\right\rceil$
>    \State $Q\gets \left\lfloor n\varepsilon^{2}\right\rfloor$
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

> [!proof]+
> By the assumption, we have that $\left| \text{OPT}(I) \right|\leq s(I)$. Then, $Q=\left\lfloor n\varepsilon^{2}\right\rfloor\leq \varepsilon \cdot \left| \text{OPT}(I) \right|$.
> 1. **Claim 1: $\left| \text{OPT}(I) \right|-Q\leq \left| \text{OPT}(J) \right|\leq \left| \text{OPT}(I) \right|$**
>    The second inequality is trivial, as rounding down only increases the number of bins. 
>    
>    For the second inequality, let $G_{1},\dots,G_{k}$ be the groups in $I$ before the rounding and $H_{1},\dots,H_{k}$ be the groups in $J$ after the rounding. We will pack $J$ by taking $H_{k}$ and packing each of the items in $H_{k}$ in its own bin. Denote the instance of the remaining $n-Q$ items by $J'$, i.e. $J'$ has $H_{1},\dots,H_{k-1}$. 
>    
>    Then, $J'$ can be as most as hard as $I$. Indeed, for all $i\in[k-1]$, we have that for any $v\in H_{i}$, $s(v):=\max_{u\in G_{i}}s(u)\leq s(w)$ for all $w\in G_{i+1}$. Therefore, $$\left| \text{OPT}(J) \right| \leq \left| \text{OPT}(J) \right| +Q\leq \left| \text{OPT}(I) \right| +Q$$
>  
>  Then, $$\left| \text{PTAS-BinPacking}(I) \right| =\left| \text{OPT}(J) \right|\geq (1-\varepsilon)\left| \text{OPT}(I) \right| $$

^697fb8
